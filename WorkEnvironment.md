# Getting Started with VScode

---

## Install VScode
Install Visual Studio Code by visiting the link : https://code.visualstudio.com/ or by typing "Visual Studio Code" into your web browser, it should be one of the first links.

## Install C# Extension
Once inside of the Visual Studio Code editor, it is beneficial to install the "C#" extension by clicking on the Extensions tab on the left. The extension is literally called "C#" and will be one of the first that is recommended.

For easier nagivation to the Extensions tab on the left use the hotkey : *Ctrl + Shift + X*

## Install vscode-solution-explorer Extension
Navigate to the same tab where you installed the "C#" extension, but this type search "vscode-solution-explorer" and install.

## Install C# SDK
Finally it is time for the C# SDK, you can nagivate to this link : https://dotnet.microsoft.com/download or type ".NET Core" in your web browser. Once at the Microsoft page, download and install the ".NET Core SDK".


## Setting Environment Variables
*Note : This is always a item to check on incase Windows does not set a path to the .NET Core.*

Navigate to your "Environment Variables" and edit the "Path" variable place a new path as "**C:\Program Files\dotnet**", this is the default path that .NET Core will be installed at.

*Note : unless you differed from the default install path, then use your custom path*

# Initializing a Project

---

## Creation of a Project
Now that you have the Visual Studio Code, the C# extension, solution extension, and the C# SDK installed you can finally create a project.

Create a directory in your windows file explorer and open that directory in VScode. Once open in VScode, a new tab on the left should pop up with the name "Solution", nagivate to that tab.

Once in the tab, there will be text saying *"No solution found (right click to create a new one)"* Right click to create a solution and give the solution a name, if prompted in the bottom right click "yes".

Right click on the solution and select "Add new project".
1. "Class Library" should be the project type (for .dll's)
2. "C#" should be the language
3. The project can be whatever practical and descriptive name you choose
4. Finally the project directory, it can be a practical and descriptive name of your choice

## Adding RimWorld and Unity References

*Note : The file paths to the .dll's may not be the same on your machine, use yours if you're not using the defaults.*

Once the project is populated with all the .vscode documents by clicking "yes" when creating the solution name, now you must reference the RimWorld files.

In the your_project_name.csproj place the XML nodes below in the ```<Project>``` node :

```
<ItemGroup>
	<Reference Include="Assembly-CSharp">
		<HintPath>C:\Program Files (x86)\Steam\steamapps\common\RimWorld\RimWorldWin64_Data\Managed\Assembly-CSharp.dll</HintPath>
	</Reference>
</ItemGroup>
```
and
```
<ItemGroup>
	<Reference Include="Assembly-CSharp">
		<HintPath>C:\Program Files (x86)\Steam\steamapps\common\RimWorld\RimWorldWin64_Data\Managed\UnityEngine.dll</HintPath>
	</Reference>
</ItemGroup>
```

So you have something like :

```
<Project Sdk="Microsoft.NET.Sdk">

	<PropertyGroup>
		<TargetFramework>netstandard2.0</TargetFramework>
		<RootNamespace>your_project_name</RootNamespace>
	</PropertyGroup>
	
	<ItemGroup>
		<Reference Include="Assembly-CSharp">
			<HintPath>C:\Program Files (x86)\Steam\steamapps\common\RimWorld\RimWorldWin64_Data\Managed\Assembly-CSharp.dll</HintPath>
		</Reference>
	</ItemGroup>
	
	<ItemGroup>
		<Reference Include="Assembly-CSharp">
			<HintPath>C:\Program Files (x86)\Steam\steamapps\common\RimWorld\RimWorldWin64_Data\Managed\UnityEngine.dll</HintPath>
		</Reference>
	</ItemGroup>
	
</Project>
```


## Conclusion
You may now reference RimWorld and UnityEngine in your C# file by the line at the top of your file.

```
using RimWorld;
using UnityEngine;
```

