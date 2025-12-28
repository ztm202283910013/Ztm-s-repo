https://istio.io/latest/docs/tasks/traffic-management/traffic-shifting/

**Istio APIs**

![image-20251228215723587](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228215723587.png)

![image-20251228215750533](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228215750533.png)

![image-20251228215814866](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228215814866.png)

![image-20251228215823163](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228215823163.png)

![image-20251228220004768](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220004768.png)

**Gateway API**

![image-20251228220029445](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220029445.png)

![image-20251228220101170](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220101170.png)

![image-20251228220208223](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220208223.png)

https://istio.io/latest/docs/tasks/traffic-management/request-routing/

**Istio APIs**

![image-20251228220246831](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220246831.png)

![image-20251228220258206](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220258206.png)

![image-20251228220313168](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220313168.png)

**Gateway API**

![image-20251228220332430](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220332430.png)

![image-20251228220346696](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220346696.png)

![image-20251228220401566](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220401566.png)

![image-20251228220417253](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220417253.png)

https://istio.io/latest/docs/tasks/traffic-management/fault-injection/

**Create a fault injection rule to delay traffic coming from the test user jason.**

![image-20251228220450255](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220450255.png)

![image-20251228220507729](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220507729.png)

![image-20251228220527449](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220527449.png)

**Fixing the bug**

1. Either increasing the productpage to reviews service timeout or decreasing the reviews to ratingstimeout
2. Stopping and restarting the fixed microservice
3. Confirming that the /productpage web page returns its response without any errors.

![image-20251228220623021](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220623021.png)

**Injecting an HTTP abort fault**

![image-20251228220651603](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220651603.png)

![image-20251228220725193](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220725193.png)

https://istio.io/latest/docs/tasks/traffic-management/circuit-breaking/

**Configuring the circuit breaker**

![image-20251228220800163](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220800163.png)

![image-20251228220814371](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220814371.png)

**Adding a client**

![image-20251228220833901](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220833901.png)

**Tripping the circuit breaker**

![image-20251228220856064](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220856064.png)

![image-20251228220922362](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220922362.png)

![image-20251228220936850](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220936850.png)

![image-20251228220948214](C:\Users\张泰铭\AppData\Roaming\Typora\typora-user-images\image-20251228220948214.png)