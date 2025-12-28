https://knative.dev/docs/getting-started/about-knative-functions/

Installing the func CLI

![image-20251228221452614](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228221452614.png)

Running a function

![image-20251228221520201](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228221520201.png)

function has been successfully run by using the invoke command and observing the output

![image-20251228221624488](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228221624488.png)

https://knative.dev/docs/getting-started/first-service/

Pull and Tag the Image for Local Registry

![image-20251228221737983](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228221737983.png)

Deploying a Knative Service

![image-20251228221817884](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228221817884.png)

![image-20251228221837266](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228221837266.png)

Traffic splitting

![image-20251228221855151](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228221855151.png)

View existing Revisions

![image-20251228221922051](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228221922051.png)

Splitting traffic between Revisions

![image-20251228221938643](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228221938643.png)

Verify the traffic split

![image-20251228221958393](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228221958393.png)

![image-20251228222013605](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228222013605.png)

https://knative.dev/docs/getting-started/getting-started-eventing/

![image-20251228222034831](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228222034831.png)

![image-20251228222047786](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228222047786.png)

Sources, Brokers, and Triggers

![image-20251228222102629](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228222102629.png)

Using a Knative Service as a source

![image-20251228222118712](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228222118712.png)

![image-20251228222137043](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228222137043.png)

Examining the CloudEvents Player

 

Using Triggers and sinks

Create a Trigger that listens for CloudEvents from the event source and places them into the sink, which is also the CloudEvents Player app.

![image-20251228222155811](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228222155811.png)