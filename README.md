# oc-demo-02

oc project oc-demo-02

oc new-app \  
https://github.com/montebello64/oc-demo-02.git \  
--docker-image=montebello64/java-s2i \  
--context-dir=rest-name \  
--name=rest-name \  
-e SPRING_PROFILES_ACTIVE=openshift \  
-l microservice=oc-demo-02

oc expose service rest-name \  
--hostname=rest-name.zuggerschnecksche.de

oc new-app \  
https://github.com/montebello64/oc-demo-02.git \  
--docker-image=montebello64/java-s2i \  
--context-dir=rest-greeting \  
--name=rest-greeting \  
-e SPRING_PROFILES_ACTIVE=openshift \  
-l microservice=oc-demo-02

oc expose service rest-greeting \  
--hostname=rest-greeting.zuggerschnecksche.de

oc new-app \  
https://github.com/montebello64/oc-demo-02.git \  
--docker-image=montebello64/java-s2i \  
--context-dir=rest-consumer \  
--name=rest-consumer \  
-e SPRING_PROFILES_ACTIVE=openshift \  
-l microservice=oc-demo-02

oc expose service rest-consumer \  
--hostname=rest-consumer.zuggerschnecksche.de
