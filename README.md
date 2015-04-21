# How to make and package a Java Console Applications

## Create console app

Create you basic console application with a main methos somewhere. You can use this mvn archetype if you like.

<pre class='prettyprint linenums'>
mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=5-SNAPSHOT
</pre>

## Package and add a manifest

You need to add the following shaded plugin to the maven pom.xml. This packages all the dependanct .jar's into an 'uber' jar that 
be distributed on it's own as your applicaiton.

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

## Build

<pre class='prettyprint linenums'>mvn install</pre>

## To run

Make sure you are in the folder with the .jar file and run:

<pre class='prettyprint linenums'>java -jar MyJavaConsoleApp-1.0-SNAPSHOT.jar</pre>

 
## To do

<ul>
	<li>Arguments</li>
	<li>Spring</li>
	<li>Injecting arguments into spring context</li>
	<li>Running via java.exe</li>
</ul>

 
