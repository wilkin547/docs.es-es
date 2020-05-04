---
title: -win32manifest
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: cef1e6c19e7fdd6fc9f42c8fc36008314ea80a80
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349129"
---
# <a name="-win32manifest-visual-basic"></a><span data-ttu-id="4396e-102">-win32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4396e-102">-win32manifest (Visual Basic)</span></span>
<span data-ttu-id="4396e-103">Identifica un archivo de manifiesto de la aplicación Win32 definido por el usuario que se va a insertar en un archivo ejecutable portable (PE) del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4396e-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4396e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4396e-104">Syntax</span></span>  
  
```console  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="4396e-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4396e-105">Arguments</span></span>  
  
|<span data-ttu-id="4396e-106">Término</span><span class="sxs-lookup"><span data-stu-id="4396e-106">Term</span></span>|<span data-ttu-id="4396e-107">Definición</span><span class="sxs-lookup"><span data-stu-id="4396e-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="4396e-108">Ruta de acceso al archivo de manifiesto personalizado.</span><span class="sxs-lookup"><span data-stu-id="4396e-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4396e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4396e-109">Remarks</span></span>  
 <span data-ttu-id="4396e-110">El compilador de Visual Basic inserta de forma predeterminada un manifiesto de aplicación que especifica un nivel de ejecución solicitado de asInvoker.</span><span class="sxs-lookup"><span data-stu-id="4396e-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="4396e-111">Crea el manifiesto en la misma carpeta en la que se ha compilado el archivo ejecutable, normalmente la carpeta bin\Debug o bin\Release cuando se usa Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4396e-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="4396e-112">Si quiere proporcionar un manifiesto personalizado, por ejemplo para especificar un nivel de ejecución solicitado de highestAvailable o requireAdministrator, use esta opción para especificar el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="4396e-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4396e-113">Esta opción y [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="4396e-113">This option and the [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="4396e-114">Si intenta usar ambas en la misma línea de comandos, obtendrá un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="4396e-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="4396e-115">Una aplicación sin manifiesto de aplicación que especifique un nivel de ejecución solicitado estará sujeta a virtualización de archivos y Registro conforme a la característica Control de cuentas de usuario de Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="4396e-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="4396e-116">Para más información sobre la virtualización, vea [Implementación de ClickOnce en Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span><span class="sxs-lookup"><span data-stu-id="4396e-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="4396e-117">La aplicación estará sujeta a virtualización si se cumple cualquiera de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="4396e-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1. <span data-ttu-id="4396e-118">Se usa la opción `-nowin32manifest` y no se proporciona ningún manifiesto en un paso de compilación posterior o como parte de un archivo de recursos de Windows (.res) con la opción `-win32resource`.</span><span class="sxs-lookup"><span data-stu-id="4396e-118">You use the `-nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `-win32resource` option.</span></span>  
  
2. <span data-ttu-id="4396e-119">Se proporciona un manifiesto personalizado que no especifica un nivel de ejecución solicitado.</span><span class="sxs-lookup"><span data-stu-id="4396e-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 <span data-ttu-id="4396e-120">Visual Studio crea un archivo de manifiesto predeterminado y lo almacena en los directorios de depuración y versión junto con el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="4396e-120">Visual Studio creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="4396e-121">Para ver o editar el archivo app.manifest predeterminado, haga clic en **Ver configuración de UAC** en la pestaña **Aplicación** del Diseñador de proyectos.</span><span class="sxs-lookup"><span data-stu-id="4396e-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="4396e-122">Para obtener más información, consulte [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="4396e-122">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="4396e-123">Puede proporcionar el manifiesto de aplicación como un paso personalizado posterior a la compilación o como parte de un archivo de recursos Win32 con la opción `-nowin32manifest`.</span><span class="sxs-lookup"><span data-stu-id="4396e-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `-nowin32manifest` option.</span></span> <span data-ttu-id="4396e-124">Use esa misma opción si quiere que la aplicación esté sujeta a virtualización de archivos y Registro en Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="4396e-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="4396e-125">Esto evitará que el compilador cree e incruste un manifiesto predeterminado en el archivo PE.</span><span class="sxs-lookup"><span data-stu-id="4396e-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4396e-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4396e-126">Example</span></span>  
 <span data-ttu-id="4396e-127">En el siguiente ejemplo se muestra el manifiesto predeterminado que el compilador de Visual Basic inserta en un archivo PE.</span><span class="sxs-lookup"><span data-stu-id="4396e-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4396e-128">El compilador inserta un nombre de aplicación estándar MyApplication.app en el archivo XML de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="4396e-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="4396e-129">Se trata de una solución alternativa para permitir que las aplicaciones se ejecuten en Windows Server 2003 Service Pack 3.</span><span class="sxs-lookup"><span data-stu-id="4396e-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4396e-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="4396e-130">See also</span></span>

- [<span data-ttu-id="4396e-131">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4396e-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4396e-132">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4396e-132">-nowin32manifest (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
