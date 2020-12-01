---
title: Certmgr.exe (Herramienta de administración de certificados)
description: Explore Certmgr.exe, la herramienta Administrador de certificados. Esta herramienta administra certificados, listas de certificados de confianza (CTL) y listas de revocaciones de certificados (CRL).
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
ms.openlocfilehash: 30a35ded6fc86af6dc6dd4bf19cdf60f66570e0c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247257"
---
# <a name="certmgrexe-certificate-manager-tool"></a><span data-ttu-id="97bf5-104">Certmgr.exe (Herramienta de administración de certificados)</span><span class="sxs-lookup"><span data-stu-id="97bf5-104">Certmgr.exe (Certificate Manager Tool)</span></span>

<span data-ttu-id="97bf5-105">El administrador de certificados (Certmgr.exe) es una herramienta que administra certificados, listas de certificados de confianza (CTL) y listas de revocación de certificados (CRL).</span><span class="sxs-lookup"><span data-stu-id="97bf5-105">The Certificate Manager tool (Certmgr.exe) manages certificates, certificate trust lists (CTLs), and certificate revocation lists (CRLs).</span></span>  
  
 <span data-ttu-id="97bf5-106">El administrador de certificados se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="97bf5-106">The Certificate Manager is automatically installed with Visual Studio.</span></span> <span data-ttu-id="97bf5-107">Para iniciar la herramienta, use los [símbolos del sistema](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="97bf5-107">To start the tool, use the [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="97bf5-108">El administrador de certificados (Certmgr.exe) es una utilidad de línea de comandos, mientras que Certificados (Certmgr.msc) es un complemento MMC (Microsoft Management Console).</span><span class="sxs-lookup"><span data-stu-id="97bf5-108">The Certificate Manager tool (Certmgr.exe) is a command-line utility, whereas Certificates (Certmgr.msc) is a Microsoft Management Console (MMC) snap-in.</span></span> <span data-ttu-id="97bf5-109">Dado que Certmgr.msc se encuentra normalmente en el directorio del sistema Windows, al escribir `certmgr` en la línea de comandos, es posible que se cargue el complemento MMC Certificados, incluso si ha abierto Símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="97bf5-109">Because Certmgr.msc is usually found in the Windows System directory, entering `certmgr` at the command line may load the Certificates MMC snap-in even if you have opened the Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="97bf5-110">Esto ocurre porque la ruta de acceso al complemento precede a la ruta de acceso al administrador de certificados en la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="97bf5-110">This occurs because the path to the snap-in precedes the path to the Certificate Manager tool in the PATH environment variable.</span></span> <span data-ttu-id="97bf5-111">Si se produce este problema, puede ejecutar los comandos de Certmgr.exe especificando la ruta de acceso al archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="97bf5-111">If you encounter this problem, you can execute Certmgr.exe commands by specifying the path to the executable.</span></span>  
  
 <span data-ttu-id="97bf5-112">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="97bf5-112">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="97bf5-113">Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="97bf5-113">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="97bf5-114">Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="97bf5-114">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="97bf5-115">Para información general sobre los certificados X.509, consulte [Trabajar con certificados](../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="97bf5-115">For an overview of X.509 certificates, see [Working with Certificates](../wcf/feature-details/working-with-certificates.md).</span></span>  
  
 <span data-ttu-id="97bf5-116">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="97bf5-116">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97bf5-117">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97bf5-117">Syntax</span></span>  
  
```console  
      certmgr [/add | /del | /put] [options]  
[/s[/r registryLocation]] [sourceStorename]  
[/s[/r registryLocation]] [destinationStorename]  
```  
  
## <a name="parameters"></a><span data-ttu-id="97bf5-118">Parámetros</span><span class="sxs-lookup"><span data-stu-id="97bf5-118">Parameters</span></span>  
  
|<span data-ttu-id="97bf5-119">Argumento</span><span class="sxs-lookup"><span data-stu-id="97bf5-119">Argument</span></span>|<span data-ttu-id="97bf5-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="97bf5-120">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="97bf5-121">*sourceStorename*</span><span class="sxs-lookup"><span data-stu-id="97bf5-121">*sourceStorename*</span></span>|<span data-ttu-id="97bf5-122">El almacén de certificados que contiene los certificados, las CTL o las CRL existentes que se van a agregar, eliminar, guardar o mostrar.</span><span class="sxs-lookup"><span data-stu-id="97bf5-122">The certificate store that contains the existing certificates, CTLs, or CRLs to add, delete, save, or display.</span></span> <span data-ttu-id="97bf5-123">Puede ser un archivo de almacén o un almacén del sistema.</span><span class="sxs-lookup"><span data-stu-id="97bf5-123">This can be a store file or a systems store.</span></span>|  
|<span data-ttu-id="97bf5-124">*destinationStorename*</span><span class="sxs-lookup"><span data-stu-id="97bf5-124">*destinationStorename*</span></span>|<span data-ttu-id="97bf5-125">El archivo o el almacén de certificados de salida.</span><span class="sxs-lookup"><span data-stu-id="97bf5-125">The output certificate store or file.</span></span>|  
  
|<span data-ttu-id="97bf5-126">Opción</span><span class="sxs-lookup"><span data-stu-id="97bf5-126">Option</span></span>|<span data-ttu-id="97bf5-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="97bf5-127">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="97bf5-128">**/add**</span><span class="sxs-lookup"><span data-stu-id="97bf5-128">**/add**</span></span>|<span data-ttu-id="97bf5-129">Agrega certificados, listas CTL y listas CRL a un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="97bf5-129">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>|  
|<span data-ttu-id="97bf5-130">**/all**</span><span class="sxs-lookup"><span data-stu-id="97bf5-130">**/all**</span></span>|<span data-ttu-id="97bf5-131">Agrega todas las entradas cuando se usa con la opción **/add**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-131">Adds all entries when used with **/add**.</span></span> <span data-ttu-id="97bf5-132">Elimina todas las entradas cuando se usa con la opción **/delete**. Muestra todas las entradas cuando se usa sin la opción **/add** o **/del**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-132">Deletes all entries when used with **/del**. Displays all entries when used without the **/add** or **/del** options.</span></span> <span data-ttu-id="97bf5-133">La opción **/all** no se puede usar con la opción **/put**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-133">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="97bf5-134">**/c**</span><span class="sxs-lookup"><span data-stu-id="97bf5-134">**/c**</span></span>|<span data-ttu-id="97bf5-135">Agrega certificados cuando se usa con la opción **/add**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-135">Adds certificates when used with **/add**.</span></span> <span data-ttu-id="97bf5-136">Elimina certificados cuando se usa con la opción **/delete**. Guarda certificados cuando se usa con la opción **/put**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-136">Deletes certificates when used with **/del**. Saves certificates when used with **/put**.</span></span> <span data-ttu-id="97bf5-137">Muestra certificados cuando se usa sin la opción **/add**, **/del** o **/put**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-137">Displays certificates when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="97bf5-138">**/CRL**</span><span class="sxs-lookup"><span data-stu-id="97bf5-138">**/CRL**</span></span>|<span data-ttu-id="97bf5-139">Agrega listas CRL cuando se usa con **/add**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-139">Adds CRLs when used with **/add**.</span></span> <span data-ttu-id="97bf5-140">Elimina listas CRL cuando se usa con **/del**. Guarda listas CRL cuando se usa con **/put**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-140">Deletes CRLs when used with **/del**. Saves CRLs when used with **/put**.</span></span> <span data-ttu-id="97bf5-141">Muestra listas CRL cuando se usa sin la opción **/add**, **/del** o **/put**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-141">Displays CRLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="97bf5-142">**/CTL**</span><span class="sxs-lookup"><span data-stu-id="97bf5-142">**/CTL**</span></span>|<span data-ttu-id="97bf5-143">Agrega listas CTL cuando se usa con **/add**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-143">Adds CTLs when used with **/add**.</span></span> <span data-ttu-id="97bf5-144">Elimina listas CTL cuando se usa con **/del**. Guarda listas CTL cuando se usa con **/put**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-144">Deletes CTLs when used with **/del**. Saves CTLs when used with **/put**.</span></span> <span data-ttu-id="97bf5-145">Muestra listas CTL cuando se usa sin la opción **/add**, **/del** o **/put**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-145">Displays CTLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="97bf5-146">**/del**</span><span class="sxs-lookup"><span data-stu-id="97bf5-146">**/del**</span></span>|<span data-ttu-id="97bf5-147">Elimina certificados, listas CTL y listas CRL de un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="97bf5-147">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>|  
|<span data-ttu-id="97bf5-148">**/e** *encodingType*</span><span class="sxs-lookup"><span data-stu-id="97bf5-148">**/e** *encodingType*</span></span>|<span data-ttu-id="97bf5-149">Especifica el tipo de codificación de los certificados.</span><span class="sxs-lookup"><span data-stu-id="97bf5-149">Specifies the certificate encoding type.</span></span> <span data-ttu-id="97bf5-150">De manera predeterminada, es `X509_ASN_ENCODING`.</span><span class="sxs-lookup"><span data-stu-id="97bf5-150">The default is `X509_ASN_ENCODING`.</span></span>|  
|<span data-ttu-id="97bf5-151">**/f** *dwFlags*</span><span class="sxs-lookup"><span data-stu-id="97bf5-151">**/f** *dwFlags*</span></span>|<span data-ttu-id="97bf5-152">Especifica la marca usada para la apertura del almacén.</span><span class="sxs-lookup"><span data-stu-id="97bf5-152">Specifies the store open flag.</span></span> <span data-ttu-id="97bf5-153">Se trata del parámetro *dwFlags* que se pasa a **CertOpenStore**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-153">This is the *dwFlags* parameter passed to **CertOpenStore**.</span></span> <span data-ttu-id="97bf5-154">El valor predeterminado es CERT_SYSTEM_STORE_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="97bf5-154">The default value is CERT_SYSTEM_STORE_CURRENT_USER.</span></span> <span data-ttu-id="97bf5-155">Esta opción solo se tiene en cuenta si se usa la opción **/y**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-155">This option is considered only if the **/y** option is used.</span></span>|  
|<span data-ttu-id="97bf5-156">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="97bf5-156">**/h**[**elp**]</span></span>|<span data-ttu-id="97bf5-157">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="97bf5-157">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="97bf5-158">**/n** *nam*</span><span class="sxs-lookup"><span data-stu-id="97bf5-158">**/n** *nam*</span></span>|<span data-ttu-id="97bf5-159">Especifica el nombre común del certificado que se va a agregar, eliminar o guardar.</span><span class="sxs-lookup"><span data-stu-id="97bf5-159">Specifies the common name of the certificate to add, delete, or save.</span></span> <span data-ttu-id="97bf5-160">Esta opción solo se puede usar con certificados; no se puede usar con listas CTL ni listas CRL.</span><span class="sxs-lookup"><span data-stu-id="97bf5-160">This option can only be used with certificates; it cannot be used with CTLs or CRLs.</span></span>|  
|<span data-ttu-id="97bf5-161">**/put**</span><span class="sxs-lookup"><span data-stu-id="97bf5-161">**/put**</span></span>|<span data-ttu-id="97bf5-162">Guarda en un archivo un certificado X.509, una lista CTL o una lista CRL procedente de un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="97bf5-162">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span> <span data-ttu-id="97bf5-163">El archivo se guarda en formato X.509.</span><span class="sxs-lookup"><span data-stu-id="97bf5-163">The file is saved in X.509 format.</span></span> <span data-ttu-id="97bf5-164">Puede usar la opción **/7** con la opción **/put** para guardar el archivo en formato PKCS #7.</span><span class="sxs-lookup"><span data-stu-id="97bf5-164">You can use the **/7** option with the **/put** option to save the file in PKCS #7 format.</span></span> <span data-ttu-id="97bf5-165">La opción **/put** debe ir seguida de **/c**, **/CTL** o **/CRL**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-165">The **/put** option must be followed by either **/c**, **/CTL**, or **/CRL**.</span></span> <span data-ttu-id="97bf5-166">La opción **/all** no se puede usar con la opción **/put**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-166">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="97bf5-167">**/r** *location*</span><span class="sxs-lookup"><span data-stu-id="97bf5-167">**/r** *location*</span></span>|<span data-ttu-id="97bf5-168">Identifica la ubicación del Registro del almacén del sistema.</span><span class="sxs-lookup"><span data-stu-id="97bf5-168">Identifies the registry location of the system store.</span></span> <span data-ttu-id="97bf5-169">Esta opción solo se tiene en cuenta si se especifica la opción **/s**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-169">This option is considered only if you specify the **/s** option.</span></span> <span data-ttu-id="97bf5-170">*location* debe ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="97bf5-170">*location* must be one of the following:</span></span><br /><br /> <span data-ttu-id="97bf5-171">-   `currentUser` indica que el almacén de certificados está bajo la clave HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="97bf5-171">-   `currentUser` indicates that the certificate store is under the HKEY_CURRENT_USER key.</span></span> <span data-ttu-id="97bf5-172">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="97bf5-172">This is the default.</span></span><br /><span data-ttu-id="97bf5-173">-   `localMachine` indica que el almacén de certificados está bajo la clave HKEY_LOCAL_MACHINE.</span><span class="sxs-lookup"><span data-stu-id="97bf5-173">-   `localMachine` indicates that the certificate store is under the HKEY_LOCAL_MACHINE key.</span></span>|  
|<span data-ttu-id="97bf5-174">**/s**</span><span class="sxs-lookup"><span data-stu-id="97bf5-174">**/s**</span></span>|<span data-ttu-id="97bf5-175">Indica que el almacén de certificados es un almacén del sistema.</span><span class="sxs-lookup"><span data-stu-id="97bf5-175">Indicates that the certificate store is a system store.</span></span> <span data-ttu-id="97bf5-176">Si no especifica esta opción, se considera que el tipo del almacén es **StoreFile**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-176">If you do not specify this option, the store is considered to be a **StoreFile**.</span></span>|  
|<span data-ttu-id="97bf5-177">**/sha1** *sha1Hash*</span><span class="sxs-lookup"><span data-stu-id="97bf5-177">**/sha1** *sha1Hash*</span></span>|<span data-ttu-id="97bf5-178">Especifica el hash SHA1 del certificado, la lista CTL o la lista CRL que se va a agregar, eliminar o guardar.</span><span class="sxs-lookup"><span data-stu-id="97bf5-178">Specifies the SHA1 hash of the certificate, CTL, or CRL to add, delete, or save.</span></span>|  
|<span data-ttu-id="97bf5-179">**/v**</span><span class="sxs-lookup"><span data-stu-id="97bf5-179">**/v**</span></span>|<span data-ttu-id="97bf5-180">Especifica el modo detallado. Muestra información detallada sobre loa certificados, las listas CTL y las listas CRL.</span><span class="sxs-lookup"><span data-stu-id="97bf5-180">Specifies verbose mode; displays detailed information about certificates, CTLs, and CRLs.</span></span> <span data-ttu-id="97bf5-181">Esta opción no se puede usar con las opciones **/add**, **/del** o **/put**.</span><span class="sxs-lookup"><span data-stu-id="97bf5-181">This option cannot be used with the **/add**, **/del**, or **/put** options.</span></span>|  
|<span data-ttu-id="97bf5-182">**/y** *provider*</span><span class="sxs-lookup"><span data-stu-id="97bf5-182">**/y** *provider*</span></span>|<span data-ttu-id="97bf5-183">Especifica el nombre del proveedor de almacén.</span><span class="sxs-lookup"><span data-stu-id="97bf5-183">Specifies the store provider name.</span></span>|  
|<span data-ttu-id="97bf5-184">**/7**</span><span class="sxs-lookup"><span data-stu-id="97bf5-184">**/7**</span></span>|<span data-ttu-id="97bf5-185">Guarda el almacén de destino como un objeto PKCS #7.</span><span class="sxs-lookup"><span data-stu-id="97bf5-185">Saves the destination store as a PKCS #7 object.</span></span>|  
|<span data-ttu-id="97bf5-186">**/?**</span><span class="sxs-lookup"><span data-stu-id="97bf5-186">**/?**</span></span>|<span data-ttu-id="97bf5-187">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="97bf5-187">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97bf5-188">Comentarios</span><span class="sxs-lookup"><span data-stu-id="97bf5-188">Remarks</span></span>  

 <span data-ttu-id="97bf5-189">Certmgr.exe realiza las funciones básicas siguientes:</span><span class="sxs-lookup"><span data-stu-id="97bf5-189">Certmgr.exe performs the following basic functions:</span></span>  
  
- <span data-ttu-id="97bf5-190">Muestra certificados, listas CTL y listas CRL en la consola.</span><span class="sxs-lookup"><span data-stu-id="97bf5-190">Displays certificates, CTLs, and CRLs to the console.</span></span>  
  
- <span data-ttu-id="97bf5-191">Agrega certificados, listas CTL y listas CRL a un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="97bf5-191">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>  
  
- <span data-ttu-id="97bf5-192">Elimina certificados, listas CTL y listas CRL de un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="97bf5-192">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>  
  
- <span data-ttu-id="97bf5-193">Guarda en un archivo un certificado X.509, una lista CTL o una lista CRL procedente de un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="97bf5-193">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span>  
  
 <span data-ttu-id="97bf5-194">Certmgr.exe funciona con dos tipos de almacenes de certificados: **StoreFile** y almacén del sistema.</span><span class="sxs-lookup"><span data-stu-id="97bf5-194">Certmgr.exe works with two types of certificate stores: **StoreFile** and system store.</span></span> <span data-ttu-id="97bf5-195">No es necesario especificar el tipo de almacén de certificados; Certmgr.exe puede identificarlo y realizar las operaciones apropiadas.</span><span class="sxs-lookup"><span data-stu-id="97bf5-195">It is not necessary to specify the type of certificate store; Certmgr.exe can identify the store type and perform the appropriate operations.</span></span>  
  
 <span data-ttu-id="97bf5-196">Cuando se ejecuta Certmgr.exe sin especificar ninguna opción, se inicia el complemento certmgr.msc, que dispone de una interfaz gráfica de usuario (GUI) que permite realizar las tareas de administración de certificados que también están disponibles desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="97bf5-196">Running Certmgr.exe without specifying any options launches the certmgr.msc snap-in, which has a GUI that helps with the certificate management tasks that are also available from the command line.</span></span> <span data-ttu-id="97bf5-197">La GUI proporciona un asistente para importación que copia certificados, listas CTL y listas CRL del disco en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="97bf5-197">The GUI provides an import wizard, which copies certificates, CTLs, and CRLs from your disk to a certificate store.</span></span>  
  
 <span data-ttu-id="97bf5-198">Para buscar los nombres de los almacenes de elementos X509Certificate para los parámetros `sourceStorename` y `destinationStorename`, compile y ejecute el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="97bf5-198">You can find the names of X509Certificate stores for the `sourceStorename` and `destinationStorename` parameters by compiling and running the following code.</span></span>  
  
 [!code-csharp[Tools.CertMgr#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tools.certmgr/cs/storenames1.cs#1)]
 [!code-vb[Tools.CertMgr#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tools.certmgr/vb/storenames1.vb#1)]  
  
 <span data-ttu-id="97bf5-199">Para más información, consulte [Trabajar con certificados](../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="97bf5-199">For more information about certificates, see [Working with Certificates](../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="97bf5-200">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="97bf5-200">Examples</span></span>  

 <span data-ttu-id="97bf5-201">El comando siguiente muestra un almacén del sistema predeterminado denominado `my` con salida detallada.</span><span class="sxs-lookup"><span data-stu-id="97bf5-201">The following command displays a default system store called `my` with verbose output.</span></span>  
  
```console  
certmgr /v /s my  
```  
  
 <span data-ttu-id="97bf5-202">El comando siguiente agrega todos los certificados de un archivo denominado `myFile.ext` a un archivo nuevo denominado `newFile.ext`.</span><span class="sxs-lookup"><span data-stu-id="97bf5-202">The following command adds all the certificates in a file called `myFile.ext` to a new file called `newFile.ext`.</span></span>  
  
```console  
certmgr /add /all /c myFile.ext newFile.ext  
```  
  
 <span data-ttu-id="97bf5-203">El comando siguiente agrega el certificado de un archivo denominado `testcert.cer` al almacén del sistema `my`.</span><span class="sxs-lookup"><span data-stu-id="97bf5-203">The following command adds the certificate in a file named `testcert.cer` to the `my` system store.</span></span>  
  
```console  
certmgr /add /c testcert.cer /s my  
```  
  
 <span data-ttu-id="97bf5-204">El comando siguiente agrega el certificado de un archivo denominado `TrustedCert.cer` al almacén de certificados raíz.</span><span class="sxs-lookup"><span data-stu-id="97bf5-204">The following command adds the certificate in a file named `TrustedCert.cer` to the root certificate store.</span></span>  
  
```console  
certmgr /c /add TrustedCert.cer /s root  
```  
  
 <span data-ttu-id="97bf5-205">El comando siguiente guarda un certificado con el nombre común `myCert` del almacén del sistema `my` en un archivo denominado `newCert.cer`.</span><span class="sxs-lookup"><span data-stu-id="97bf5-205">The following command saves a certificate with the common name `myCert` in the `my` system store to a file called `newCert.cer`.</span></span>  
  
```console  
certmgr /add /c /n myCert /s my newCert.cer  
```  
  
 <span data-ttu-id="97bf5-206">El comando siguiente elimina todas las listas CTL del almacén del sistema `my` y guarda el almacén resultante en un archivo denominado `newStore.str`.</span><span class="sxs-lookup"><span data-stu-id="97bf5-206">The following command deletes all CTLs in the `my` system store and saves the resulting store to a file called `newStore.str`.</span></span>  
  
```console  
certmgr /del /all /ctl /s my newStore.str  
```  
  
 <span data-ttu-id="97bf5-207">El comando siguiente guarda un certificado del almacén del sistema `my` en el archivo `newFile`.</span><span class="sxs-lookup"><span data-stu-id="97bf5-207">The following command saves a certificate in the `my` system store in the file `newFile`.</span></span> <span data-ttu-id="97bf5-208">Se le pedirá que especifique el número del certificado de `my` para colocarlo en `newFile`.</span><span class="sxs-lookup"><span data-stu-id="97bf5-208">You will be prompted to enter the certificate number from `my` to put in `newFile`.</span></span>  
  
```console  
certmgr /put /c /s my newFile  
```  
  
## <a name="see-also"></a><span data-ttu-id="97bf5-209">Vea también</span><span class="sxs-lookup"><span data-stu-id="97bf5-209">See also</span></span>

- [<span data-ttu-id="97bf5-210">Herramientas</span><span class="sxs-lookup"><span data-stu-id="97bf5-210">Tools</span></span>](index.md)
- [<span data-ttu-id="97bf5-211">Makecert.exe (Herramienta de creación de certificados)</span><span class="sxs-lookup"><span data-stu-id="97bf5-211">Makecert.exe (Certificate Creation Tool)</span></span>](/windows/desktop/SecCrypto/makecert)
- [<span data-ttu-id="97bf5-212">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="97bf5-212">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
