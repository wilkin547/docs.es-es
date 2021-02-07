---
description: 'Más información acerca de: ejemplo FindPrivateKey'
title: Ejemplo de FindPrivateKey
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: 0e876aa3e1f6dde16acbb3ddd2a130ad49d369fc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732428"
---
# <a name="findprivatekey-sample"></a><span data-ttu-id="00548-103">Ejemplo de FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="00548-103">FindPrivateKey sample</span></span>

<span data-ttu-id="00548-104">Puede ser difícil buscar la ubicación y el nombre del archivo de clave privada asociados a un certificado X.509 concreto en el almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="00548-104">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="00548-105">La herramienta FindPrivateKey.exe facilita este proceso.</span><span class="sxs-lookup"><span data-stu-id="00548-105">The FindPrivateKey.exe tool facilitates this process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00548-106">FindPrivateKey es un ejemplo que debe compilarse antes de su uso.</span><span class="sxs-lookup"><span data-stu-id="00548-106">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="00548-107">Vea la sección [para compilar el proyecto FindPrivateKey](#to-build-the-findprivatekey-project) para obtener instrucciones sobre cómo compilar la herramienta FindPrivateKey.</span><span class="sxs-lookup"><span data-stu-id="00548-107">See the [To build the FindPrivateKey project](#to-build-the-findprivatekey-project) section for instructions on how to build the FindPrivateKey tool.</span></span>

<span data-ttu-id="00548-108">Un administrador o cualquier usuario instala los certificados X.509 en el equipo.</span><span class="sxs-lookup"><span data-stu-id="00548-108">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="00548-109">Sin embargo, se puede tener acceso al certificado mediante un servicio que se ejecuta en una cuenta diferente.</span><span class="sxs-lookup"><span data-stu-id="00548-109">However, the certificate may be accessed by a service running under a different account.</span></span> <span data-ttu-id="00548-110">Por ejemplo, la cuenta de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="00548-110">For example, the NETWORK SERVICE account.</span></span>

<span data-ttu-id="00548-111">Puede que esta cuenta no tenga acceso al archivo de clave privada porque no instaló el certificado en un principio.</span><span class="sxs-lookup"><span data-stu-id="00548-111">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="00548-112">La herramienta FindPrivateKey le da la ubicación del archivo de clave privada de un certificado X.509 determinado.</span><span class="sxs-lookup"><span data-stu-id="00548-112">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="00548-113">Puede agregar o quitar permisos a este archivo cuando conoce la ubicación del archivo de clave privada de los certificados X.509 determinados.</span><span class="sxs-lookup"><span data-stu-id="00548-113">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>

<span data-ttu-id="00548-114">Los ejemplos que usan certificados para la seguridad utilizan la herramienta FindPrivateKey en el archivo de *Setup.bat* .</span><span class="sxs-lookup"><span data-stu-id="00548-114">The samples that use certificates for security use the FindPrivateKey tool in the *Setup.bat* file.</span></span> <span data-ttu-id="00548-115">Una vez que se ha encontrado el archivo de clave privada, puede usar otras herramientas como *Cacls.exe* para establecer los derechos de acceso adecuados en el archivo.</span><span class="sxs-lookup"><span data-stu-id="00548-115">Once the private key file has been found, you can use other tools such as *Cacls.exe* to set the appropriate access rights onto the file.</span></span>

<span data-ttu-id="00548-116">Al ejecutar un servicio de Windows Communication Foundation (WCF) bajo una cuenta de usuario, como un archivo ejecutable autohospedado, asegúrese de que la cuenta de usuario tiene acceso de solo lectura al archivo.</span><span class="sxs-lookup"><span data-stu-id="00548-116">When running a Windows Communication Foundation (WCF) service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="00548-117">Al ejecutar un servicio WCF en Internet Information Services (IIS), las cuentas predeterminadas en las que se ejecuta el servicio son el servicio de red en IIS 7 y versiones anteriores, o la identidad del grupo de aplicaciones en IIS 7,5 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="00548-117">When running a WCF service under Internet Information Services (IIS) the default accounts that the service runs under are the NETWORK SERVICE on IIS 7 and earlier versions, or Application Pool Identity on IIS 7.5 and later versions.</span></span> <span data-ttu-id="00548-118">Para obtener más información, vea [identidades del grupo de aplicaciones](/iis/manage/configuring-security/application-pool-identities).</span><span class="sxs-lookup"><span data-stu-id="00548-118">For more information, see [Application Pool Identities](/iis/manage/configuring-security/application-pool-identities).</span></span>

## <a name="examples"></a><span data-ttu-id="00548-119">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="00548-119">Examples</span></span>

<span data-ttu-id="00548-120">Al tener acceso a un certificado para el que el proceso no tiene privilegios de lectura, verá un mensaje de excepción similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="00548-120">When accessing a certificate for which the process doesn't have read privilege, you see an exception message similar to the following example:</span></span>

```output
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

<span data-ttu-id="00548-121">Cuando esto suceda, use la herramienta FindPrivateKey para buscar el archivo de clave privada y, a continuación, establezca el derecho de acceso para el proceso en el que se está ejecutando el servicio.</span><span class="sxs-lookup"><span data-stu-id="00548-121">When this occurs, use the FindPrivateKey tool to find the private key file, and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="00548-122">Por ejemplo, esto se puede hacer con la herramienta Cacls.exe como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="00548-122">For example, this can be done with the Cacls.exe tool as shown in the following example:</span></span>

```console
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="00548-123">Para compilar el proyecto FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="00548-123">To build the FindPrivateKey project</span></span>

<span data-ttu-id="00548-124">Para descargar el proyecto, visite los [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span><span class="sxs-lookup"><span data-stu-id="00548-124">To download the project, visit [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span></span>

1. <span data-ttu-id="00548-125">Abra el explorador de archivos y vaya a la carpeta *WF_WCF_Samples \wcf\setup\findprivatekey\cs* bajo la ubicación del directorio donde instaló el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="00548-125">Open File Explorer and navigate to the *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* folder under the directory location where you installed the sample.</span></span>

2. <span data-ttu-id="00548-126">Haga doble clic en el icono del archivo .sln para abrir el archivo en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="00548-126">Double-click the .sln file icon to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="00548-127">En el menú **compilar** , seleccione **recompilar solución**.</span><span class="sxs-lookup"><span data-stu-id="00548-127">In the **Build** menu, select **Rebuild Solution**.</span></span>

4. <span data-ttu-id="00548-128">Al compilar la solución, se crea el archivo: FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="00548-128">Building the solution generates the file: FindPrivateKey.exe.</span></span>

## <a name="conventionscommand-line-entries"></a><span data-ttu-id="00548-129">Convenciones: entradas de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="00548-129">Conventions—Command-Line entries</span></span>

 <span data-ttu-id="00548-130">"[*opción*]" representa un conjunto opcional de parámetros.</span><span class="sxs-lookup"><span data-stu-id="00548-130">"[*option*]" represents an optional set of parameters.</span></span>

 <span data-ttu-id="00548-131">"{*Option*}" representa un conjunto obligatorio de parámetros.</span><span class="sxs-lookup"><span data-stu-id="00548-131">"{*option*}" represents a mandatory set of parameters.</span></span>

 <span data-ttu-id="00548-132">"*opción1* &#124; *opción2*" representa una opción entre los conjuntos de opciones.</span><span class="sxs-lookup"><span data-stu-id="00548-132">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>

 <span data-ttu-id="00548-133">" \<*value*> " representa un valor de parámetro que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="00548-133">"\<*value*>" represents a parameter value to be entered.</span></span>

## <a name="usage"></a><span data-ttu-id="00548-134">Uso</span><span class="sxs-lookup"><span data-stu-id="00548-134">Usage</span></span>

```console
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

<span data-ttu-id="00548-135">Donde:</span><span class="sxs-lookup"><span data-stu-id="00548-135">Where:</span></span>

| <span data-ttu-id="00548-136">Parámetro</span><span class="sxs-lookup"><span data-stu-id="00548-136">Parameter</span></span>         | <span data-ttu-id="00548-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="00548-137">Description</span></span>                                                                       |
|-----------------|-----------------------------------------------------------------------------------|
| `<subjectName>` | <span data-ttu-id="00548-138">Nombre del firmante del certificado.</span><span class="sxs-lookup"><span data-stu-id="00548-138">The subject name of the certificate</span></span>                                               |
| `<thumbprint>`  | <span data-ttu-id="00548-139">La huella digital del certificado (puede usar la herramienta de Certmgr.exe para encontrarla)</span><span class="sxs-lookup"><span data-stu-id="00548-139">The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)</span></span> |
| `-f`            | <span data-ttu-id="00548-140">solo nombre del archivo de salida</span><span class="sxs-lookup"><span data-stu-id="00548-140">output file name only</span></span>                                                             |
| `-d`            | <span data-ttu-id="00548-141">solo el directorio de salida</span><span class="sxs-lookup"><span data-stu-id="00548-141">output directory only</span></span>                                                             |
| `-a`            | <span data-ttu-id="00548-142">nombre de archivo absoluto de salida</span><span class="sxs-lookup"><span data-stu-id="00548-142">output absolute file name</span></span>                                                         |

<span data-ttu-id="00548-143">Si no se especifica ningún parámetro en el símbolo del sistema, se muestra el texto de ayuda con esta información.</span><span class="sxs-lookup"><span data-stu-id="00548-143">If no parameters are specified at the command prompt, then help text with this information is displayed.</span></span>

## <a name="examples"></a><span data-ttu-id="00548-144">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="00548-144">Examples</span></span>

<span data-ttu-id="00548-145">Este ejemplo busca el nombre de archivo del certificado con un nombre de sujeto "CN = localhost", en el almacén personal del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="00548-145">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.</span></span>

```console
FindPrivateKey My CurrentUser -n "CN=localhost"
```

<span data-ttu-id="00548-146">En este ejemplo se busca el nombre de archivo del certificado con un nombre de sujeto de "CN = localhost", en el almacén personal del usuario actual y se genera la ruta de acceso completa al directorio.</span><span class="sxs-lookup"><span data-stu-id="00548-146">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User and output the full directory path.</span></span>

```console
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

<span data-ttu-id="00548-147">Este ejemplo busca el nombre de archivo del certificado con una huella digital de "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", en el almacén personal del equipo local.</span><span class="sxs-lookup"><span data-stu-id="00548-147">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>

```console
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
