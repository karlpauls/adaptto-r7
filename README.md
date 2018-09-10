# adaptto-r7

## First

Clone and mvn clean install the following repo: https://github.com/karlpauls/adaptto-featuremodel
Clone and mvn clean install the following repo: https://github.com/apache/sling-org-apache-sling-feature-launcher

## Then

export JAVA_HOME=$(/usr/libexec/java_home -v 10)

du -h -d0 $JAVA_HOME

rm -rf se.ee && \
/Library/Java/JavaVirtualMachines/jdk-10.jdk/Contents/Home/bin/jlink \
  --add-modules java.se.ee \
  --output se.ee

du -h -d0 se.ee

se.ee/bin/java --add-modules java.se.ee --add-opens=java.base/jdk.internal.loader=ALL-UNNAMED --add-opens=java.base/java.net=ALL-UNNAMED \
  -jar ~/.m2/repository/org/apache/sling/org.apache.sling.feature.launcher/0.1.0-SNAPSHOT/org.apache.sling.feature.launcher-0.1.0-SNAPSHOT.jar \
  -f mvn:org.apache.sling/org.apache.sling.adaptto.featuremodel.example/0.0.1/slingfeature/webconsole.http \
  -D felix.systempackages.calculate.uses=true -D org.osgi.framework.storage.clean=onFirstInit

se.ee/bin/java --add-opens=java.base/jdk.internal.loader=ALL-UNNAMED --add-opens=java.base/java.net=ALL-UNNAMED \
  -jar ~/.m2/repository/org/apache/sling/org.apache.sling.feature.launcher/0.1.0-SNAPSHOT/org.apache.sling.feature.launcher-0.1.0-SNAPSHOT.jar \
  -f mvn:org.apache.sling/org.apache.sling.adaptto.featuremodel.example/0.0.1/slingfeature/webconsole.http \
  -D felix.systempackages.calculate.uses=true -D org.osgi.framework.storage.clean=onFirstInit

rm -rf min && \
/Library/Java/JavaVirtualMachines/jdk-10.jdk/Contents/Home/bin/jlink \
  --add-modules java.base,java.logging,java.xml.ws.annotation,java.management,java.naming,java.rmi,java.xml \
  --output min

du -h -d0 min

min/bin/java --add-opens=java.base/jdk.internal.loader=ALL-UNNAMED --add-opens=java.base/java.net=ALL-UNNAMED \
  -jar ~/.m2/repository/org/apache/sling/org.apache.sling.feature.launcher/0.1.0-SNAPSHOT/org.apache.sling.feature.launcher-0.1.0-SNAPSHOT.jar \
  -f mvn:org.apache.sling/org.apache.sling.adaptto.featuremodel.example/0.0.1/slingfeature/webconsole.http \
  -D felix.systempackages.calculate.uses=true -D org.osgi.framework.storage.clean=onFirstInit

se.ee/bin/java --add-modules java.se.ee --add-opens=java.base/jdk.internal.loader=ALL-UNNAMED --add-opens=java.base/java.net=ALL-UNNAMED \
  -jar ~/.m2/repository/org/apache/sling/org.apache.sling.feature.launcher/0.1.0-SNAPSHOT/org.apache.sling.feature.launcher-0.1.0-SNAPSHOT.jar \
  -f mvn:org.apache.sling/org.apache.sling.adaptto.featuremodel.example/0.0.1/slingfeature/webconsole.http \
  -D felix.systempackages.calculate.uses=true -D org.osgi.framework.storage.clean=onFirstInit

cd example1 && mvn clean install sling:install

min/bin/java --add-opens=java.base/jdk.internal.loader=ALL-UNNAMED --add-opens=java.base/java.net=ALL-UNNAMED \
  -jar ~/.m2/repository/org/apache/sling/org.apache.sling.feature.launcher/0.1.0-SNAPSHOT/org.apache.sling.feature.launcher-0.1.0-SNAPSHOT.jar \
  -f mvn:org.apache.sling/org.apache.sling.adaptto.featuremodel.example/0.0.1/slingfeature/webconsole.http \
  -D felix.systempackages.calculate.uses=true -D org.osgi.framework.storage.clean=onFirstInit

cd example1 && mvn clean install sling:install

se.ee/bin/java --add-modules java.se.ee --add-opens=java.base/jdk.internal.loader=ALL-UNNAMED --add-opens=java.base/java.net=ALL-UNNAMED \
  -jar ~/.m2/repository/org/apache/sling/org.apache.sling.feature.launcher/0.1.0-SNAPSHOT/org.apache.sling.feature.launcher-0.1.0-SNAPSHOT.jar \
  -f mvn:org.apache.sling/org.apache.sling.adaptto.featuremodel.example/0.0.1/slingfeature/webconsole.http \
  -f mvn:org.apache.sling/org.apache.sling.adaptto.featuremodel.example/0.0.1/slingfeature/gogo \
  -D felix.systempackages.calculate.uses=true -fv 5.6.10 -D org.osgi.framework.storage.clean=onFirstInit

install file:example1/target/org.apache.sling.adaptto.r7.example1-0.0.1.jar 

cd example2 && mvn clean install sling:install

min/bin/java --add-opens=java.base/jdk.internal.loader=ALL-UNNAMED --add-opens=java.base/java.net=ALL-UNNAMED \
  -jar ~/.m2/repository/org/apache/sling/org.apache.sling.feature.launcher/0.1.0-SNAPSHOT/org.apache.sling.feature.launcher-0.1.0-SNAPSHOT.jar \
  -f mvn:org.apache.sling/org.apache.sling.adaptto.featuremodel.example/0.0.1/slingfeature/webconsole.http \
  -D felix.systempackages.calculate.uses=true -D org.osgi.framework.storage.clean=onFirstInit

cd example2 && mvn clean install sling:install
