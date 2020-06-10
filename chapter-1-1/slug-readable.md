# BenergySD/StarNonsense

[Permalink](https://github.com/BenergySD/StarNonsense/blob/941be3957221a39ce3ae7bb71b00e34bff3594cd/milliconverter.java)

 Fetching contributors…

![](https://github.githubassets.com/images/spinners/octocat-spinner-32-EAF2F5.gif) Cannot retrieve contributors at this time

 19 lines \(13 sloc\) 552 Bytes

|  | import java.util.concurrent.TimeUnit; |
| :--- | :--- |
|  |  |
|  | public class Milliseconds { |
|  |  |
|  |  public static void main\(String\[\] args\) { |
|  |  long milliseconds = 1000000; |
|  |  |
|  |  // long minutes = \(milliseconds / 1000\) / 60; |
|  |  long minutes = TimeUnit.MILLISECONDS.toMinutes\(milliseconds\); |
|  |  |
|  |  // long seconds = \(milliseconds / 1000\); |
|  |  long seconds = TimeUnit.MILLISECONDS.toSeconds\(milliseconds\); |
|  |  |
|  |  System.out.format\("%d Milliseconds = %d minutes\n", milliseconds, minutes \); |
|  |  System.out.println\("Or"\); |
|  |  System.out.format\("%d Milliseconds = %d seconds", milliseconds, seconds \); |
|  |  |
|  |  } |
|  | } |

