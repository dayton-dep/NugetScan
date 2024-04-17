# NugetScan
Nuget Vulnerability Scanner lightweight CLI tool

This CLI tool is used in conjuntion with `dotnet restore` or `nuget restore`, and allows you to properly identify and ignore vulnerabilities found within your .NET project.

## How to run this tool

After installation, this tool can be run as follows:

`nugetscan <solution file.sln> <source directory>`

This will run `nuget restore` on the provided solution. 

To force the tool to run `dotnet restore`, simply add the `--useDotNet` flag.

### Ignoring vulnerabilities

Vulnerabilities can be ignored by creating a file called `nugetconfig.json` at the root of your source directory. The json file is structured as follows:

```
{
    "vulnerabilities": [
        {    
            "url": Github advisory URL as string,
            "expiry": Date in YYYY-MM-DD format,
            "statement": This is an optional property that allows for a comment on the vulnerability.
        },
        ...
    ]
}

```