#
# This base image is to host dotnet core asp apps on servercore images 
# to better support things like GDI+ image manipulation or COM
#

FROM  mcr.microsoft.com/windows/servercore:1803
SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]

WORKDIR /app
RUN iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1')); \
	choco install dotnetcore-runtime --version 2.2.7 -y; \
	choco install aspnetcore-runtimepackagestore --version 2.2.7 -y

ENV ASPNETCORE_URLS http://*:80
EXPOSE 80
