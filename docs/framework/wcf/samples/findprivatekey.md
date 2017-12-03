---
title: FindPrivateKey
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 81ca357ccdcbe76f36f3ba56caf2013a80143728
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="findprivatekey"></a><span data-ttu-id="48c71-102">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="48c71-102">FindPrivateKey</span></span>
<span data-ttu-id="48c71-103">Puede ser difícil buscar la ubicación y el nombre del archivo de clave privada asociados a un certificado X.509 concreto en el almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="48c71-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="48c71-104">La herramienta FindPrivateKey.exe facilita este proceso.</span><span class="sxs-lookup"><span data-stu-id="48c71-104">The FindPrivateKey.exe tool facilitates this process.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="48c71-105">FindPrivateKey es un ejemplo que debe compilarse antes de su uso.</span><span class="sxs-lookup"><span data-stu-id="48c71-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="48c71-106">Consulte la sección "para compilar el proyecto FindPrivateKey" a continuación para obtener instrucciones sobre cómo compilar la herramienta FindPrivateKey.</span><span class="sxs-lookup"><span data-stu-id="48c71-106">See the "To build the FindPrivateKey project" section below for instructions on how to build the FindPrivateKey tool.</span></span>  
  
 <span data-ttu-id="48c71-107">Un administrador o cualquier usuario instala los certificados X.509 en el equipo.</span><span class="sxs-lookup"><span data-stu-id="48c71-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="48c71-108">Sin embargo, se puede tener acceso al certificado mediante un servicio que se ejecuta bajo una cuenta diferente (por ejemplo, ASPNET en [!INCLUDE[wxp](../../../../includes/wxp-md.md)] o las cuentas del SERVICIO DE RED en [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="48c71-108">However the certificate may be accessed by a service running under a different account (for example, the ASPNET on [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or the NETWORK SERVICE accounts on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]).</span></span>  
  
 <span data-ttu-id="48c71-109">Puede que esta cuenta no tenga acceso al archivo de clave privada porque no instaló el certificado en un principio.</span><span class="sxs-lookup"><span data-stu-id="48c71-109">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="48c71-110">La herramienta FindPrivateKey le da la ubicación del archivo de clave privada de un certificado X.509 determinado.</span><span class="sxs-lookup"><span data-stu-id="48c71-110">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="48c71-111">Puede agregar o quitar permisos a este archivo cuando conoce la ubicación del archivo de clave privada de los certificados X.509 determinados.</span><span class="sxs-lookup"><span data-stu-id="48c71-111">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>  
  
 <span data-ttu-id="48c71-112">Los ejemplos que utilizan certificados para la seguridad utilizan la herramienta FindPrivateKey en el archivo Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="48c71-112">The samples that use certificates for security use the FindPrivateKey tool in the Setup.bat file.</span></span> <span data-ttu-id="48c71-113">Una vez que se ha encontrado el archivo de clave privada, puede usar otras herramientas como Cacls.exe para establecer los derechos de acceso adecuados en el archivo.</span><span class="sxs-lookup"><span data-stu-id="48c71-113">Once the private key file has been found you can use other tools such as Cacls.exe to set the appropriate access rights onto the file.</span></span>  
  
 <span data-ttu-id="48c71-114">Cuando se ejecuta un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] bajo una cuenta de usuario, como una aplicación ejecutable autohospedada, asegúrese de que la cuenta de usuario tiene acceso de solo lectura al archivo.</span><span class="sxs-lookup"><span data-stu-id="48c71-114">When running a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="48c71-115">Al ejecutar un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bajo Internet Information Services (IIS), las cuentas predeterminadas que el servicio ejecuta son ASPNET en [!INCLUDE[wxp](../../../../includes/wxp-md.md)] o el SERVICIO DE RED en [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], que no tiene acceso al archivo de clave privada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="48c71-115">When running a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service under Internet Information Services (IIS) the default accounts that the service runs under are the ASPNET on [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or the NETWORK SERVICE on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], which by default do not have access to the private key file.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="48c71-116">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="48c71-116">Examples</span></span>  
 <span data-ttu-id="48c71-117">Al tener acceso a un certificado para el que el proceso no tiene privilegio de lectura, ve un mensaje de excepción similar al siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="48c71-117">When accessing a certificate for which the process does not have read privilege, you see an exception message similar to the following example.</span></span>  
  
```  
System.ArgumentException was unhandled  
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."  
Source="System.ServiceModel"  
```  
  
 <span data-ttu-id="48c71-118">Cuando esto se produce, utilice la herramienta FindPrivateKey para buscar el archivo de clave privada y, a continuación, establezca el derecho de acceso para el proceso bajo el que el servicio se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="48c71-118">When this occurs use the FindPrivateKey tool to find the private key file and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="48c71-119">Por ejemplo, esto se puede hacer con la herramienta Cacls.exe, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="48c71-119">For example, this can be done with the Cacls.exe tool as shown in the following example.</span></span>  
  
```  
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
```  
  
#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="48c71-120">Para compilar el proyecto FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="48c71-120">To build the FindPrivateKey project</span></span>  
  
1.  <span data-ttu-id="48c71-121">Abra [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] y desplácese hasta el subdirectorio específico del lenguaje bajo la ubicación del directorio donde instaló el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="48c71-121">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the language-specific subdirectory under the directory location where you installed the sample.</span></span>  
  
2.  <span data-ttu-id="48c71-122">Haga doble clic en el icono del archivo .sln para abrir el archivo en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="48c71-122">Double-click the .sln file icon to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="48c71-123">En el **generar** menú, seleccione **volver a generar solución**.</span><span class="sxs-lookup"><span data-stu-id="48c71-123">In the **Build** menu, select **Rebuild Solution**.</span></span> <span data-ttu-id="48c71-124">Los archivos de programa del cliente se compilan en client\bin y los archivos de programa del servicio se compilan en service\bin.</span><span class="sxs-lookup"><span data-stu-id="48c71-124">The client program files are built to client\bin and the service program files are built to service\bin.</span></span>  
  
4.  <span data-ttu-id="48c71-125">Al compilar la solución, se crea el archivo: FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="48c71-125">Building the solution generates the file: FindPrivateKey.exe.</span></span>  
  
## <a name="conventionscommand-line-entries"></a><span data-ttu-id="48c71-126">Convenciones: entradas de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="48c71-126">Conventions—Command-Line Entries</span></span>  
 <span data-ttu-id="48c71-127">"[*opción*]" representa un conjunto opcional de parámetros.</span><span class="sxs-lookup"><span data-stu-id="48c71-127">"[*option*]" represents an optional set of parameters.</span></span>  
  
 <span data-ttu-id="48c71-128">"{*opción*}" representa un conjunto de parámetros obligatorio.</span><span class="sxs-lookup"><span data-stu-id="48c71-128">"{*option*}" represents a mandatory set of parameters.</span></span>  
  
 <span data-ttu-id="48c71-129">"*opción1* &#124; *opción2*"representa una opción entre conjuntos de opciones.</span><span class="sxs-lookup"><span data-stu-id="48c71-129">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>  
  
 <span data-ttu-id="48c71-130">"\<*valor*>" representa un valor de parámetro que se especifique.</span><span class="sxs-lookup"><span data-stu-id="48c71-130">"\<*value*>" represents a parameter value to be entered.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="48c71-131">Uso</span><span class="sxs-lookup"><span data-stu-id="48c71-131">Usage</span></span>  
  
```  
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]  
```  
  
 <span data-ttu-id="48c71-132">Donde:</span><span class="sxs-lookup"><span data-stu-id="48c71-132">Where:</span></span>  
  
```  
       <subjectName> The subject name of the certificate  
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)  
       -f            output file name only  
       -d            output directory only  
       -a            output absolute file name  
```  
  
 <span data-ttu-id="48c71-133">Si no se especifica ningún parámetro en el símbolo del sistema, se mostrará este texto de ayuda.</span><span class="sxs-lookup"><span data-stu-id="48c71-133">If no parameters are specified at the command prompt then this help text is displayed.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="48c71-134">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="48c71-134">Examples</span></span>  
 <span data-ttu-id="48c71-135">Este ejemplo busca el nombre de archivo del certificado con un nombre de asunto de "CN=localhost", en el almacén personal de Current User.FindPrivateKey My CurrentUser -n "CN=localhost".</span><span class="sxs-lookup"><span data-stu-id="48c71-135">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.FindPrivateKey My CurrentUser -n "CN=localhost".</span></span>  
  
 <span data-ttu-id="48c71-136">Este ejemplo busca el nombre de archivo del certificado con un nombre de asunto de "CN=localhost", en el almacén personal del usuario actual y proporciona la ruta de acceso completa al directorio.</span><span class="sxs-lookup"><span data-stu-id="48c71-136">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current and output the full directory path.</span></span>  
  
```  
User.FindPrivateKey My CurrentUser -n "CN=localhost" -a  
```  
  
 <span data-ttu-id="48c71-137">Este ejemplo busca el nombre de archivo del certificado con una huella digital de "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", en el almacén personal del equipo local.</span><span class="sxs-lookup"><span data-stu-id="48c71-137">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>  
  
```  
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –c  
```  
  
## <a name="see-also"></a><span data-ttu-id="48c71-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="48c71-138">See Also</span></span>
