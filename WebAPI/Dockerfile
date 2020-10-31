# escape=`
FROM microsoft/windows-2019-for-containers AS builder
WORKDIR C:\src\3-Tier-App\WebAPI\
COPY . .
RUN msbuild WebAPI.sln /p:OutputPath=c:\out

# app image
FROM microsoft/dotnet-framework:4.6.2-windowsservercore-10.0.14393.1884
WORKDIR C:\hello-world
COPY --from=builder C:\out .
#CMD HelloWorld.Console.exe
