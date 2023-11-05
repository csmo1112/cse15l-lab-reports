## Part 1: Bugs  
Failure-inducing input:  
In `ArrayTests.java`, we have the test of a simple array, `{1, 2, 3}`:  
```
@Test
public void testReversed2() {
  int[] input1 = {1,2,3};
  assertArrayEquals(new int[]{3,2,1}, ArrayExamples.reversed(input1));
}
```
An input that does not cause a failure is when an array's reverse is the same as the original, for example `{}`:
```
  @Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```  
The symptom when running in the terminal:
```
JUnit version 4.13.2
...E
Time: 0.01
There was 1 failure:
1) testReversed2(ArrayTests)
arrays first differed at element [0]; expected:<3> but was:<0>
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:78)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:28)
        at org.junit.Assert.internalArrayEquals(Assert.java:534)
        at org.junit.Assert.assertArrayEquals(Assert.java:418)
        at org.junit.Assert.assertArrayEquals(Assert.java:429)
        at ArrayTests.testReversed2(ArrayTests.java:22)
        ... 30 trimmed
Caused by: java.lang.AssertionError: expected:<3> but was:<0>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at org.junit.internal.ExactComparisonCriteria.assertElementsEqual(ExactComparisonCriteria.java:8)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:76)
        ... 36 more

FAILURES!!!
Tests run: 3,  Failures: 1
```
In `ArrayExamples.java`, we keep the original code to replicate the bug:  
```
  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
And we fixed the bug and the new, working code is shown below:
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[arr.length - i - 1] = arr[i];
    }
    return newArray;
  }
```  
By making the function return `newArray` instead of `arr` (the original array), and switching the order of assignment, we fix the bugs in the function `reversed()`. Previously, the function copied empty array values from `newArray` into the original array instead of copying original values into the new one, resulting in the fuction returning an empty array. After the fixes, the symptoms are addressed as well:
```
JUnit version 4.13.2
...
Time: 0.011

OK (3 tests)
```

## Part 2: Researching Commands  

`grep` has many command-line options, and the four that I chose are `-r`, `-c`, `-w`, and `-v`. Generally, `grep` looks for patterns within . I found these while looking at the [Linux Manual Page](https://man7.org/linux/man-pages/man1/grep.1.html), and the examples on `./technical` are shown below:  

`-r` recursively searches the specified directory and its contents, and returns the line containing the match. The first test I did was calling `grep -r "Monday" .`, and my results are shown here:  
```
chris@LAPTOP-HS27MT5I MINGW64 ~/Documents/GitHub/docsearch/technical (main)
$ grep -r "Monday" .
./911report/chapter-10.txt:                    competitive firms of the financial industry, the markets reopened on Monday,
./911report/chapter-10.txt:                prepared a paper that President Bush then considered with principals on Monday
./biomed/1471-2458-1-9.txt:        followed by the week's highest counts on Mondays. However,
./biomed/1472-6920-2-1.txt:            (Monday, Wednesday and Friday afternoons) during a
./government/Media/AP_LawSchoolDebts.txt:private sector, a study being released Monday found.
./government/Media/Barnes_new_job.txt:On Monday, departing Gov. Roy Barnes will spend his first day as
./government/Media/Boone_legal_service.txt:Monday, December 23, 2002
./government/Media/Crains_New_York_Business.txt:Monday, September 9, 2002
./government/Media/Disaster_center.txt:will be available from 8 a.m. to 8 p.m., Monday through Thursday,
./government/Media/fight_domestic_abuse.txt:U.S. Rep. John Tanner announced Monday that the grant was
./government/Media/Funds_Shortage.txt:the keynote speech to the legal aid providers on Monday and will
./government/Media/help_rent-to-own_tenants.txt:director) Ed McCann about it," Bryant said Monday. "I asked them to
./government/Media/Law_Schools.txt:Monday, December 16, 2002
./government/Media/Library_Lawyers.txt:Monday, December 16, 2002
./government/Media/NJ_Legal_Services.txt:Monday, October 14, 2002
./government/Media/Owning_a_Piece.txt:On Monday, Legal Aid will break ground at the first building it
./government/Media/pro_bono_efforts.txt:Monday.
./government/Media/Rumble_in_the_Bronx.txt:Services system. Last Monday, the Bronx organization filed a
./government/Media/Rumble_in_the_Bronx.txt:City Limits (NY) - Monday, August 12, 2002
./government/Media/State_funding.txt:Monday, December 16, 2002
./government/Media/The_Columbian.txt:OLYMPIA -- The U.S. Supreme Court agreed Monday to hear a
./government/Media/Unusual_Woodburn.txt:Monday, October 28, 2002 Alex Davis
./government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt:Sweden chose to deliver two days per week (Monday/Thursday in some
./government/Post_Rate_Comm/Gleiman_EMASpeech.txt:on Monday, November 13th.
./government/Post_Rate_Comm/Gleiman_gca2000.txt:weekend, before the December board meeting that took place Monday
./plos/pmed.0020059.txt:          The first step is to stratify the data by day of week: Monday, Tuesday,…, Sunday. The
./plos/pmed.0020059.txt:          z, given that it was observed on a Monday, is the same for all Mondays,
./plos/pmed.0020059.txt:          the same hospital and the same day of week. That is, if Monday was missing during the
./plos/pmed.0020059.txt:          last week, then we removed all Mondays for that hospital. This removal introduces
```  
Since my working directory was `/c/Users/chris/Documents/GitHub/docsearch/technical`, it recursively searched all directories within `technical` and outputted the line that had "Monday" in it. I then tested `grep -r "Monday" ./911report/` and as expected, got the top two matches from the above output: 
```
chris@LAPTOP-HS27MT5I MINGW64 ~/Documents/GitHub/docsearch/technical (main)
$ grep -r "Monday" ./911report/
./911report/chapter-10.txt:                    competitive firms of the financial industry, the markets reopened on Monday,
./911report/chapter-10.txt:                prepared a paper that President Bush then considered with principals on Monday
```
