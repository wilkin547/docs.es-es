---
description: -win32manifest (Opciones del compilador de C#)
title: -win32manifest (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /win32manifest
helpviewer_keywords:
- /win32manifest compiler option [C#]
- win32manifest compiler option [C#]
- -win32manifest compiler option [C#]
ms.assetid: 9460ea1b-6c9f-44b8-8f73-301b30a01de1
ms.openlocfilehash: 1d2eefdab433f67e1cba5f709a2db8ec6b9a5dc7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171317"
---
# <a name="-win32manifest-c-compiler-options"></a><span data-ttu-id="4cf13-103">-win32manifest (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="4cf13-103">-win32manifest (C# Compiler Options)</span></span>

<span data-ttu-id="4cf13-104">Use la opción **-win32manifest** para identificar un archivo de manifiesto de aplicación Win32 definido por el usuario que se va a incluir en un archivo portable ejecutable (PE) del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4cf13-104">Use the **-win32manifest** option to specify a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cf13-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4cf13-105">Syntax</span></span>  
  
```console  
-win32manifest: filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="4cf13-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4cf13-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="4cf13-107">Nombre y ubicación del archivo de manifiesto personalizado.</span><span class="sxs-lookup"><span data-stu-id="4cf13-107">The name and location of the custom manifest file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cf13-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4cf13-108">Remarks</span></span>  

 <span data-ttu-id="4cf13-109">De forma predeterminada, el compilador de Visual C# inserta un manifiesto de aplicación que especifica un nivel de ejecución solicitado de "asInvoker".</span><span class="sxs-lookup"><span data-stu-id="4cf13-109">By default, the Visual C# compiler embeds an application manifest that specifies a requested execution level of "asInvoker."</span></span> <span data-ttu-id="4cf13-110">Crea el manifiesto en la misma carpeta en la que se ha compilado el archivo ejecutable, normalmente la carpeta bin\Debug o bin\Release cuando se usa Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4cf13-110">It creates the manifest in the same folder in which the executable is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="4cf13-111">Si quiere proporcionar un manifiesto personalizado, por ejemplo para especificar un nivel de ejecución solicitado de "highestAvailable" o "requireAdministrator", use esta opción para especificar el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="4cf13-111">If you want to supply a custom manifest, for example to specify a requested execution level of "highestAvailable" or "requireAdministrator," use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4cf13-112">Esta opción y [-win32res (Opciones del compilador de C#)](./win32res-compiler-option.md) son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="4cf13-112">This option and the [-win32res (C# Compiler Options)](./win32res-compiler-option.md) option are mutually exclusive.</span></span> <span data-ttu-id="4cf13-113">Si intenta usar ambas en la misma línea de comandos, obtendrá un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="4cf13-113">If you try to use both options in the same command line you will get a build error.</span></span>  
  
 <span data-ttu-id="4cf13-114">Una aplicación sin manifiesto de aplicación que especifique un nivel de ejecución solicitado estará sujeta a virtualización de archivos y Registro conforme a la característica Control de cuentas de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="4cf13-114">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows.</span></span> <span data-ttu-id="4cf13-115">Para más información, vea [User Account Control](/windows/access-protection/user-account-control/user-account-control-overview) (Control de cuentas de usuario).</span><span class="sxs-lookup"><span data-stu-id="4cf13-115">For more information, see [User Account Control](/windows/access-protection/user-account-control/user-account-control-overview).</span></span>  
  
 <span data-ttu-id="4cf13-116">La aplicación estará sujeta a virtualización si se cumple cualquiera de estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="4cf13-116">Your application will be subject to virtualization if either of these conditions is true:</span></span>  
  
- <span data-ttu-id="4cf13-117">Se usa la opción **-nowin32manifest** y no se proporciona ningún manifiesto en un paso de compilación posterior o como parte de un archivo de recursos de Windows (.res) mediante la opción **-win32res**.</span><span class="sxs-lookup"><span data-stu-id="4cf13-117">You use the **-nowin32manifest** option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the **-win32res** option.</span></span>  
  
- <span data-ttu-id="4cf13-118">Se proporciona un manifiesto personalizado que no especifica un nivel de ejecución solicitado.</span><span class="sxs-lookup"><span data-stu-id="4cf13-118">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 <span data-ttu-id="4cf13-119">Visual Studio crea un archivo de manifiesto predeterminado y lo almacena en los directorios de depuración y versión junto con el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="4cf13-119">Visual Studio creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="4cf13-120">Puede agregar un manifiesto personalizado si crea uno en cualquier editor de texto y luego lo agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="4cf13-120">You can add a custom manifest by creating one in any text editor and then adding the file to the project.</span></span> <span data-ttu-id="4cf13-121">También puede hacer clic con el botón derecho en el icono **Proyecto** del **Explorador de soluciones**, hacer clic en **Agregar nuevo elemento** y luego en **Archivo de manifiesto de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="4cf13-121">Alternatively, you can right-click the **Project** icon in **Solution Explorer**, click **Add New Item**, and then click **Application Manifest File**.</span></span> <span data-ttu-id="4cf13-122">Después de haber agregado el archivo de manifiesto nuevo o existente, aparecerá en la lista desplegable **Manifiesto**.</span><span class="sxs-lookup"><span data-stu-id="4cf13-122">After you have added your new or existing manifest file, it will appear in the **Manifest** drop down list.</span></span> <span data-ttu-id="4cf13-123">Para más información, vea [Página de aplicación, Diseñador de proyectos (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="4cf13-123">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="4cf13-124">Puede proporcionar el manifiesto de aplicación como un paso personalizado posterior a la compilación o como parte de un archivo de recursos Win32 mediante la opción [-nowin32manifest (Opciones del compilador de C#)](./nowin32manifest-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="4cf13-124">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the [-nowin32manifest (C# Compiler Options)](./nowin32manifest-compiler-option.md) option.</span></span> <span data-ttu-id="4cf13-125">Use esa misma opción si quiere que la aplicación esté sujeta a virtualización de archivos y Registro en Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="4cf13-125">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="4cf13-126">Esto evitará que el compilador cree e incruste un manifiesto predeterminado en el archivo portable ejecutable (PE).</span><span class="sxs-lookup"><span data-stu-id="4cf13-126">This will prevent the compiler from creating and embedding a default manifest in the portable executable (PE) file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cf13-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4cf13-127">Example</span></span>  

 <span data-ttu-id="4cf13-128">En el ejemplo siguiente se muestra el manifiesto predeterminado que el compilador de Visual C# inserta en un archivo PE.</span><span class="sxs-lookup"><span data-stu-id="4cf13-128">The following example shows the default manifest that the Visual C# compiler inserts into a PE.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4cf13-129">El compilador inserta un nombre de aplicación estándar "MyApplication.app" en el archivo xml.</span><span class="sxs-lookup"><span data-stu-id="4cf13-129">The compiler inserts a standard application name " MyApplication.app " into the xml.</span></span> <span data-ttu-id="4cf13-130">Se trata de una solución alternativa para permitir que las aplicaciones se ejecuten en Windows Server 2003 Service Pack 3.</span><span class="sxs-lookup"><span data-stu-id="4cf13-130">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4cf13-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cf13-131">See also</span></span>

- [<span data-ttu-id="4cf13-132">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="4cf13-132">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="4cf13-133">-nowin32manifest (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="4cf13-133">-nowin32manifest (C# Compiler Options)</span></span>](./nowin32manifest-compiler-option.md)
- [<span data-ttu-id="4cf13-134">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="4cf13-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
