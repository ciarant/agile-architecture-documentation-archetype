<h1 align="center">Welcome to Agile architecture documentation archetype 👋</h1>
<p>
  <a href="https://twitter.com/Riduidel" target="_blank">
    <img alt="Twitter: Riduidel" src="https://img.shields.io/twitter/follow/Riduidel.svg?style=social" />
  </a>
</p>

> A Maven archetype allowing you to easily create your agile architecture documentation using a mix of C4, Asciidoc and PlantUML

## Install

Since I use Jitpack for easy deployment of that archetype, and [maven requires archetypes to be defined in settings.xml](http://maven.apache.org/archetype/maven-archetype-plugin/archetype-repository.html), you first have to define a jitpack profile in your settings.xml this way

```xml
		<profile>
			<id>jitpack</id>
			<repositories>
				<repository>
					<id>archetype</id><!-- id expected by maven-archetype-plugin to avoid 
						fetching from everywhere -->
					<url>https://jitpack.io</url>
					<releases>
						<enabled>true</enabled>
						<checksumPolicy>fail</checksumPolicy>
					</releases>
					<snapshots>
						<enabled>true</enabled>
						<checksumPolicy>warn</checksumPolicy>
					</snapshots>
				</repository>
			</repositories>
		</profile>
```

Then, you can use the archetype by running this maven-friendly 😅command.

```sh
mvn archetype:generate -DarchetypeVersion=master-SNAPSHOT -DarchetypeRepository=https://jitpack.io -DarchetypeGroupId=com.github.Riduidel -DarchetypeArtifactId=agile-architecture-documentation-archetype -Pjitpack
```

This will ask you a few questions and generate the project.

## Usage

Once the archetype has been run, you'll have a project with Structurizr compatible source in `src/main/java`
and asciidoc files following Agile architecture documentation template in `src/docs/asciidoc`.

Running `mvn install` will 

1. compile and run Java code to have C4 model-compatible diagrams generated by PlantUML
1. generate AsciiDoc HTML and PDF files

Running `mvn fizzed-watcher:run` will start the fizzed-watcher plugin, which observes changes in source folders and regenrates output at need. This is particularly handy when working on project.

## Author

👤 **Nicolas Delsaux**

* Twitter: [@Riduidel](https://twitter.com/Riduidel)
* Github: [@Riduidel](https://github.com/Riduidel)

## 🤝 Contributing

Contributions, issues and feature requests are welcome!<br />Feel free to check [issues page](https://github.com/Riduidel/agile-architecture-documentation-archetype/issues).

## Show your support

Give a ⭐️ if this project helped you!

***
_This README was generated with ❤️ by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_