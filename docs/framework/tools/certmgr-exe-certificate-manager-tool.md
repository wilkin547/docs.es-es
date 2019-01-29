---
title: Certmgr.exe (Herramienta de administración de certificados)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates, managing
- CRLs
- certificate trust lists
- Certmgr.exe
- Certificate Manager tool
- CTLs
- certificate revocation lists
ms.assetid: 7e953b43-1374-4bbc-814f-53ca1b6b52bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2284baf7057ec8c0c947325b1efeced7fdd4acbd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745927"
---
# <a name="certmgrexe-certificate-manager-tool"></a><span data-ttu-id="aaa95-102">Certmgr.exe (Herramienta de administración de certificados)</span><span class="sxs-lookup"><span data-stu-id="aaa95-102">Certmgr.exe (Certificate Manager Tool)</span></span>
<span data-ttu-id="aaa95-103">El administrador de certificados (Certmgr.exe) es una herramienta que administra certificados, listas de certificados de confianza (CTL) y listas de revocación de certificados (CRL).</span><span class="sxs-lookup"><span data-stu-id="aaa95-103">The Certificate Manager tool (Certmgr.exe) manages certificates, certificate trust lists (CTLs), and certificate revocation lists (CRLs).</span></span>  
  
 <span data-ttu-id="aaa95-104">El administrador de certificados se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aaa95-104">The Certificate Manager is automatically installed with Visual Studio.</span></span> <span data-ttu-id="aaa95-105">Para iniciar la herramienta, use los [símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="aaa95-105">To start the tool, use the [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aaa95-106">El administrador de certificados (Certmgr.exe) es una utilidad de línea de comandos, mientras que Certificados (Certmgr.msc) es un complemento MMC (Microsoft Management Console).</span><span class="sxs-lookup"><span data-stu-id="aaa95-106">The Certificate Manager tool (Certmgr.exe) is a command-line utility, whereas Certificates (Certmgr.msc) is a Microsoft Management Console (MMC) snap-in.</span></span> <span data-ttu-id="aaa95-107">Dado que Certmgr.msc se encuentra normalmente en el directorio del sistema Windows, al escribir `certmgr` en la línea de comandos, es posible que se cargue el complemento MMC Certificados, incluso si ha abierto Símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aaa95-107">Because Certmgr.msc is usually found in the Windows System directory, entering `certmgr` at the command line may load the Certificates MMC snap-in even if you have opened the Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="aaa95-108">Esto ocurre porque la ruta de acceso al complemento precede a la ruta de acceso al administrador de certificados en la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="aaa95-108">This occurs because the path to the snap-in precedes the path to the Certificate Manager tool in the PATH environment variable.</span></span> <span data-ttu-id="aaa95-109">Si se produce este problema, puede ejecutar los comandos de Certmgr.exe especificando la ruta de acceso al archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="aaa95-109">If you encounter this problem, you can execute Certmgr.exe commands by specifying the path to the executable.</span></span>  
  
 <span data-ttu-id="aaa95-110">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aaa95-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="aaa95-111">Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="aaa95-111">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="aaa95-112">Para más información, consulte [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="aaa95-112">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="aaa95-113">Para información general sobre los certificados X.509, consulte [Trabajar con certificados](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="aaa95-113">For an overview of X.509 certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
 <span data-ttu-id="aaa95-114">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aaa95-114">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaa95-115">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aaa95-115">Syntax</span></span>  
  
```  
      certmgr [/add | /del | /put] [options]  
[/s[/r registryLocation]] [sourceStorename]  
[/s[/r registryLocation]] [destinationStorename]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aaa95-116">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aaa95-116">Parameters</span></span>  
  
|<span data-ttu-id="aaa95-117">Argumento</span><span class="sxs-lookup"><span data-stu-id="aaa95-117">Argument</span></span>|<span data-ttu-id="aaa95-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="aaa95-118">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="aaa95-119">*sourceStorename*</span><span class="sxs-lookup"><span data-stu-id="aaa95-119">*sourceStorename*</span></span>|<span data-ttu-id="aaa95-120">El almacén de certificados que contiene los certificados, las CTL o las CRL existentes que se van a agregar, eliminar, guardar o mostrar.</span><span class="sxs-lookup"><span data-stu-id="aaa95-120">The certificate store that contains the existing certificates, CTLs, or CRLs to add, delete, save, or display.</span></span> <span data-ttu-id="aaa95-121">Puede ser un archivo de almacén o un almacén del sistema.</span><span class="sxs-lookup"><span data-stu-id="aaa95-121">This can be a store file or a systems store.</span></span>|  
|<span data-ttu-id="aaa95-122">*destinationStorename*</span><span class="sxs-lookup"><span data-stu-id="aaa95-122">*destinationStorename*</span></span>|<span data-ttu-id="aaa95-123">El archivo o el almacén de certificados de salida.</span><span class="sxs-lookup"><span data-stu-id="aaa95-123">The output certificate store or file.</span></span>|  
  
|<span data-ttu-id="aaa95-124">Opción</span><span class="sxs-lookup"><span data-stu-id="aaa95-124">Option</span></span>|<span data-ttu-id="aaa95-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="aaa95-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="aaa95-126">**/add**</span><span class="sxs-lookup"><span data-stu-id="aaa95-126">**/add**</span></span>|<span data-ttu-id="aaa95-127">Agrega certificados, listas CTL y listas CRL a un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="aaa95-127">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>|  
|<span data-ttu-id="aaa95-128">**/all**</span><span class="sxs-lookup"><span data-stu-id="aaa95-128">**/all**</span></span>|<span data-ttu-id="aaa95-129">Agrega todas las entradas cuando se usa con la opción **/add**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-129">Adds all entries when used with **/add**.</span></span> <span data-ttu-id="aaa95-130">Elimina todas las entradas cuando se usa con la opción **/delete**. Muestra todas las entradas cuando se usa sin la opción **/add** o **/del**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-130">Deletes all entries when used with **/del**. Displays all entries when used without the **/add** or **/del** options.</span></span> <span data-ttu-id="aaa95-131">La opción **/all** no se puede usar con la opción **/put**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-131">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="aaa95-132">**/c**</span><span class="sxs-lookup"><span data-stu-id="aaa95-132">**/c**</span></span>|<span data-ttu-id="aaa95-133">Agrega certificados cuando se usa con la opción **/add**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-133">Adds certificates when used with **/add**.</span></span> <span data-ttu-id="aaa95-134">Elimina certificados cuando se usa con la opción **/delete**. Guarda certificados cuando se usa con la opción **/put**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-134">Deletes certificates when used with **/del**. Saves certificates when used with **/put**.</span></span> <span data-ttu-id="aaa95-135">Muestra certificados cuando se usa sin la opción **/add**, **/del** o **/put**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-135">Displays certificates when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="aaa95-136">**/CRL**</span><span class="sxs-lookup"><span data-stu-id="aaa95-136">**/CRL**</span></span>|<span data-ttu-id="aaa95-137">Agrega listas CRL cuando se usa con **/add**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-137">Adds CRLs when used with **/add**.</span></span> <span data-ttu-id="aaa95-138">Elimina listas CRL cuando se usa con **/del**. Guarda listas CRL cuando se usa con **/put**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-138">Deletes CRLs when used with **/del**. Saves CRLs when used with **/put**.</span></span> <span data-ttu-id="aaa95-139">Muestra listas CRL cuando se usa sin la opción **/add**, **/del** o **/put**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-139">Displays CRLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="aaa95-140">**/CTL**</span><span class="sxs-lookup"><span data-stu-id="aaa95-140">**/CTL**</span></span>|<span data-ttu-id="aaa95-141">Agrega listas CTL cuando se usa con **/add**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-141">Adds CTLs when used with **/add**.</span></span> <span data-ttu-id="aaa95-142">Elimina listas CTL cuando se usa con **/del**. Guarda listas CTL cuando se usa con **/put**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-142">Deletes CTLs when used with **/del**. Saves CTLs when used with **/put**.</span></span> <span data-ttu-id="aaa95-143">Muestra listas CTL cuando se usa sin la opción **/add**, **/del** o **/put**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-143">Displays CTLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="aaa95-144">**/del**</span><span class="sxs-lookup"><span data-stu-id="aaa95-144">**/del**</span></span>|<span data-ttu-id="aaa95-145">Elimina certificados, listas CTL y listas CRL de un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="aaa95-145">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>|  
|<span data-ttu-id="aaa95-146">**/e** *encodingType*</span><span class="sxs-lookup"><span data-stu-id="aaa95-146">**/e** *encodingType*</span></span>|<span data-ttu-id="aaa95-147">Especifica el tipo de codificación de los certificados.</span><span class="sxs-lookup"><span data-stu-id="aaa95-147">Specifies the certificate encoding type.</span></span> <span data-ttu-id="aaa95-148">De manera predeterminada, es `X509_ASN_ENCODING`.</span><span class="sxs-lookup"><span data-stu-id="aaa95-148">The default is `X509_ASN_ENCODING`.</span></span>|  
|<span data-ttu-id="aaa95-149">**/f** *dwFlags*</span><span class="sxs-lookup"><span data-stu-id="aaa95-149">**/f** *dwFlags*</span></span>|<span data-ttu-id="aaa95-150">Especifica la marca usada para la apertura del almacén.</span><span class="sxs-lookup"><span data-stu-id="aaa95-150">Specifies the store open flag.</span></span> <span data-ttu-id="aaa95-151">Se trata del parámetro *dwFlags* que se pasa a **CertOpenStore**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-151">This is the *dwFlags* parameter passed to **CertOpenStore**.</span></span> <span data-ttu-id="aaa95-152">El valor predeterminado es CERT_SYSTEM_STORE_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="aaa95-152">The default value is CERT_SYSTEM_STORE_CURRENT_USER.</span></span> <span data-ttu-id="aaa95-153">Esta opción solo se tiene en cuenta si se usa la opción **/y**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-153">This option is considered only if the **/y** option is used.</span></span>|  
|<span data-ttu-id="aaa95-154">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="aaa95-154">**/h**[**elp**]</span></span>|<span data-ttu-id="aaa95-155">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="aaa95-155">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="aaa95-156">**/n** *nam*</span><span class="sxs-lookup"><span data-stu-id="aaa95-156">**/n** *nam*</span></span>|<span data-ttu-id="aaa95-157">Especifica el nombre común del certificado que se va a agregar, eliminar o guardar.</span><span class="sxs-lookup"><span data-stu-id="aaa95-157">Specifies the common name of the certificate to add, delete, or save.</span></span> <span data-ttu-id="aaa95-158">Esta opción solo se puede usar con certificados; no se puede usar con listas CTL ni listas CRL.</span><span class="sxs-lookup"><span data-stu-id="aaa95-158">This option can only be used with certificates; it cannot be used with CTLs or CRLs.</span></span>|  
|<span data-ttu-id="aaa95-159">**/put**</span><span class="sxs-lookup"><span data-stu-id="aaa95-159">**/put**</span></span>|<span data-ttu-id="aaa95-160">Guarda en un archivo un certificado X.509, una lista CTL o una lista CRL procedente de un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="aaa95-160">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span> <span data-ttu-id="aaa95-161">El archivo se guarda en formato X.509.</span><span class="sxs-lookup"><span data-stu-id="aaa95-161">The file is saved in X.509 format.</span></span> <span data-ttu-id="aaa95-162">Puede usar la opción **/7** con la opción **/put** para guardar el archivo en formato PKCS #7.</span><span class="sxs-lookup"><span data-stu-id="aaa95-162">You can use the **/7** option with the **/put** option to save the file in PKCS #7 format.</span></span> <span data-ttu-id="aaa95-163">La opción **/put** debe ir seguida de **/c**, **/CTL** o **/CRL**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-163">The **/put** option must be followed by either **/c**, **/CTL**, or **/CRL**.</span></span> <span data-ttu-id="aaa95-164">La opción **/all** no se puede usar con la opción **/put**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-164">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="aaa95-165">**/r** *location*</span><span class="sxs-lookup"><span data-stu-id="aaa95-165">**/r** *location*</span></span>|<span data-ttu-id="aaa95-166">Identifica la ubicación del Registro del almacén del sistema.</span><span class="sxs-lookup"><span data-stu-id="aaa95-166">Identifies the registry location of the system store.</span></span> <span data-ttu-id="aaa95-167">Esta opción solo se tiene en cuenta si se especifica la opción **/s**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-167">This option is considered only if you specify the **/s** option.</span></span> <span data-ttu-id="aaa95-168">*location* debe ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="aaa95-168">*location* must be one of the following:</span></span><br /><br /> <span data-ttu-id="aaa95-169">-   `currentUser` indica que el almacén de certificados está bajo la clave HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="aaa95-169">-   `currentUser` indicates that the certificate store is under the HKEY_CURRENT_USER key.</span></span> <span data-ttu-id="aaa95-170">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="aaa95-170">This is the default.</span></span><br /><span data-ttu-id="aaa95-171">-   `localMachine` indica que el almacén de certificados está bajo la clave HKEY_LOCAL_MACHINE.</span><span class="sxs-lookup"><span data-stu-id="aaa95-171">-   `localMachine` indicates that the certificate store is under the HKEY_LOCAL_MACHINE key.</span></span>|  
|<span data-ttu-id="aaa95-172">**/s**</span><span class="sxs-lookup"><span data-stu-id="aaa95-172">**/s**</span></span>|<span data-ttu-id="aaa95-173">Indica que el almacén de certificados es un almacén del sistema.</span><span class="sxs-lookup"><span data-stu-id="aaa95-173">Indicates that the certificate store is a system store.</span></span> <span data-ttu-id="aaa95-174">Si no especifica esta opción, se considera que el tipo del almacén es **StoreFile**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-174">If you do not specify this option, the store is considered to be a **StoreFile**.</span></span>|  
|<span data-ttu-id="aaa95-175">**/sha1** *sha1Hash*</span><span class="sxs-lookup"><span data-stu-id="aaa95-175">**/sha1** *sha1Hash*</span></span>|<span data-ttu-id="aaa95-176">Especifica el hash SHA1 del certificado, la lista CTL o la lista CRL que se va a agregar, eliminar o guardar.</span><span class="sxs-lookup"><span data-stu-id="aaa95-176">Specifies the SHA1 hash of the certificate, CTL, or CRL to add, delete, or save.</span></span>|  
|<span data-ttu-id="aaa95-177">**/v**</span><span class="sxs-lookup"><span data-stu-id="aaa95-177">**/v**</span></span>|<span data-ttu-id="aaa95-178">Especifica el modo detallado. Muestra información detallada sobre loa certificados, las listas CTL y las listas CRL.</span><span class="sxs-lookup"><span data-stu-id="aaa95-178">Specifies verbose mode; displays detailed information about certificates, CTLs, and CRLs.</span></span> <span data-ttu-id="aaa95-179">Esta opción no se puede usar con las opciones **/add**, **/del** o **/put**.</span><span class="sxs-lookup"><span data-stu-id="aaa95-179">This option cannot be used with the **/add**, **/del**, or **/put** options.</span></span>|  
|<span data-ttu-id="aaa95-180">**/y** *provider*</span><span class="sxs-lookup"><span data-stu-id="aaa95-180">**/y** *provider*</span></span>|<span data-ttu-id="aaa95-181">Especifica el nombre del proveedor de almacén.</span><span class="sxs-lookup"><span data-stu-id="aaa95-181">Specifies the store provider name.</span></span>|  
|<span data-ttu-id="aaa95-182">**/7**</span><span class="sxs-lookup"><span data-stu-id="aaa95-182">**/7**</span></span>|<span data-ttu-id="aaa95-183">Guarda el almacén de destino como un objeto PKCS #7.</span><span class="sxs-lookup"><span data-stu-id="aaa95-183">Saves the destination store as a PKCS #7 object.</span></span>|  
|<span data-ttu-id="aaa95-184">**/?**</span><span class="sxs-lookup"><span data-stu-id="aaa95-184">**/?**</span></span>|<span data-ttu-id="aaa95-185">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="aaa95-185">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aaa95-186">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aaa95-186">Remarks</span></span>  
 <span data-ttu-id="aaa95-187">Certmgr.exe realiza las funciones básicas siguientes:</span><span class="sxs-lookup"><span data-stu-id="aaa95-187">Certmgr.exe performs the following basic functions:</span></span>  
  
-   <span data-ttu-id="aaa95-188">Muestra certificados, listas CTL y listas CRL en la consola.</span><span class="sxs-lookup"><span data-stu-id="aaa95-188">Displays certificates, CTLs, and CRLs to the console.</span></span>  
  
-   <span data-ttu-id="aaa95-189">Agrega certificados, listas CTL y listas CRL a un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="aaa95-189">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>  
  
-   <span data-ttu-id="aaa95-190">Elimina certificados, listas CTL y listas CRL de un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="aaa95-190">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>  
  
-   <span data-ttu-id="aaa95-191">Guarda en un archivo un certificado X.509, una lista CTL o una lista CRL procedente de un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="aaa95-191">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span>  
  
 <span data-ttu-id="aaa95-192">Certmgr.exe funciona con dos tipos de almacenes de certificados: **StoreFile** y almacén del sistema.</span><span class="sxs-lookup"><span data-stu-id="aaa95-192">Certmgr.exe works with two types of certificate stores: **StoreFile** and system store.</span></span> <span data-ttu-id="aaa95-193">No es necesario especificar el tipo de almacén de certificados; Certmgr.exe puede identificarlo y realizar las operaciones apropiadas.</span><span class="sxs-lookup"><span data-stu-id="aaa95-193">It is not necessary to specify the type of certificate store; Certmgr.exe can identify the store type and perform the appropriate operations.</span></span>  
  
 <span data-ttu-id="aaa95-194">Cuando se ejecuta Certmgr.exe sin especificar ninguna opción, se inicia el complemento certmgr.msc, que dispone de una interfaz gráfica de usuario (GUI) que permite realizar las tareas de administración de certificados que también están disponibles desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="aaa95-194">Running Certmgr.exe without specifying any options launches the certmgr.msc snap-in, which has a GUI that helps with the certificate management tasks that are also available from the command line.</span></span> <span data-ttu-id="aaa95-195">La GUI proporciona un asistente para importación que copia certificados, listas CTL y listas CRL del disco en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="aaa95-195">The GUI provides an import wizard, which copies certificates, CTLs, and CRLs from your disk to a certificate store.</span></span>  
  
 <span data-ttu-id="aaa95-196">Para buscar los nombres de los almacenes de elementos X509Certificate para los parámetros `sourceStorename` y `destinationStorename`, compile y ejecute el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="aaa95-196">You can find the names of X509Certificate stores for the `sourceStorename` and `destinationStorename` parameters by compiling and running the following code.</span></span>  
  
 [!code-csharp[Tools.CertMgr#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tools.certmgr/cs/storenames1.cs#1)]
 [!code-vb[Tools.CertMgr#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tools.certmgr/vb/storenames1.vb#1)]  
  
 <span data-ttu-id="aaa95-197">Para más información, consulte [Trabajar con certificados](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="aaa95-197">For more information about certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="aaa95-198">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="aaa95-198">Examples</span></span>  
 <span data-ttu-id="aaa95-199">El comando siguiente muestra un almacén del sistema predeterminado denominado `my` con salida detallada.</span><span class="sxs-lookup"><span data-stu-id="aaa95-199">The following command displays a default system store called `my` with verbose output.</span></span>  
  
```  
certmgr /v /s my  
```  
  
 <span data-ttu-id="aaa95-200">El comando siguiente agrega todos los certificados de un archivo denominado `myFile.ext` a un archivo nuevo denominado `newFile.ext`.</span><span class="sxs-lookup"><span data-stu-id="aaa95-200">The following command adds all the certificates in a file called `myFile.ext` to a new file called `newFile.ext`.</span></span>  
  
```  
certmgr /add /all /c myFile.ext newFile.ext  
```  
  
 <span data-ttu-id="aaa95-201">El comando siguiente agrega el certificado de un archivo denominado `testcert.cer` al almacén del sistema `my`.</span><span class="sxs-lookup"><span data-stu-id="aaa95-201">The following command adds the certificate in a file named `testcert.cer` to the `my` system store.</span></span>  
  
```  
certmgr /add /c testcert.cer /s my  
```  
  
 <span data-ttu-id="aaa95-202">El comando siguiente agrega el certificado de un archivo denominado `TrustedCert.cer` al almacén de certificados raíz.</span><span class="sxs-lookup"><span data-stu-id="aaa95-202">The following command adds the certificate in a file named `TrustedCert.cer` to the root certificate store.</span></span>  
  
```  
certmgr /c /add TrustedCert.cer /s root  
```  
  
 <span data-ttu-id="aaa95-203">El comando siguiente guarda un certificado con el nombre común `myCert` del almacén del sistema `my` en un archivo denominado `newCert.cer`.</span><span class="sxs-lookup"><span data-stu-id="aaa95-203">The following command saves a certificate with the common name `myCert` in the `my` system store to a file called `newCert.cer`.</span></span>  
  
```  
certmgr /add /c /n myCert /s my newCert.cer  
```  
  
 <span data-ttu-id="aaa95-204">El comando siguiente elimina todas las listas CTL del almacén del sistema `my` y guarda el almacén resultante en un archivo denominado `newStore.str`.</span><span class="sxs-lookup"><span data-stu-id="aaa95-204">The following command deletes all CTLs in the `my` system store and saves the resulting store to a file called `newStore.str`.</span></span>  
  
```  
certmgr /del /all /ctl /s my newStore.str  
```  
  
 <span data-ttu-id="aaa95-205">El comando siguiente guarda un certificado del almacén del sistema `my` en el archivo `newFile`.</span><span class="sxs-lookup"><span data-stu-id="aaa95-205">The following command saves a certificate in the `my` system store in the file `newFile`.</span></span> <span data-ttu-id="aaa95-206">Se le pedirá que especifique el número del certificado de `my` para colocarlo en `newFile`.</span><span class="sxs-lookup"><span data-stu-id="aaa95-206">You will be prompted to enter the certificate number from `my` to put in `newFile`.</span></span>  
  
```  
certmgr /put /c /s my newFile  
```  
  
## <a name="see-also"></a><span data-ttu-id="aaa95-207">Vea también</span><span class="sxs-lookup"><span data-stu-id="aaa95-207">See also</span></span>
- [<span data-ttu-id="aaa95-208">Herramientas</span><span class="sxs-lookup"><span data-stu-id="aaa95-208">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="aaa95-209">Makecert.exe (Herramienta de creación de certificados)</span><span class="sxs-lookup"><span data-stu-id="aaa95-209">Makecert.exe (Certificate Creation Tool)</span></span>](/windows/desktop/SecCrypto/makecert)
- [<span data-ttu-id="aaa95-210">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="aaa95-210">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
