---
title: Información general sobre la generación de certificados autofirmados
description: Información general de la herramienta dotnet dev-certs de Microsoft que agrega funcionalidad para proyectos de .NET Core y ASP.NET Core, y otras opciones para usar certificados autofirmados.
author: angee
ms.date: 11/19/2020
ms.openlocfilehash: b5bf4b719495c2d6ec248e8592367ac452be91c1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032182"
---
# <a name="generate-self-signed-certificates-with-the-net-cli"></a><span data-ttu-id="31579-103">Generación de certificados autofirmados con la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="31579-103">Generate self-signed certificates with the .NET CLI</span></span>

<span data-ttu-id="31579-104">Cuando se usan certificados autofirmados, hay diferentes maneras de crearlos y usarlos en escenarios de desarrollo y pruebas.</span><span class="sxs-lookup"><span data-stu-id="31579-104">When using self-signed certificates, there are different ways to create and use them for development and testing scenarios.</span></span>  <span data-ttu-id="31579-105">En esta guía, se describirá el uso de certificados autofirmados con `dotnet dev-certs` y otras opciones, como `PowerShell` y `OpenSSL`.</span><span class="sxs-lookup"><span data-stu-id="31579-105">In this guide, you'll cover using self-signed certificates with `dotnet dev-certs`, and other options like `PowerShell` and `OpenSSL`.</span></span>

<span data-ttu-id="31579-106">Después, puede validar que el certificado se cargará mediante un ejemplo como una [aplicación ASP.NET Core](https://github.com/dotnet/dotnet-docker/blob/master/samples/run-aspnetcore-https-development.md) hospedada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="31579-106">You can then validate that the certificate will load using an example such as an [ASP.NET Core app](https://github.com/dotnet/dotnet-docker/blob/master/samples/run-aspnetcore-https-development.md) hosted in a container.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="31579-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="31579-107">Prerequisites</span></span>

<span data-ttu-id="31579-108">En el ejemplo, puede usar .NET Core 3.1 o .NET 5.</span><span class="sxs-lookup"><span data-stu-id="31579-108">In the sample, you can utilize either .NET Core 3.1 or .NET 5.</span></span>

<span data-ttu-id="31579-109">Para `dotnet dev-certs`, asegúrese de que tiene instalada la versión adecuada de .NET:</span><span class="sxs-lookup"><span data-stu-id="31579-109">For `dotnet dev-certs`, be sure to have the appropriate version of .NET installed:</span></span>

* [<span data-ttu-id="31579-110">Instalación de .NET en Windows</span><span class="sxs-lookup"><span data-stu-id="31579-110">Install .NET on Windows</span></span>](../install/windows.md)
* [<span data-ttu-id="31579-111">Instalación de .NET en Linux</span><span class="sxs-lookup"><span data-stu-id="31579-111">Install .NET on Linux</span></span>](../install/linux.md)
* [<span data-ttu-id="31579-112">Instalación de .NET en macOS</span><span class="sxs-lookup"><span data-stu-id="31579-112">Install .NET on macOS</span></span>](../install/macos.md)

<span data-ttu-id="31579-113">En este ejemplo se necesita la versión [Docker 17.06](https://docs.docker.com/release-notes/docker-ce) o posterior del [cliente Docker](https://www.docker.com/products/docker).</span><span class="sxs-lookup"><span data-stu-id="31579-113">This sample requires [Docker 17.06](https://docs.docker.com/release-notes/docker-ce) or later of the [Docker client](https://www.docker.com/products/docker).</span></span>

## <a name="prepare-sample-app"></a><span data-ttu-id="31579-114">Preparación de la aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="31579-114">Prepare sample app</span></span>

<span data-ttu-id="31579-115">Tendrá que preparar la aplicación de ejemplo en función del entorno de ejecución que quiera usar para las pruebas, ya sea [.NET Core 3.1](#net-core-31-sample-app) o [.NET 5](#net-5-sample-app).</span><span class="sxs-lookup"><span data-stu-id="31579-115">You'll need to prepare the sample app depending on which runtime you'd like to use for testing, either [.NET Core 3.1](#net-core-31-sample-app) or [.NET 5](#net-5-sample-app).</span></span>

<span data-ttu-id="31579-116">En esta guía, usará una [aplicación de ejemplo](https://hub.docker.com/_/microsoft-dotnet-samples) y realizará los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="31579-116">For this guide, you'll use a [sample app](https://hub.docker.com/_/microsoft-dotnet-samples) and make changes where appropriate.</span></span>

### <a name="net-core-31-sample-app"></a><span data-ttu-id="31579-117">Aplicación de ejemplo para .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="31579-117">.NET Core 3.1 sample app</span></span>

<span data-ttu-id="31579-118">Obtener la aplicación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="31579-118">Get the sample app.</span></span>

```console
git clone https://github.com/dotnet/dotnet-docker/
```

<span data-ttu-id="31579-119">Navegue al repositorio de forma local y abra el área de trabajo en un editor.</span><span class="sxs-lookup"><span data-stu-id="31579-119">Navigate to the repository locally and open up the workspace in an editor.</span></span>

> [!NOTE]
> <span data-ttu-id="31579-120">Si quiere usar parámetros de dotnet publish para *recortar* la implementación, tendrá que asegurarse de que se incluyan las dependencias adecuadas para admitir los certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="31579-120">If you're looking to use dotnet publish parameters to *trim* the deployment, you should make sure that the appropriate dependencies are included for supporting SSL certificates.</span></span>
<span data-ttu-id="31579-121">Actualice [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) para asegurarse de que los ensamblados adecuados están incluidos en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="31579-121">Update the [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) to ensure that the appropriate assemblies are included in the container.</span></span> <span data-ttu-id="31579-122">Como referencia, compruebe cómo actualizar el archivo .csproj para [admitir certificados SSL](../deploying/trim-self-contained.md#support-for-ssl-certificates) al usar el recorte para las implementaciones independientes.</span><span class="sxs-lookup"><span data-stu-id="31579-122">For reference, check how to update the .csproj file to [support ssl certificates](../deploying/trim-self-contained.md#support-for-ssl-certificates) when using trimming for self-contained deployments.</span></span>

<span data-ttu-id="31579-123">Asegúrese de que `aspnetapp.csproj` incluye la plataforma de destino adecuada:</span><span class="sxs-lookup"><span data-stu-id="31579-123">Make sure the `aspnetapp.csproj` includes the appropriate target framework:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>.netcoreapp3.1</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

<span data-ttu-id="31579-124">Modifique el Dockerfile para asegurarse de que el entorno de ejecución apunta a .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="31579-124">Modify the Dockerfile to make sure the runtime points to .NET Core 3.1:</span></span>

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

<span data-ttu-id="31579-125">Asegúrese de que apunta a la aplicación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="31579-125">Make sure you're pointing to the sample app.</span></span>

```console
cd .\dotnet-docker\samples\aspnetapp
```

<span data-ttu-id="31579-126">Cree el contenedor para realizar las pruebas localmente.</span><span class="sxs-lookup"><span data-stu-id="31579-126">Build the container for testing locally.</span></span>

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

### <a name="net-5-sample-app"></a><span data-ttu-id="31579-127">Aplicación de ejemplo de .NET 5</span><span class="sxs-lookup"><span data-stu-id="31579-127">.NET 5 sample app</span></span>

<span data-ttu-id="31579-128">En esta guía, se debe comprobar .NET 5 en [el archivo aspnetapp de ejemplo](https://hub.docker.com/_/microsoft-dotnet-samples).</span><span class="sxs-lookup"><span data-stu-id="31579-128">For this guide, the [sample aspnetapp](https://hub.docker.com/_/microsoft-dotnet-samples) should be checked for .NET 5.</span></span>

<span data-ttu-id="31579-129">Compruebe que en el [Dockerfile](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile) de la aplicación de ejemplo se usa .NET 5.</span><span class="sxs-lookup"><span data-stu-id="31579-129">Check sample app [Dockerfile](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile) is using .NET 5.</span></span>

<span data-ttu-id="31579-130">En función del sistema operativo del host, es posible que sea necesario actualizar el entorno de ejecución de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="31579-130">Depending on the host OS, the ASP.NET runtime may need to be updated.</span></span> <span data-ttu-id="31579-131">Por ejemplo, el cambio de `mcr.microsoft.com/dotnet/aspnet:5.0-nanoservercore-2009 AS runtime` a `mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime` en el Dockerfile ayudará a establecer como destino el entorno de ejecución de Windows adecuado.</span><span class="sxs-lookup"><span data-stu-id="31579-131">For example, changing from `mcr.microsoft.com/dotnet/aspnet:5.0-nanoservercore-2009 AS runtime` to `mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime` in the Dockerfile will help with targeting the appropriate Windows runtime.</span></span>

<span data-ttu-id="31579-132">Por ejemplo, esto ayudará a probar los certificados en Windows:</span><span class="sxs-lookup"><span data-stu-id="31579-132">For example, this will help with testing the certificates on Windows:</span></span>

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

<span data-ttu-id="31579-133">Si se van a probar los certificados en Linux, puede usar el Dockerfile existente.</span><span class="sxs-lookup"><span data-stu-id="31579-133">If we're testing the certificates on Linux, you can use the existing Dockerfile.</span></span>

<span data-ttu-id="31579-134">Asegúrese de que `aspnetapp.csproj` incluye la plataforma de destino adecuada:</span><span class="sxs-lookup"><span data-stu-id="31579-134">Make sure the `aspnetapp.csproj` includes the appropriate target framework:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

> [!NOTE]
> <span data-ttu-id="31579-135">Si quiere usar parámetros `dotnet publish` para *recortar* la implementación, asegúrese de que se incluyan las dependencias adecuadas para admitir los certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="31579-135">If you want to use `dotnet publish` parameters to *trim* the deployment, make sure that the appropriate dependencies are included for supporting SSL certificates.</span></span>
<span data-ttu-id="31579-136">Actualice [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) para asegurarse de que los ensamblados adecuados están incluidos en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="31579-136">Update the [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) to ensure that the appropriate assemblies are included in the container.</span></span> <span data-ttu-id="31579-137">Como referencia, compruebe cómo actualizar el archivo .csproj para [admitir certificados SSL](../deploying/trim-self-contained.md#support-for-ssl-certificates) al usar el recorte para las implementaciones independientes.</span><span class="sxs-lookup"><span data-stu-id="31579-137">For reference, check how to update the .csproj file to [support ssl certificates](../deploying/trim-self-contained.md#support-for-ssl-certificates) when using trimming for self-contained deployments.</span></span>

<span data-ttu-id="31579-138">Asegúrese de que apunta a la aplicación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="31579-138">Make sure you're pointing to the sample app.</span></span>

```console
cd .\dotnet-docker\samples\aspnetapp
```

<span data-ttu-id="31579-139">Cree el contenedor para realizar las pruebas localmente.</span><span class="sxs-lookup"><span data-stu-id="31579-139">Build the container for testing locally.</span></span>

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="31579-140">Creación de un certificado autofirmado</span><span class="sxs-lookup"><span data-stu-id="31579-140">Create a self-signed certificate</span></span>

<span data-ttu-id="31579-141">Puede crear un certificado autofirmado:</span><span class="sxs-lookup"><span data-stu-id="31579-141">You can create a self-signed certificate:</span></span>

- [<span data-ttu-id="31579-142">Con dotnet dev-certs</span><span class="sxs-lookup"><span data-stu-id="31579-142">With dotnet dev-certs</span></span>](#with-dotnet-dev-certs)
- [<span data-ttu-id="31579-143">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="31579-143">With PowerShell</span></span>](#with-powershell)
- [<span data-ttu-id="31579-144">Con OpenSSL</span><span class="sxs-lookup"><span data-stu-id="31579-144">With OpenSSL</span></span>](#with-openssl)

### <a name="with-dotnet-dev-certs"></a><span data-ttu-id="31579-145">Con dotnet dev-certs</span><span class="sxs-lookup"><span data-stu-id="31579-145">With dotnet dev-certs</span></span>

<span data-ttu-id="31579-146">Puede usar `dotnet dev-certs` para trabajar con certificados autofirmados.</span><span class="sxs-lookup"><span data-stu-id="31579-146">You can use `dotnet dev-certs` to work with self-signed certificates.</span></span> <span data-ttu-id="31579-147">En este ejemplo se usa una consola de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31579-147">This example uses a PowerShell console.</span></span>

```console
dotnet dev-certs https -ep $env:USERPROFILE\.aspnet\https\aspnetapp.pfx -p crypticpassword
dotnet dev-certs https --trust
```

> [!NOTE]
> <span data-ttu-id="31579-148">El nombre del certificado, en este caso *aspnetapp*.pfx debe coincidir con el nombre del ensamblado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="31579-148">The certificate name, in this case *aspnetapp*.pfx must match the project assembly name.</span></span> <span data-ttu-id="31579-149">`crypticpassword` se usa como sustituto de una contraseña que elija.</span><span class="sxs-lookup"><span data-stu-id="31579-149">`crypticpassword` is used as a stand-in for a password of your own choosing.</span></span> <span data-ttu-id="31579-150">Si la consola devuelve "Ya hay un certificado HTTPS válido.", ya existe un certificado de confianza en el almacén.</span><span class="sxs-lookup"><span data-stu-id="31579-150">If console returns "A valid HTTPS certificate is already present.", a trusted certificate already exists in your store.</span></span> <span data-ttu-id="31579-151">Se puede exportar mediante la consola de MMC.</span><span class="sxs-lookup"><span data-stu-id="31579-151">It can be exported using MMC Console.</span></span>

<span data-ttu-id="31579-152">Configure los secretos de la aplicación para el certificado:</span><span class="sxs-lookup"><span data-stu-id="31579-152">Configure application secrets, for the certificate:</span></span>

```console
dotnet user-secrets -p aspnetapp\aspnetapp.csproj set "Kestrel:Certificates:Development:Password" "crypticpassword"
```

> [!NOTE]
> <span data-ttu-id="31579-153">Nota: La contraseña debe coincidir con la contraseña usada para el certificado.</span><span class="sxs-lookup"><span data-stu-id="31579-153">Note: The password must match the password used for the certificate.</span></span>

<span data-ttu-id="31579-154">Ejecute la imagen de contenedor con ASP.NET Core configurado para HTTPS:</span><span class="sxs-lookup"><span data-stu-id="31579-154">Run the container image with ASP.NET Core configured for HTTPS:</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -v $env:APPDATA\microsoft\UserSecrets\:C:\Users\ContainerUser\AppData\Roaming\microsoft\UserSecrets -v $env:USERPROFILE\.aspnet\https:C:\Users\ContainerUser\AppData\Roaming\ASP.NET\Https mcr.microsoft.com/dotnet/samples:aspnetapp
```

<span data-ttu-id="31579-155">Una vez que se inicie la aplicación, vaya a `https://localhost:8001` en el explorador web.</span><span class="sxs-lookup"><span data-stu-id="31579-155">Once the application starts, navigate to `https://localhost:8001` in your web browser.</span></span>

#### <a name="clean-up"></a><span data-ttu-id="31579-156">Limpieza</span><span class="sxs-lookup"><span data-stu-id="31579-156">Clean up</span></span>

<span data-ttu-id="31579-157">Si los secretos y certificados no están en uso, asegúrese de limpiarlos.</span><span class="sxs-lookup"><span data-stu-id="31579-157">If the secrets and certificates are not in use, be sure to clean them up.</span></span>

```console
dotnet user-secrets remove "Kestrel:Certificates:Development:Password" -p aspnetapp\aspnetapp.csproj
dotnet dev-certs https --clean
```

### <a name="with-powershell"></a><span data-ttu-id="31579-158">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="31579-158">With PowerShell</span></span>

<span data-ttu-id="31579-159">Puede usar PowerShell para generar certificados autofirmados.</span><span class="sxs-lookup"><span data-stu-id="31579-159">You can use PowerShell to generate self-signed certificates.</span></span> <span data-ttu-id="31579-160">El [cliente PKI](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps&preserver-view=true) se puede usar para generar un certificado autofirmado.</span><span class="sxs-lookup"><span data-stu-id="31579-160">The [PKI Client](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps&preserver-view=true) can be used to generate a self-signed certificate.</span></span>

```powershell
$cert = New-SelfSignedCertificate -DnsName @("contoso.com", "www.contoso.com") -CertStoreLocation "cert:\LocalMachine\My"
```

<span data-ttu-id="31579-161">El certificado se generará, pero se debe colocar en un almacén de certificados para realizar las pruebas en un explorador.</span><span class="sxs-lookup"><span data-stu-id="31579-161">The certificate will be generated, but for the purposes of testing, should be placed in a cert store for testing in a browser.</span></span>

```powershell
$certKeyPath = "c:\certs\contoso.com.pfx"
$password = ConvertTo-SecureString 'password' -AsPlainText -Force
$cert | Export-PfxCertificate -FilePath $certKeyPath -Password $password
$rootCert = $(Import-PfxCertificate -FilePath $certKeyPath -CertStoreLocation 'Cert:\LocalMachine\Root' -Password $password)
```

<span data-ttu-id="31579-162">En este momento, los certificados deben ser visibles desde un [complemento MMC](../../framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="31579-162">At this point, the certificates should be viewable from an [MMC snap-in](../../framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>

<span data-ttu-id="31579-163">Puede ejecutar el contenedor de ejemplo en el Subsistema de Windows para Linux (WSL):</span><span class="sxs-lookup"><span data-stu-id="31579-163">You can run the sample container in Windows Subsystem for Linux (WSL):</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> <span data-ttu-id="31579-164">Tenga en cuenta que, con el montaje del volumen, la ruta de acceso del archivo se podría controlar de otra manera en función del host.</span><span class="sxs-lookup"><span data-stu-id="31579-164">Note that with the volume mount the file path could be handled differently based on host.</span></span>  <span data-ttu-id="31579-165">Por ejemplo, en WSL se podría reemplazar */c/certs* por */mnt/c/certs*.</span><span class="sxs-lookup"><span data-stu-id="31579-165">For example, in WSL we may replace */c/certs* with */mnt/c/certs*.</span></span>

<span data-ttu-id="31579-166">Si usa el contenedor compilado anteriormente para Windows, el comando run tendría el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="31579-166">If you're using the container built earlier for Windows, the run command would look like the following:</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="31579-167">Una vez que la aplicación esté activa, vaya a contoso.com:8001 en un explorador.</span><span class="sxs-lookup"><span data-stu-id="31579-167">Once the application is up, navigate to contoso.com:8001 in a browser.</span></span>

<span data-ttu-id="31579-168">Asegúrese de que las entradas del host se actualizan para que `contoso.com` responda en la dirección IP adecuada (por ejemplo, 127.0.0.1).</span><span class="sxs-lookup"><span data-stu-id="31579-168">Be sure that the host entries are updated for `contoso.com` to answer on  the appropriate ip address (for example 127.0.0.1).</span></span> <span data-ttu-id="31579-169">Si no se reconoce el certificado, asegúrese de que el certificado que se carga con el contenedor también sea de confianza en el host y de que existan entradas SAN/DNS adecuadas para `contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="31579-169">If the certificate isn't recognized, make sure that the certificate that is loaded with the container is also trusted on the host, and that there's appropriate SAN / DNS entries for `contoso.com`.</span></span>

#### <a name="clean-up"></a><span data-ttu-id="31579-170">Limpieza</span><span class="sxs-lookup"><span data-stu-id="31579-170">Clean up</span></span>

```powershell
$cert | Remove-Item
Get-ChildItem $certFilePath | Remove-Item
$rootCert | Remove-item
```

### <a name="with-openssl"></a><span data-ttu-id="31579-171">Con OpenSSL</span><span class="sxs-lookup"><span data-stu-id="31579-171">With OpenSSL</span></span>

<span data-ttu-id="31579-172">Puede usar [OpenSSL](https://www.openssl.org/) para crear certificados autofirmados.</span><span class="sxs-lookup"><span data-stu-id="31579-172">You can use [OpenSSL](https://www.openssl.org/) to create self-signed certificates.</span></span> <span data-ttu-id="31579-173">En este ejemplo se usará WSL / Ubuntu y un shell de bash con `OpenSSL`.</span><span class="sxs-lookup"><span data-stu-id="31579-173">This example will use WSL / Ubuntu and a bash shell with `OpenSSL`.</span></span>

<span data-ttu-id="31579-174">Esto generará un archivo .crt y otro .key.</span><span class="sxs-lookup"><span data-stu-id="31579-174">This will generate a .crt and a .key.</span></span>

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

<span data-ttu-id="31579-175">Para obtener un archivo .pfx, use el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="31579-175">To get a .pfx, use the following command:</span></span>

```bash
openssl pkcs12 -export -out $PARENT.pfx -inkey $PARENT.key -in $PARENT.crt
```

> [!NOTE]
> <span data-ttu-id="31579-176">En el ejemplo .aspnetcore 3.1 se usará `.pfx` y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="31579-176">The .aspnetcore 3.1 example will use `.pfx` and a password.</span></span> <span data-ttu-id="31579-177">A partir del entorno de ejecución `.net 5`, Kestrel también puede tomar archivos `.crt` y `.key` con codificación PEM.</span><span class="sxs-lookup"><span data-stu-id="31579-177">Starting with the `.net 5` runtime, Kestrel can also take `.crt` and PEM-encoded `.key` files.</span></span>

<span data-ttu-id="31579-178">En función del sistema operativo del host, el certificado tendrá que ser de confianza.</span><span class="sxs-lookup"><span data-stu-id="31579-178">Depending on the host os, the certificate will need to be trusted.</span></span> <span data-ttu-id="31579-179">En un host de Linux, la "confianza" en el certificado es diferente y depende de la distribución.</span><span class="sxs-lookup"><span data-stu-id="31579-179">On a Linux host, 'trusting' the certificate is different and distro dependent.</span></span>

<span data-ttu-id="31579-180">Para los fines de esta guía, este es un ejemplo de Windows con PowerShell:</span><span class="sxs-lookup"><span data-stu-id="31579-180">For the purposes of this guide, here's an example in Windows using PowerShell:</span></span>

```powershell
Import-Certificate -FilePath $certFilePath -CertStoreLocation 'Cert:\LocalMachine\Root'
```

<span data-ttu-id="31579-181">Para .NET Core 3.1, ejecute el comando siguiente en WSL:</span><span class="sxs-lookup"><span data-stu-id="31579-181">For .NET Core 3.1, run the following command in WSL:</span></span>

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/path/to/certs/:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

<span data-ttu-id="31579-182">A partir de .NET 5, Kestrel puede tomar los archivos `.crt` y `.key` con codificación PEM.</span><span class="sxs-lookup"><span data-stu-id="31579-182">Starting with .NET 5, Kestrel can take the `.crt` and PEM-encoded `.key` files.</span></span> <span data-ttu-id="31579-183">Puede ejecutar el ejemplo con el comando siguiente para .NET 5:</span><span class="sxs-lookup"><span data-stu-id="31579-183">You can run the sample with the following command for .NET 5:</span></span>

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=/https/contoso.com.key -v /c/path/to/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> <span data-ttu-id="31579-184">Tenga en cuenta que en WSL, la ruta de montaje del volumen puede cambiar en función de la configuración.</span><span class="sxs-lookup"><span data-stu-id="31579-184">Note that in WSL, the volume mount path may change depending on the configuration.</span></span>

<span data-ttu-id="31579-185">Para .NET Core 3.1 en Windows, ejecute el comando siguiente en `Powershell`:</span><span class="sxs-lookup"><span data-stu-id="31579-185">For .NET Core 3.1 in Windows, run the following command in `Powershell`:</span></span>

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="31579-186">Para .NET 5 en Windows, ejecute el comando siguiente en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="31579-186">For .NET 5 in Windows, run the following command in PowerShell:</span></span>

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=c:\https\contoso.com.key -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="31579-187">Una vez que la aplicación esté activa, vaya a contoso.com:8001 en un explorador.</span><span class="sxs-lookup"><span data-stu-id="31579-187">Once the application is up, navigate to contoso.com:8001 in a browser.</span></span>

<span data-ttu-id="31579-188">Asegúrese de que las entradas del host se actualizan para que `contoso.com` responda en la dirección IP adecuada (por ejemplo, 127.0.0.1).</span><span class="sxs-lookup"><span data-stu-id="31579-188">Be sure that the host entries are updated for `contoso.com` to answer on  the appropriate ip address (for example 127.0.0.1).</span></span> <span data-ttu-id="31579-189">Si no se reconoce el certificado, asegúrese de que el certificado que se carga con el contenedor también sea de confianza en el host y de que existan entradas SAN/DNS adecuadas para `contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="31579-189">If the certificate isn't recognized, make sure that the certificate that is loaded with the container is also trusted on the host, and that there's appropriate SAN / DNS entries for `contoso.com`.</span></span>

#### <a name="clean-up"></a><span data-ttu-id="31579-190">Limpieza</span><span class="sxs-lookup"><span data-stu-id="31579-190">Clean up</span></span>

<span data-ttu-id="31579-191">Asegúrese de limpiar los certificados autofirmados una vez que se hayan realizado las pruebas.</span><span class="sxs-lookup"><span data-stu-id="31579-191">Be sure to clean up the self-signed certificates once done testing.</span></span>

```powershell
Get-ChildItem $certFilePath | Remove-Item
```
