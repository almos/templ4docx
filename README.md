# templ4docx - Utility library for filling templates in docx files.

The heart of this library is `apache-poi`

Thanks to `templ4docx` you can read the entire content (as simple String) of docx file, you can find all variables, register variables pattern and you can fill docx template file by your own map of variables.

The recommended way to get started using templ4docx in your project is a dependency management system – the snippet below can be copied and pasted into your build.

## For Maven

**Step 1.** Add the JitPack repository to your build file. Add it in your root build.gradle at the end of repositories:

```
<repositories>
	<repository>
		<id>jitpack.io</id>
		<url>https://jitpack.io</url>
	</repository>
</repositories>
```

**Step 2.** Add the dependency

```
<dependency>
	<groupId>com.github.youngyou</groupId>
	<artifactId>templ4docx</artifactId>
	<version>v2.1.0</version>
</dependency>
```

## For Gradle

**Step 1.** Add the JitPack repository to your build file. Add it in your root build.gradle at the end of repositories:

```
allprojects {
	repositories {
		...
		maven { url 'https://jitpack.io' }
	}
}
```

**Step 2.** Add the dependency

```
dependencies {
	implementation 'com.github.youngyou:templ4docx:v2.1.0'
}
```

## Example usage

```
Docx docx = new Docx("template.docx");
docx.setVariablePattern(new VariablePattern("#{", "}"));

// preparing variables
Variables variables = new Variables();
variables.addTextVariable(new TextVariable("#{firstname}", "Lukasz"));
variables.addTextVariable(new TextVariable("#{lastname}", "Stypka"));

// fill template
docx.fillTemplate(variables);

// save filled .docx file
docx.save("lstypka.docx");
```

More details:

- [Text Variables](http://jsolve.github.io/java/templ4docx-2-0-0-text-variables/) <br />
- [Image Variables](http://jsolve.github.io/java/templ4docx-2-0-0-text-variables/) <br />
- [Bullet List Variables](http://jsolve.github.io/java/templ4docx-2-0-0-text-variables/) <br />
- [Table Variables](http://jsolve.github.io/java/templ4docx-2-0-0-text-variables/) <br />
