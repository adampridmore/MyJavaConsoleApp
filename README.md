# MyJavaConsoleApp

 - How to make a Java console application

 - mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=5-SNAPSHOT

 - Add the following plugin to the maven pom.xml

<pre class='prettyprint linenums'>&lt;build>
  &lt;plugins>
    &lt;plugin>
      &lt;groupId>org.apache.maven.plugins&lt;/groupId>
      &lt;artifactId>maven-jar-plugin&lt;/artifactId>
    &lt;/plugin>
    &lt;plugin>
      &lt;groupId>org.apache.maven.plugins&lt;/groupId>
      &lt;artifactId>maven-shade-plugin&lt;/artifactId>
      &lt;version>2.3&lt;/version>
      &lt;executions>
        &lt;execution>
          &lt;phase>package&lt;/phase>
          &lt;goals>
            &lt;goal>shade&lt;/goal>
          &lt;/goals>
          &lt;configuration>
            &lt;transformers>
              &lt;transformer implementation="org.apache.maven.plugins.shade.resource.ManifestResourceTransformer">
               &lt;mainClass>MyJavaConsoleApp.App&lt;/mainClass>
              &lt;/transformer>
            &lt;/transformers&gt;
          &lt;/configuration&gt;
        &lt;/execution&gt;
      &lt;/executions&gt;
    &lt;/plugin&gt;
  &lt;/plugins&gt;
&lt;/build&gt;
</pre>

To build: mvn install
To run: java -jar target\MyJavaConsoleApp-1.0-SNAPSHOT.jar

 - Main class with main method
 - Arguments
 - Spring
 - Injecting arguments into spring context
 - Packaging a 'uber jar' using shaded plugin.
 - Running via java.exe
