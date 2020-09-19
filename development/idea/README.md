# IntelliJ IDEA tips
## Plugins must have:<br/>
1. Generate UUID (after install, class needs to implement Serializable interface and then right click "Generate..." --> SerialVersionUID):<br/>
* https://plugins.jetbrains.com/plugin/8320-uuid-generator<br/>
2. Sonarqube:<br/>
* https://www.sonarlint.org/intellij/index.html<br/>
3. Checkstyle:<br/>
*  https://plugins.jetbrains.com/plugin/1065-checkstyle-idea<br/>

<br/>
<br/>
## Usage tips:<br/>
Show "problems"-panel (requires: https://i.stack.imgur.com/HtBFh.png):<br/>
https://i.stack.imgur.com/Dsl3e.png<br/>
<br/>
## StackOverflow tips:<br/>
* https://stackoverflow.com/questions/9030986/intellij-is-it-possible-to-add-overrrides-to-all-methods-of-a-particular-interf<br/>
<br/>
## Spring devtools:<br/>
<p>
https://www.metakoder.com/blog/spring-boot-devtools-on-intellij

1. Add Spring DevTools dependency to pom.xml:
<dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-devtools</artifactId>
   <scope>runtime</scope>
</dependency>
2. Changes in IntelliJ build configuration
Go to Preference -> build,execution,deployment. -> Compiler and Enable build project automatically.
3. Changes in IntelliJ registory
   Go to Cmd+Shift +A (Mac) or Ctrl+ Shift+A (Windows) -> Registry
   Enable compiler.automake.allow.when.app.running
<p>
