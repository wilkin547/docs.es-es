---
title: Información general sobre la generación de certificados autofirmados
description: Información general de la herramienta dotnet dev-certs de Microsoft que agrega funcionalidad para proyectos de .NET Core y ASP.NET Core, y otras opciones para usar certificados autofirmados.
author: angee
ms.date: 11/19/2020
ms.openlocfilehash: 738af3fc091e415399a53015a40748ad6116a2b4
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104873021"
---
# <a name="generate-self-signed-certificates-with-the-net-cli"></a>Generación de certificados autofirmados con la CLI de .NET

Cuando se usan certificados autofirmados, hay diferentes maneras de crearlos y usarlos en escenarios de desarrollo y pruebas.  En esta guía, se describirá el uso de certificados autofirmados con `dotnet dev-certs` y otras opciones, como `PowerShell` y `OpenSSL`.

Después, puede validar que el certificado se cargará mediante un ejemplo como una [aplicación ASP.NET Core](https://github.com/dotnet/dotnet-docker/blob/main/samples/run-aspnetcore-https-development.md) hospedada en un contenedor.

## <a name="prerequisites"></a>Requisitos previos

En el ejemplo, puede usar .NET Core 3.1 o .NET 5.

Para `dotnet dev-certs`, asegúrese de que tiene instalada la versión adecuada de .NET:

* [Instalación de .NET en Windows](../install/windows.md)
* [Instalación de .NET en Linux](../install/linux.md)
* [Instalación de .NET en macOS](../install/macos.md)

En este ejemplo se necesita la versión [Docker 17.06](https://docs.docker.com/release-notes/docker-ce) o posterior del [cliente Docker](https://www.docker.com/products/docker).

## <a name="prepare-sample-app"></a>Preparación de la aplicación de ejemplo

Tendrá que preparar la aplicación de ejemplo en función del entorno de ejecución que quiera usar para las pruebas, ya sea [.NET Core 3.1](#net-core-31-sample-app) o [.NET 5](#net-5-sample-app).

En esta guía, usará una [aplicación de ejemplo](https://hub.docker.com/_/microsoft-dotnet-samples) y realizará los cambios necesarios.

### <a name="net-core-31-sample-app"></a>Aplicación de ejemplo para .NET Core 3.1

Obtener la aplicación de ejemplo.

```console
git clone https://github.com/dotnet/dotnet-docker/
```

Navegue al repositorio de forma local y abra el área de trabajo en un editor.

> [!NOTE]
> Si quiere usar parámetros de dotnet publish para *recortar* la implementación, tendrá que asegurarse de que se incluyan las dependencias adecuadas para admitir los certificados SSL.
Actualice [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/main/samples/aspnetapp/aspnetapp/aspnetapp.csproj) para asegurarse de que los ensamblados adecuados están incluidos en el contenedor. Como referencia, compruebe cómo actualizar el archivo .csproj para [admitir certificados SSL](../deploying/trim-self-contained.md#support-for-ssl-certificates) al usar el recorte para las implementaciones independientes.

Asegúrese de que `aspnetapp.csproj` incluye la plataforma de destino adecuada:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>.netcoreapp3.1</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

Modifique el Dockerfile para asegurarse de que el entorno de ejecución apunta a .NET Core 3.1:

```Dockerfile
# https://hub.docker.com/_/microsoft-dotnet-core
FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
WORKDIR /source

# copy csproj and restore as distinct layers
COPY *.sln .
COPY aspnetapp/*.csproj ./aspnetapp/
RUN dotnet restore

# copy everything else and build app
COPY aspnetapp/. ./aspnetapp/
WORKDIR /source/aspnetapp
RUN dotnet publish -c release -o /app --no-restore

# final stage/image
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
WORKDIR /app
COPY --from=build /app ./
ENTRYPOINT ["dotnet", "aspnetapp.dll"]
```

Asegúrese de que apunta a la aplicación de ejemplo.

```console
cd .\dotnet-docker\samples\aspnetapp
```

Cree el contenedor para realizar las pruebas localmente.

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

### <a name="net-5-sample-app"></a>Aplicación de ejemplo de .NET 5

En esta guía, se debe comprobar .NET 5 en [el archivo aspnetapp de ejemplo](https://hub.docker.com/_/microsoft-dotnet-samples).

Compruebe que en el [Dockerfile](https://github.com/dotnet/dotnet-docker/blob/main/samples/aspnetapp/Dockerfile) de la aplicación de ejemplo se usa .NET 5.

En función del sistema operativo del host, es posible que sea necesario actualizar el entorno de ejecución de ASP.NET. Por ejemplo, el cambio de `mcr.microsoft.com/dotnet/aspnet:5.0-nanoservercore-2009 AS runtime` a `mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime` en el Dockerfile ayudará a establecer como destino el entorno de ejecución de Windows adecuado.

Por ejemplo, esto ayudará a probar los certificados en Windows:

```Dockerfile
# https://hub.docker.com/_/microsoft-dotnet
FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /source

# copy csproj and restore as distinct layers
COPY *.sln .
COPY aspnetapp/*.csproj ./aspnetapp/
RUN dotnet restore -r win-x64

# copy everything else and build app
COPY aspnetapp/. ./aspnetapp/
WORKDIR /source/aspnetapp
RUN dotnet publish -c release -o /app -r win-x64 --self-contained false --no-restore

# final stage/image
# Uses the 2009 release; 2004, 1909, and 1809 are other choices
FROM mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime
WORKDIR /app
COPY --from=build /app ./
ENTRYPOINT ["aspnetapp"]

```

Si se van a probar los certificados en Linux, puede usar el Dockerfile existente.

Asegúrese de que `aspnetapp.csproj` incluye la plataforma de destino adecuada:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

> [!NOTE]
> Si quiere usar parámetros `dotnet publish` para *recortar* la implementación, asegúrese de que se incluyan las dependencias adecuadas para admitir los certificados SSL.
Actualice [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/main/samples/aspnetapp/aspnetapp/aspnetapp.csproj) para asegurarse de que los ensamblados adecuados están incluidos en el contenedor. Como referencia, compruebe cómo actualizar el archivo .csproj para [admitir certificados SSL](../deploying/trim-self-contained.md#support-for-ssl-certificates) al usar el recorte para las implementaciones independientes.

Asegúrese de que apunta a la aplicación de ejemplo.

```console
cd .\dotnet-docker\samples\aspnetapp
```

Cree el contenedor para realizar las pruebas localmente.

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

## <a name="create-a-self-signed-certificate"></a>Creación de un certificado autofirmado

Puede crear un certificado autofirmado:

- [Con dotnet dev-certs](#with-dotnet-dev-certs)
- [Con PowerShell](#with-powershell)
- [Con OpenSSL](#with-openssl)

### <a name="with-dotnet-dev-certs"></a>Con dotnet dev-certs

Puede usar `dotnet dev-certs` para trabajar con certificados autofirmados. En este ejemplo se usa una consola de PowerShell.

```console
dotnet dev-certs https -ep $env:USERPROFILE\.aspnet\https\aspnetapp.pfx -p crypticpassword
dotnet dev-certs https --trust
```

> [!NOTE]
> El nombre del certificado, en este caso *aspnetapp*.pfx debe coincidir con el nombre del ensamblado del proyecto. `crypticpassword` se usa como sustituto de una contraseña que elija. Si la consola devuelve "Ya hay un certificado HTTPS válido.", ya existe un certificado de confianza en el almacén. Se puede exportar mediante la consola de MMC.

Configure los secretos de la aplicación para el certificado:

```console
dotnet user-secrets -p aspnetapp\aspnetapp.csproj set "Kestrel:Certificates:Development:Password" "crypticpassword"
```

> [!NOTE]
> Nota: La contraseña debe coincidir con la contraseña usada para el certificado.

Ejecute la imagen de contenedor con ASP.NET Core configurado para HTTPS:

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -v $env:APPDATA\microsoft\UserSecrets\:C:\Users\ContainerUser\AppData\Roaming\microsoft\UserSecrets -v $env:USERPROFILE\.aspnet\https:C:\Users\ContainerUser\AppData\Roaming\ASP.NET\Https mcr.microsoft.com/dotnet/samples:aspnetapp
```

Una vez que se inicie la aplicación, vaya a `https://localhost:8001` en el explorador web.

#### <a name="clean-up"></a>Limpieza

Si los secretos y certificados no están en uso, asegúrese de limpiarlos.

```console
dotnet user-secrets remove "Kestrel:Certificates:Development:Password" -p aspnetapp\aspnetapp.csproj
dotnet dev-certs https --clean
```

### <a name="with-powershell"></a>Con PowerShell

Puede usar PowerShell para generar certificados autofirmados. El [cliente PKI](/powershell/module/pkiclient/new-selfsignedcertificate?preserve-view=true&view=win10-ps) se puede usar para generar un certificado autofirmado.

```powershell
$cert = New-SelfSignedCertificate -DnsName @("contoso.com", "www.contoso.com") -CertStoreLocation "cert:\LocalMachine\My"
```

El certificado se generará, pero se debe colocar en un almacén de certificados para realizar las pruebas en un explorador.

```powershell
$certKeyPath = "c:\certs\contoso.com.pfx"
$password = ConvertTo-SecureString 'password' -AsPlainText -Force
$cert | Export-PfxCertificate -FilePath $certKeyPath -Password $password
$rootCert = $(Import-PfxCertificate -FilePath $certKeyPath -CertStoreLocation 'Cert:\LocalMachine\Root' -Password $password)
```

En este momento, los certificados deben ser visibles desde un [complemento MMC](../../framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).

Puede ejecutar el contenedor de ejemplo en el Subsistema de Windows para Linux (WSL):

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> Tenga en cuenta que, con el montaje del volumen, la ruta de acceso del archivo se podría controlar de otra manera en función del host.  Por ejemplo, en WSL se podría reemplazar */c/certs* por */mnt/c/certs*.

Si usa el contenedor compilado anteriormente para Windows, el comando run tendría el siguiente aspecto:

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

Una vez que la aplicación esté activa, vaya a contoso.com:8001 en un explorador.

Asegúrese de que las entradas del host se actualizan para que `contoso.com` responda en la dirección IP adecuada (por ejemplo, 127.0.0.1). Si no se reconoce el certificado, asegúrese de que el certificado que se carga con el contenedor también sea de confianza en el host y de que existan entradas SAN/DNS adecuadas para `contoso.com`.

#### <a name="clean-up"></a>Limpieza

```powershell
$cert | Remove-Item
Get-ChildItem $certFilePath | Remove-Item
$rootCert | Remove-item
```

### <a name="with-openssl"></a>Con OpenSSL

Puede usar [OpenSSL](https://www.openssl.org/) para crear certificados autofirmados. En este ejemplo se usará WSL / Ubuntu y un shell de bash con `OpenSSL`.

Esto generará un archivo .crt y otro .key.

```bash
PARENT="contoso.com"
openssl req \
-x509 \
-newkey rsa:4096 \
-sha256 \
-days 365 \
-nodes \
-keyout $PARENT.key \
-out $PARENT.crt \
-subj "/CN=${PARENT}" \
-extensions v3_ca \
-extensions v3_req \
-config <( \
  echo '[req]'; \
  echo 'default_bits= 4096'; \
  echo 'distinguished_name=req'; \
  echo 'x509_extension = v3_ca'; \
  echo 'req_extensions = v3_req'; \
  echo '[v3_req]'; \
  echo 'basicConstraints = CA:FALSE'; \
  echo 'keyUsage = nonRepudiation, digitalSignature, keyEncipherment'; \
  echo 'subjectAltName = @alt_names'; \
  echo '[ alt_names ]'; \
  echo "DNS.1 = www.${PARENT}"; \
  echo "DNS.2 = ${PARENT}"; \
  echo '[ v3_ca ]'; \
  echo 'subjectKeyIdentifier=hash'; \
  echo 'authorityKeyIdentifier=keyid:always,issuer'; \
  echo 'basicConstraints = critical, CA:TRUE, pathlen:0'; \
  echo 'keyUsage = critical, cRLSign, keyCertSign'; \
  echo 'extendedKeyUsage = serverAuth, clientAuth')

openssl x509 -noout -text -in $PARENT.crt
```

Para obtener un archivo .pfx, use el comando siguiente:

```bash
openssl pkcs12 -export -out $PARENT.pfx -inkey $PARENT.key -in $PARENT.crt
```

> [!NOTE]
> En el ejemplo .aspnetcore 3.1 se usará `.pfx` y una contraseña. A partir del entorno de ejecución `.net 5`, Kestrel también puede tomar archivos `.crt` y `.key` con codificación PEM.

En función del sistema operativo del host, el certificado tendrá que ser de confianza. En un host de Linux, la "confianza" en el certificado es diferente y depende de la distribución.

Para los fines de esta guía, este es un ejemplo de Windows con PowerShell:

```powershell
Import-Certificate -FilePath $certFilePath -CertStoreLocation 'Cert:\LocalMachine\Root'
```

Para .NET Core 3.1, ejecute el comando siguiente en WSL:

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/path/to/certs/:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

A partir de .NET 5, Kestrel puede tomar los archivos `.crt` y `.key` con codificación PEM. Puede ejecutar el ejemplo con el comando siguiente para .NET 5:

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=/https/contoso.com.key -v /c/path/to/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> Tenga en cuenta que en WSL, la ruta de montaje del volumen puede cambiar en función de la configuración.

Para .NET Core 3.1 en Windows, ejecute el comando siguiente en `Powershell`:

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

Para .NET 5 en Windows, ejecute el comando siguiente en PowerShell:

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=c:\https\contoso.com.key -v c:\certs:C:\https aspnetapp:my-sample
```

Una vez que la aplicación esté activa, vaya a contoso.com:8001 en un explorador.

Asegúrese de que las entradas del host se actualizan para que `contoso.com` responda en la dirección IP adecuada (por ejemplo, 127.0.0.1). Si no se reconoce el certificado, asegúrese de que el certificado que se carga con el contenedor también sea de confianza en el host y de que existan entradas SAN/DNS adecuadas para `contoso.com`.

#### <a name="clean-up"></a>Limpieza

Asegúrese de limpiar los certificados autofirmados una vez que se hayan realizado las pruebas.

```powershell
Get-ChildItem $certFilePath | Remove-Item
```
