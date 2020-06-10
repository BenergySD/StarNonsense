# BenergySD/StarNonsense

[Permalink](https://github.com/BenergySD/StarNonsense/blob/d50631e5c2dd644bb565e50f3672e09ba07c0e9f/milliconverter.java)

 19 lines \(15 sloc\) 657 Bytes

|  | import java.util.concurrent.TimeUnit; |
| :--- | :--- |
|  |  |
|  | public class Milliseconds { |
|  | // hfkdshfgkdshafgklshakfldhsajkfhdjksal Does this update????? |
|  |  public static void main\(String\[\] args\) { |
|  |  long milliseconds = 1000000; |
|  |  System.out.println\("Does this update??"\) |
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

