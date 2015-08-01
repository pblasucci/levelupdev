- title : Level Up Your Library Development
- description : Use Project Scaffold to go from zero to professional-grade library in a matter of minutes.
- author : Paulmichael Blasucci
- theme : Blood
- transition : slide

***

<hr/>

### Level Up Your
### Library Development

<hr/>

<div class="subhead">From zero to professional-grade library in a matter of minutes with Project Scaffold</div>

---

### Paulmichael Blasucci

Senior Software Engineer

![QuickenLoans](images/QL.png)

github.com [/pblasucci](http://github.com/pblasucci)

twitter.com [/pblasucci](http://twitter.com/pblasucci)

***

#### Project Scaffold

---------------------------------------------------------------|---------------------------
[Paket](http://fsprojects.github.io/Paket/)                    | _dependency management_
[F# Formatting](http://tpetricek.github.io/FSharp.Formatting/) | _literate documentation_
[FAKE](http://fsharp.github.io/FAKE/)                          | _build management_

' <ul>
' <li>Recommended directory structure and collection of libraries</li>
' <li>Powered by two F# scripts (build.fsx and generate.fsx)</li>
' <li>Includes 1st-run wizard to help get things sorted</li>
' </ul>

---

#### Paket

  	source https://nuget.org/api/v2

  	// NuGet packages
  	nuget NUnit ~> 2.6.3
  	nuget FAKE ~> 3.4
  	nuget DotNetZip >= 1.9
  	nuget SourceLink.Fake

  	// Files from GitHub repositories
  	github forki/FsUnit FsUnit.fs

  	// Gist files
  	gist Thorium/1972349 timestamp.fs

  	// HTTP resources
  	http http://www.fssnip.net/1n decrypt.fs

' <ul>
' <li>"NuGet does not separate out the concept of transitive dependencies..."</li>
' <li>"If two packages reference conflicting versions of a package, NuGet will silently take the latest version..."</li>
' <li>"Paket on the other hand... enables you to determine exactly what's happening with your dependencies."</li>
' <li>"Paket also enables one to reference files directly from GitHub repositories, Gists and HTTP."</li>
' </ul>

---

#### FSharp.Formatting

    # First-level heading

      [hide]
      let print s = printfn "%s" s

    Some more documentation using `Markdown`.

      [module=Hello]
      let helloWorld() = print "Hello world!"

    ## Second-level heading
    With some more documentation

      [lang=csharp]
      var name = Console.ReadLine();
      Console.WriteLine("Hello, {0}!", name);

' <ul>
' <li>Literate programming - generate narrative documentation</li>
' <li>Embed results of a literate script file in the generated output</li>
' <li>Generates nice HTML documentation from "XML comments" in your (not just) F# libraries</li>
' <li>Basis for more sophisticated tools (e.g. FsBlob, FsReveal)</li>
' </ul>

---

#### FAKE - F# Make

  	#r "tools/FAKE/tools/FakeLib.dll" // include Fake lib
  	open Fake


  	Target "Test" (fun _ ->
  	    trace "Testing stuff..."
  	)

  	Target "Deploy" (fun _ ->
  	    trace "Heavy deploy action"
  	)

  	"Test"            // define the dependencies
  	   ==> "Deploy"

  	Run "Deploy"

' <ul>
' <li>Targets, the main unit of work, have a name and an action (given as an F# code block)</li>
' <li>Filesets = similar include and exclude patterns as NAnt and MSBuild</li>
' <li>Includes dozens of dozens of "helpers" (collections of utility functions): assembly info, et cetera</li>
' </ul>

---

#### Also "in the box"

+ Track changes with the [Release Notes Helper](http://fsharp.github.io/FAKE/apidocs/fake-releasenoteshelper.html)
+ Hooked into [GitHub](http://github.com/) for project hosting
+ [NUnit](http://www.nunit.org/) configured for unit-test execution
+ Source-linking enabled via [SourceLink](http://ctaggart.github.io/SourceLink/)
+ Ready for CI servers ([Travis](https://travis-ci.org/), [AppVeyor](http://www.appveyor.com/))

***

### Walkthrough

***

### More Information

+ [fsharp.org](http://fsharp.org)

+ [github.com/fsprojects/ProjectScaffold](http://github.com/fsprojects/ProjectScaffold)

+ [fsprojects.github.io/Paket](http://fsprojects.github.io/Paket)
+ [tpetricek.github.io/FSharp.Formatting](http://tpetricek.github.io/FSharp.Formatting)
+ [fsharp.github.io/FAKE](http://fsharp.github.io/FAKE)
