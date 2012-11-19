This maven plugin generates services files for the ServiceLoader introduced in Java 6 :
http://java.sun.com/javase/6/docs/api/java/util/ServiceLoader.html

for example:

    <build>
      <plugins>
        <plugin>
          <groupId>eu.somatik.serviceloader-maven-plugin</groupId>
          <artifactId>serviceloader-maven-plugin</artifactId>
          <configuration>
            <services>
              <param>com.foo.Dictionary</param>
              <param>com.foo.Operation</param>
            </services>
          </configuration>
        </plugin>
      </plugins>
    </build>

this will generate these files:
META-INF/services/com.foo.Dictionary
META-INF/services/com.foo.Operation
by scanning the generated classes and finding all
non-abstract/non-interface implementations of the service interfaces.
The plugin itself has no Java 6 dependency

More info here: 
http://jira.codehaus.org/browse/MOJO-1272?focusedCommentId=242147#action_242147