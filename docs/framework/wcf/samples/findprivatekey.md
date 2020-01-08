---
title: Ejemplo de FindPrivateKey
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: 0ed1e5e81a5d2f7f3586e5dce306e8244b5ebd48
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346018"
---
# <a name="findprivatekey-sample"></a><span data-ttu-id="95d85-102">Ejemplo de FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="95d85-102">FindPrivateKey sample</span></span>

<span data-ttu-id="95d85-103">Puede ser difícil buscar la ubicación y el nombre del archivo de clave privada asociados a un certificado X.509 concreto en el almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="95d85-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="95d85-104">La herramienta FindPrivateKey.exe facilita este proceso.</span><span class="sxs-lookup"><span data-stu-id="95d85-104">The FindPrivateKey.exe tool facilitates this process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95d85-105">FindPrivateKey es un ejemplo que debe compilarse antes de su uso.</span><span class="sxs-lookup"><span data-stu-id="95d85-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="95d85-106">Vea la sección [para compilar el proyecto FindPrivateKey](#to-build-the-findprivatekey-project) para obtener instrucciones sobre cómo compilar la herramienta FindPrivateKey.</span><span class="sxs-lookup"><span data-stu-id="95d85-106">See the [To build the FindPrivateKey project](#to-build-the-findprivatekey-project) section for instructions on how to build the FindPrivateKey tool.</span></span>

<span data-ttu-id="95d85-107">Un administrador o cualquier usuario instala los certificados X.509 en el equipo.</span><span class="sxs-lookup"><span data-stu-id="95d85-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="95d85-108">Sin embargo, se puede tener acceso al certificado mediante un servicio que se ejecuta en una cuenta diferente.</span><span class="sxs-lookup"><span data-stu-id="95d85-108">However, the certificate may be accessed by a service running under a different account.</span></span> <span data-ttu-id="95d85-109">Por ejemplo, la cuenta de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="95d85-109">For example, the NETWORK SERVICE account.</span></span>

<span data-ttu-id="95d85-110">Puede que esta cuenta no tenga acceso al archivo de clave privada porque no instaló el certificado en un principio.</span><span class="sxs-lookup"><span data-stu-id="95d85-110">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="95d85-111">La herramienta FindPrivateKey le da la ubicación del archivo de clave privada de un certificado X.509 determinado.</span><span class="sxs-lookup"><span data-stu-id="95d85-111">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="95d85-112">Puede agregar o quitar permisos a este archivo cuando conoce la ubicación del archivo de clave privada de los certificados X.509 determinados.</span><span class="sxs-lookup"><span data-stu-id="95d85-112">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>

<span data-ttu-id="95d85-113">Los ejemplos que usan certificados para la seguridad utilizan la herramienta FindPrivateKey en el archivo *setup. bat* .</span><span class="sxs-lookup"><span data-stu-id="95d85-113">The samples that use certificates for security use the FindPrivateKey tool in the *Setup.bat* file.</span></span> <span data-ttu-id="95d85-114">Una vez que se ha encontrado el archivo de clave privada, puede usar otras herramientas como *cacls. exe* para establecer los derechos de acceso adecuados en el archivo.</span><span class="sxs-lookup"><span data-stu-id="95d85-114">Once the private key file has been found, you can use other tools such as *Cacls.exe* to set the appropriate access rights onto the file.</span></span>

<span data-ttu-id="95d85-115">Al ejecutar un servicio de Windows Communication Foundation (WCF) bajo una cuenta de usuario, como un archivo ejecutable autohospedado, asegúrese de que la cuenta de usuario tiene acceso de solo lectura al archivo.</span><span class="sxs-lookup"><span data-stu-id="95d85-115">When running a Windows Communication Foundation (WCF) service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="95d85-116">Al ejecutar un servicio WCF en Internet Information Services (IIS), las cuentas predeterminadas en las que se ejecuta el servicio son el servicio de red en IIS 7 y versiones anteriores, o la identidad del grupo de aplicaciones en IIS 7,5 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="95d85-116">When running a WCF service under Internet Information Services (IIS) the default accounts that the service runs under are the NETWORK SERVICE on IIS 7 and earlier versions, or Application Pool Identity on IIS 7.5 and later versions.</span></span> <span data-ttu-id="95d85-117">Para obtener más información, vea [identidades del grupo de aplicaciones](/iis/manage/configuring-security/application-pool-identities).</span><span class="sxs-lookup"><span data-stu-id="95d85-117">For more information, see [Application Pool Identities](/iis/manage/configuring-security/application-pool-identities).</span></span>

## <a name="examples"></a><span data-ttu-id="95d85-118">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="95d85-118">Examples</span></span>

<span data-ttu-id="95d85-119">Al tener acceso a un certificado para el que el proceso no tiene privilegios de lectura, verá un mensaje de excepción similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="95d85-119">When accessing a certificate for which the process doesn't have read privilege, you see an exception message similar to the following example:</span></span>

```output
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

<span data-ttu-id="95d85-120">Cuando esto suceda, use la herramienta FindPrivateKey para buscar el archivo de clave privada y, a continuación, establezca el derecho de acceso para el proceso en el que se está ejecutando el servicio.</span><span class="sxs-lookup"><span data-stu-id="95d85-120">When this occurs, use the FindPrivateKey tool to find the private key file, and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="95d85-121">Por ejemplo, esto se puede hacer con la herramienta CACLS. exe como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="95d85-121">For example, this can be done with the Cacls.exe tool as shown in the following example:</span></span>

```console
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="95d85-122">Para compilar el proyecto FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="95d85-122">To build the FindPrivateKey project</span></span>

<span data-ttu-id="95d85-123">Para descargar el proyecto, visite los [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span><span class="sxs-lookup"><span data-stu-id="95d85-123">To download the project, visit [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span></span>

1. <span data-ttu-id="95d85-124">Abra el explorador de archivos y vaya a la carpeta *WF_WCF_Samples \wcf\setup\findprivatekey\cs* bajo la ubicación del directorio donde instaló el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="95d85-124">Open File Explorer and navigate to the *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* folder under the directory location where you installed the sample.</span></span>

2. <span data-ttu-id="95d85-125">Haga doble clic en el icono del archivo .sln para abrir el archivo en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="95d85-125">Double-click the .sln file icon to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="95d85-126">En el menú **compilar** , seleccione **recompilar solución**.</span><span class="sxs-lookup"><span data-stu-id="95d85-126">In the **Build** menu, select **Rebuild Solution**.</span></span>

4. <span data-ttu-id="95d85-127">Al compilar la solución, se crea el archivo: FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="95d85-127">Building the solution generates the file: FindPrivateKey.exe.</span></span>

## <a name="conventionscommand-line-entries"></a><span data-ttu-id="95d85-128">Convenciones: entradas de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="95d85-128">Conventions—Command-Line entries</span></span>

 <span data-ttu-id="95d85-129">"[*opción*]" representa un conjunto opcional de parámetros.</span><span class="sxs-lookup"><span data-stu-id="95d85-129">"[*option*]" represents an optional set of parameters.</span></span>

 <span data-ttu-id="95d85-130">"{*Option*}" representa un conjunto obligatorio de parámetros.</span><span class="sxs-lookup"><span data-stu-id="95d85-130">"{*option*}" represents a mandatory set of parameters.</span></span>

 <span data-ttu-id="95d85-131">"*Opción1* &#124; *opción2*" representa una opción entre los conjuntos de opciones.</span><span class="sxs-lookup"><span data-stu-id="95d85-131">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>

 <span data-ttu-id="95d85-132">"\<*valor*>" representa un valor de parámetro que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="95d85-132">"\<*value*>" represents a parameter value to be entered.</span></span>

## <a name="usage"></a><span data-ttu-id="95d85-133">Usage</span><span class="sxs-lookup"><span data-stu-id="95d85-133">Usage</span></span>

```console
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

<span data-ttu-id="95d85-134">Donde:</span><span class="sxs-lookup"><span data-stu-id="95d85-134">Where:</span></span>

| <span data-ttu-id="95d85-135">Parámetro</span><span class="sxs-lookup"><span data-stu-id="95d85-135">Parameter</span></span>         | <span data-ttu-id="95d85-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="95d85-136">Description</span></span>                                                                       |
|-----------------|-----------------------------------------------------------------------------------|
| `<subjectName>` | <span data-ttu-id="95d85-137">Nombre del firmante del certificado.</span><span class="sxs-lookup"><span data-stu-id="95d85-137">The subject name of the certificate</span></span>                                               |
| `<thumbprint>`  | <span data-ttu-id="95d85-138">La huella digital del certificado (puede usar la herramienta Certmgr. exe para encontrarlo)</span><span class="sxs-lookup"><span data-stu-id="95d85-138">The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)</span></span> |
| `-f`            | <span data-ttu-id="95d85-139">solo nombre del archivo de salida</span><span class="sxs-lookup"><span data-stu-id="95d85-139">output file name only</span></span>                                                             |
| `-d`            | <span data-ttu-id="95d85-140">solo el directorio de salida</span><span class="sxs-lookup"><span data-stu-id="95d85-140">output directory only</span></span>                                                             |
| `-a`            | <span data-ttu-id="95d85-141">nombre de archivo absoluto de salida</span><span class="sxs-lookup"><span data-stu-id="95d85-141">output absolute file name</span></span>                                                         |

<span data-ttu-id="95d85-142">Si no se especifica ningún parámetro en el símbolo del sistema, se muestra el texto de ayuda con esta información.</span><span class="sxs-lookup"><span data-stu-id="95d85-142">If no parameters are specified at the command prompt, then help text with this information is displayed.</span></span>

## <a name="examples"></a><span data-ttu-id="95d85-143">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="95d85-143">Examples</span></span>

<span data-ttu-id="95d85-144">Este ejemplo busca el nombre de archivo del certificado con un nombre de sujeto "CN = localhost", en el almacén personal del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="95d85-144">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.</span></span>

```console
FindPrivateKey My CurrentUser -n "CN=localhost"
```

<span data-ttu-id="95d85-145">En este ejemplo se busca el nombre de archivo del certificado con un nombre de sujeto de "CN = localhost", en el almacén personal del usuario actual y se genera la ruta de acceso completa al directorio.</span><span class="sxs-lookup"><span data-stu-id="95d85-145">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User and output the full directory path.</span></span>

```console
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

<span data-ttu-id="95d85-146">Este ejemplo busca el nombre de archivo del certificado con una huella digital de "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", en el almacén personal del equipo local.</span><span class="sxs-lookup"><span data-stu-id="95d85-146">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>

```console
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
