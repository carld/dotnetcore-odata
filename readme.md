
# Developing an OData Service using Visual Studio Code and the dotnet CLI

The objective of this project was to implement an OData service equivalent of the "Hello, World!" program. That is, a minimal example of an OData service using the widely available Visual Studio Code and DotNet Core tools on a Macbook.

## Development Environment

| Tool | Version |
|------|---------|
| Visual Studio Code | 1.58.1 |
| dotnet cli | .NET SDK (5.0.202) |
| macOS Catalina | 10.15.7 |

## References

Most usefully, the OData github profile provides sample applications that can be found under the sample folder here:

https://github.com/OData/AspNetCoreOData

In fact the Newtonsoft JSON example offers the desired outcome with the addition of the that JSON framework.

## Method

Using the dotnet CLI tool, create a new webapi project. Before running the command, create a directory 
for this project because running the command below as it was created the files in the current directory.

	mkdir odata-service
	cd odata-service

Now create the files for a web API service using the dotnet CLI.

	dotnet new webapi

To run the web service,

	dotnet run

To add the OData package for Asp .Net core to the project:

	dotnet add package Microsoft.AspNetCore.OData

In addition, the following packages were also required to provide the model builder,
and the entity data model.

	dotnet add package Microsoft.OData.ModelBuilder
	dotnet add package Microsoft.OData.Edm


## Try It Out

At a terminal, start the service:

	dotnet run

In a web browser, view the OData endpoints by visiting https://localhost:5001/$odata

Try an OData query, https://localhost:5001/odata/WeatherForecast?$select=TemperatureC


