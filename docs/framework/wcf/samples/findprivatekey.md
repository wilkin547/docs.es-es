---
title: Ejemplo de FindPrivateKey - WCF
ms.date: 12/04/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords: FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 29489cd1b82cf1c31f178d8a305a21371b542f15
ms.sourcegitcommit: 9bee08539b1886c9d57fa3d5bd8a58dfdd7cad94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2017
---
# <a name="findprivatekey-sample"></a><span data-ttu-id="66154-102">Ejemplo de FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="66154-102">FindPrivateKey sample</span></span>

<span data-ttu-id="66154-103">Puede ser difícil buscar la ubicación y el nombre del archivo de clave privada asociados a un certificado X.509 concreto en el almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="66154-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="66154-104">La herramienta FindPrivateKey.exe facilita este proceso.</span><span class="sxs-lookup"><span data-stu-id="66154-104">The FindPrivateKey.exe tool facilitates this process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66154-105">FindPrivateKey es un ejemplo que debe compilarse antes de su uso.</span><span class="sxs-lookup"><span data-stu-id="66154-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="66154-106">Consulte la [para compilar el proyecto FindPrivateKey](#to-build-the-findprivatekey-project) sección para obtener instrucciones sobre cómo compilar la herramienta FindPrivateKey.</span><span class="sxs-lookup"><span data-stu-id="66154-106">See the [To build the FindPrivateKey project](#to-build-the-findprivatekey-project) section for instructions on how to build the FindPrivateKey tool.</span></span>

<span data-ttu-id="66154-107">Un administrador o cualquier usuario instala los certificados X.509 en el equipo.</span><span class="sxs-lookup"><span data-stu-id="66154-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="66154-108">Sin embargo, puede tener acceso al certificado por un servicio que se ejecuta bajo una cuenta diferente.</span><span class="sxs-lookup"><span data-stu-id="66154-108">However, the certificate may be accessed by a service running under a different account.</span></span> <span data-ttu-id="66154-109">Por ejemplo, la cuenta de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="66154-109">For example, the NETWORK SERVICE account.</span></span>

<span data-ttu-id="66154-110">Puede que esta cuenta no tenga acceso al archivo de clave privada porque no instaló el certificado en un principio.</span><span class="sxs-lookup"><span data-stu-id="66154-110">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="66154-111">La herramienta FindPrivateKey le da la ubicación del archivo de clave privada de un certificado X.509 determinado.</span><span class="sxs-lookup"><span data-stu-id="66154-111">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="66154-112">Puede agregar o quitar permisos a este archivo cuando conoce la ubicación del archivo de clave privada de los certificados X.509 determinados.</span><span class="sxs-lookup"><span data-stu-id="66154-112">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>

<span data-ttu-id="66154-113">Los ejemplos que utilizan certificados para la seguridad usan la herramienta FindPrivateKey en el *Setup.bat* archivo.</span><span class="sxs-lookup"><span data-stu-id="66154-113">The samples that use certificates for security use the FindPrivateKey tool in the *Setup.bat* file.</span></span> <span data-ttu-id="66154-114">Una vez que se ha encontrado el archivo de clave privada, puede usar otras herramientas como *Cacls.exe* para establecer los derechos de acceso adecuados en el archivo.</span><span class="sxs-lookup"><span data-stu-id="66154-114">Once the private key file has been found, you can use other tools such as *Cacls.exe* to set the appropriate access rights onto the file.</span></span>

<span data-ttu-id="66154-115">Cuando se ejecuta un servicio de Windows Communication Foundation (WCF) en una cuenta de usuario, como una aplicación ejecutable autohospedada, asegúrese de que la cuenta de usuario tiene acceso de solo lectura al archivo.</span><span class="sxs-lookup"><span data-stu-id="66154-115">When running a Windows Communication Foundation (WCF) service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="66154-116">Cuando se ejecuta un servicio WCF en Internet Information Services (IIS) son las cuentas predeterminadas que se ejecuta el servicio en el servicio de red en IIS 7 y versiones anteriores, o la identidad del grupo de aplicaciones en IIS 7.5 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="66154-116">When running a WCF service under Internet Information Services (IIS) the default accounts that the service runs under are the NETWORK SERVICE on IIS 7 and earlier versions, or Application Pool Identity on IIS 7.5 and later versions.</span></span> <span data-ttu-id="66154-117">Para obtener más información, consulte [identidades del grupo de aplicaciones](/iis/manage/configuring-security/application-pool-identities).</span><span class="sxs-lookup"><span data-stu-id="66154-117">For more information, see [Application Pool Identities](/iis/manage/configuring-security/application-pool-identities).</span></span>

## <a name="examples"></a><span data-ttu-id="66154-118">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="66154-118">Examples</span></span>

<span data-ttu-id="66154-119">Cuando se obtiene acceso a un certificado para el que el proceso no tiene privilegios de lectura, verá un mensaje de excepción similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="66154-119">When accessing a certificate for which the process doesn't have read privilege, you see an exception message similar to the following example:</span></span>

```
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

<span data-ttu-id="66154-120">Cuando esto ocurre, use la herramienta FindPrivateKey para buscar el archivo de clave privada y, a continuación, establezca el derecho de acceso para el proceso que se ejecuta el servicio.</span><span class="sxs-lookup"><span data-stu-id="66154-120">When this occurs, use the FindPrivateKey tool to find the private key file, and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="66154-121">Por ejemplo, puede hacerlo con la herramienta Cacls.exe tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="66154-121">For example, this can be done with the Cacls.exe tool as shown in the following example:</span></span>

```
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="66154-122">Para compilar el proyecto FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="66154-122">To build the FindPrivateKey project</span></span>

<span data-ttu-id="66154-123">Para descargar el proyecto, visite [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span><span class="sxs-lookup"><span data-stu-id="66154-123">To download the project, visit [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span></span>

1. <span data-ttu-id="66154-124">Abra [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] y navegue hasta la *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* carpeta en la ubicación del directorio donde instaló el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="66154-124">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* folder under the directory location where you installed the sample.</span></span>

2. <span data-ttu-id="66154-125">Haga doble clic en el icono del archivo .sln para abrir el archivo en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66154-125">Double-click the .sln file icon to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="66154-126">En el **generar** menú, seleccione **volver a generar solución**.</span><span class="sxs-lookup"><span data-stu-id="66154-126">In the **Build** menu, select **Rebuild Solution**.</span></span>

4. <span data-ttu-id="66154-127">Al compilar la solución, se crea el archivo: FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="66154-127">Building the solution generates the file: FindPrivateKey.exe.</span></span>

## <a name="conventionscommand-line-entries"></a><span data-ttu-id="66154-128">Convenciones: entradas de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="66154-128">Conventions—Command-Line entries</span></span>

 <span data-ttu-id="66154-129">"[*opción*]" representa un conjunto opcional de parámetros.</span><span class="sxs-lookup"><span data-stu-id="66154-129">"[*option*]" represents an optional set of parameters.</span></span>

 <span data-ttu-id="66154-130">"{*opción*}" representa un conjunto de parámetros obligatorio.</span><span class="sxs-lookup"><span data-stu-id="66154-130">"{*option*}" represents a mandatory set of parameters.</span></span>

 <span data-ttu-id="66154-131">"*opción1* &#124; *opción2*"representa una opción entre conjuntos de opciones.</span><span class="sxs-lookup"><span data-stu-id="66154-131">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>

 <span data-ttu-id="66154-132">"\<*valor*>" representa un valor de parámetro que se especifique.</span><span class="sxs-lookup"><span data-stu-id="66154-132">"\<*value*>" represents a parameter value to be entered.</span></span>

## <a name="usage"></a><span data-ttu-id="66154-133">Uso</span><span class="sxs-lookup"><span data-stu-id="66154-133">Usage</span></span>

```
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

<span data-ttu-id="66154-134">Dónde:</span><span class="sxs-lookup"><span data-stu-id="66154-134">Where:</span></span>

```
       <subjectName> The subject name of the certificate
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)
       -f            output file name only
       -d            output directory only
       -a            output absolute file name
```

<span data-ttu-id="66154-135">Si se especifica ningún parámetro en el símbolo del sistema, se muestra este texto de ayuda.</span><span class="sxs-lookup"><span data-stu-id="66154-135">If no parameters are specified at the command prompt, then this help text is displayed.</span></span>

## <a name="examples"></a><span data-ttu-id="66154-136">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="66154-136">Examples</span></span>

<span data-ttu-id="66154-137">Este ejemplo busca el nombre de archivo del certificado con un nombre de sujeto de "CN = localhost", en el almacén Personal del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="66154-137">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.</span></span>

```
FindPrivateKey My CurrentUser -n "CN=localhost"
```

<span data-ttu-id="66154-138">Este ejemplo busca el nombre de archivo del certificado con un nombre de sujeto de "CN = localhost", en el Personal almacén del usuario actual y la ruta de acceso completa del directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="66154-138">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User and output the full directory path.</span></span>

```
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

<span data-ttu-id="66154-139">Este ejemplo busca el nombre de archivo del certificado con una huella digital de "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", en el almacén personal del equipo local.</span><span class="sxs-lookup"><span data-stu-id="66154-139">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
