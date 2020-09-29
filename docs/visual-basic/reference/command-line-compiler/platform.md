---
title: -platform
ms.date: 03/13/2018
helpviewer_keywords:
- platform compiler option [Visual Basic]
- /platform compiler option [Visual Basic]
- -platform compiler option [Visual Basic]
ms.assetid: f9bc61e6-e854-4ae1-87b9-d6244de23fd1
ms.openlocfilehash: 488a1da6b25bcb4b42f0d355c6faee542046d0f5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91098896"
---
# <a name="-platform-visual-basic"></a><span data-ttu-id="15b0a-102">-platform (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15b0a-102">-platform (Visual Basic)</span></span>

<span data-ttu-id="15b0a-103">Especifica qué versión de la plataforma de Common Language Runtime (CLR) puede ejecutar el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="15b0a-103">Specifies which platform version of common language runtime (CLR) can run the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15b0a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15b0a-104">Syntax</span></span>  
  
```console  
-platform:{ x86 | x64 | Itanium | arm | anycpu | anycpu32bitpreferred }  
```  
  
## <a name="arguments"></a><span data-ttu-id="15b0a-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="15b0a-105">Arguments</span></span>  
  
|<span data-ttu-id="15b0a-106">Término</span><span class="sxs-lookup"><span data-stu-id="15b0a-106">Term</span></span>|<span data-ttu-id="15b0a-107">Definición</span><span class="sxs-lookup"><span data-stu-id="15b0a-107">Definition</span></span>|  
|---|---|  
|`x86`|<span data-ttu-id="15b0a-108">Compila el ensamblado de forma que el CLR de 32 bits compatible con x86 pueda ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="15b0a-108">Compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>|  
|`x64`|<span data-ttu-id="15b0a-109">Compila el ensamblado de forma que el CLR de 64 bits pueda ejecutarlo en equipos compatibles con el conjunto de instrucciones AMD64 o EM64T.</span><span class="sxs-lookup"><span data-stu-id="15b0a-109">Compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>|  
|`Itanium`|<span data-ttu-id="15b0a-110">Compila el ensamblado de forma que el CLR de 64 bits pueda ejecutarlo en un equipo con un procesador Itanium.</span><span class="sxs-lookup"><span data-stu-id="15b0a-110">Compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>|  
|`arm`|<span data-ttu-id="15b0a-111">Compila el ensamblado de forma que pueda ejecutarse en un equipo con un procesador ARM (Advanced RISC Machine).</span><span class="sxs-lookup"><span data-stu-id="15b0a-111">Compiles your assembly to be run on a computer with an ARM (Advanced RISC Machine) processor.</span></span>|  
|`anycpu`|<span data-ttu-id="15b0a-112">Compila el ensamblado de forma que pueda ejecutarse en cualquier plataforma.</span><span class="sxs-lookup"><span data-stu-id="15b0a-112">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="15b0a-113">La aplicación se ejecutará como una aplicación de 32 bits en versiones de 32 bits de Windows, y como una aplicación de 64 bits en versiones de 64 bits de Windows.</span><span class="sxs-lookup"><span data-stu-id="15b0a-113">The application will run as a 32-bit application on 32-bit versions of Windows and as a 64-bit application on 64-bit versions of Windows.</span></span> <span data-ttu-id="15b0a-114">Esta marca es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="15b0a-114">This flag is the default value.</span></span>|  
|`anycpu32bitpreferred`|<span data-ttu-id="15b0a-115">Compila el ensamblado de forma que pueda ejecutarse en cualquier plataforma.</span><span class="sxs-lookup"><span data-stu-id="15b0a-115">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="15b0a-116">La aplicación se ejecutará como una aplicación de 32 bits en versiones de 32 bits y de 64 bits de Windows.</span><span class="sxs-lookup"><span data-stu-id="15b0a-116">The application will run as a 32-bit application on both 32-bit and 64-bit versions of Windows.</span></span> <span data-ttu-id="15b0a-117">Esta marca solo es válida para ejecutables (.EXE) y requiere .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="15b0a-117">This flag is valid only for executables (.EXE) and requires .NET Framework 4.5.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15b0a-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15b0a-118">Remarks</span></span>  

 <span data-ttu-id="15b0a-119">Use la opción `-platform` para especificar el tipo de procesador de destino del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="15b0a-119">Use the `-platform` option to specify the type of processor targeted by the output file.</span></span>  
  
 <span data-ttu-id="15b0a-120">En general, los ensamblados de .NET Framework escritos en Visual Basic se ejecutarán de la misma manera independientemente de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="15b0a-120">In general, .NET Framework assemblies written in Visual Basic will run the same regardless of the platform.</span></span> <span data-ttu-id="15b0a-121">Sin embargo, en algunos casos se comportan de forma diferente en distintas plataformas.</span><span class="sxs-lookup"><span data-stu-id="15b0a-121">However, there are some cases that behave differently on different platforms.</span></span> <span data-ttu-id="15b0a-122">Estos casos comunes son:</span><span class="sxs-lookup"><span data-stu-id="15b0a-122">These common cases are:</span></span>  
  
- <span data-ttu-id="15b0a-123">Estructuras que contengan miembros cuyo tamaño varía según la plataforma, como cualquier tipo de puntero.</span><span class="sxs-lookup"><span data-stu-id="15b0a-123">Structures that contain members that change size depending on the platform, such as any pointer type.</span></span>  
  
- <span data-ttu-id="15b0a-124">Aritmética de punteros que incluya tamaños constantes.</span><span class="sxs-lookup"><span data-stu-id="15b0a-124">Pointer arithmetic that includes constant sizes.</span></span>  
  
- <span data-ttu-id="15b0a-125">Invocación incorrecta de la plataforma o declaraciones COM que utilicen `Integer` para los controladores en lugar de <xref:System.IntPtr>.</span><span class="sxs-lookup"><span data-stu-id="15b0a-125">Incorrect platform invoke or COM declarations that use `Integer` for handles instead of <xref:System.IntPtr>.</span></span>  
  
- <span data-ttu-id="15b0a-126">Conversión de <xref:System.IntPtr> a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="15b0a-126">Casting <xref:System.IntPtr> to `Integer`.</span></span>  
  
- <span data-ttu-id="15b0a-127">Uso de invocación de plataforma o interoperabilidad COM con componentes que no existen en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="15b0a-127">Using platform invoke or COM interop with components that do not exist on all platforms.</span></span>  
  
 <span data-ttu-id="15b0a-128">La opción **-platform** mitigará algunos problemas si ha realizado suposiciones sobre la arquitectura en la que se ejecutará el código.</span><span class="sxs-lookup"><span data-stu-id="15b0a-128">The **-platform** option will mitigate some issues if you know you have made assumptions about the architecture your code will run on.</span></span> <span data-ttu-id="15b0a-129">De manera específica:</span><span class="sxs-lookup"><span data-stu-id="15b0a-129">Specifically:</span></span>  
  
- <span data-ttu-id="15b0a-130">Si decide que el destino sea una plataforma de 64 bits pero la aplicación se ejecuta en un equipo de 32 bits, el mensaje de error aparece mucho antes y se centra más bien en el problema que en el error que aparece sin utilizar este modificador.</span><span class="sxs-lookup"><span data-stu-id="15b0a-130">If you decide to target a 64-bit platform, and the application is run on a 32-bit machine, the error message comes much earlier and is more targeted at the problem than the error that occurs without using this switch.</span></span>  
  
- <span data-ttu-id="15b0a-131">Si establece la marca `x86` en la opción y posteriormente la aplicación se ejecuta en un equipo de 64 bits, la aplicación se ejecutará en el subsistema WOW, en lugar de ejecutarse de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="15b0a-131">If you set the `x86` flag on the option and the application is subsequently run on a 64-bit machine, the application will run in the WOW subsystem instead of running natively.</span></span>  
  
 <span data-ttu-id="15b0a-132">En un sistema operativo de Windows de 64 bits:</span><span class="sxs-lookup"><span data-stu-id="15b0a-132">On a 64-bit Windows operating system:</span></span>  
  
- <span data-ttu-id="15b0a-133">Los ensamblados compilados con `-platform:x86` se ejecutarán en el CLR de 32 bits que se ejecuta en WOW64.</span><span class="sxs-lookup"><span data-stu-id="15b0a-133">Assemblies compiled with `-platform:x86` will execute on the 32-bit CLR running under WOW64.</span></span>  
  
- <span data-ttu-id="15b0a-134">Los ejecutables compilados con `-platform:anycpu` se ejecutarán en el CLR de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="15b0a-134">Executables compiled with the `-platform:anycpu` will execute on the 64-bit CLR.</span></span>  
  
- <span data-ttu-id="15b0a-135">Un archivo DLL compilado con `-platform:anycpu` se ejecutará en el mismo CLR que el proceso en el que se cargó.</span><span class="sxs-lookup"><span data-stu-id="15b0a-135">A DLL compiled with the `-platform:anycpu` will execute on the same CLR as the process into which it loaded.</span></span>  
  
- <span data-ttu-id="15b0a-136">Los archivos ejecutables que se compilan con `-platform:anycpu32bitpreferred` se ejecutarán en el CLR de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="15b0a-136">Executables that are compiled with `-platform:anycpu32bitpreferred` will execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="15b0a-137">Para obtener más información sobre cómo desarrollar una aplicación para que se ejecute en una versión de 64 bits de Windows, vea [Aplicaciones de 64 bits](../../../framework/64-bit-apps.md).</span><span class="sxs-lookup"><span data-stu-id="15b0a-137">For more information about how to develop an application to run on a 64-bit version of Windows, see [64-bit Applications](../../../framework/64-bit-apps.md).</span></span>  
  
### <a name="to-set--platform-in-the-visual-studio-ide"></a><span data-ttu-id="15b0a-138">Para establecer -platform en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="15b0a-138">To set -platform in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="15b0a-139">En el **Explorador de soluciones**, elija el proyecto, abra el menú **Proyecto** y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="15b0a-139">In **Solution Explorer**, choose the project, open the **Project** menu, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="15b0a-140">En la pestaña **Compilar**, active o desactive la casilla **Preferencia de 32 bits**, o bien elija un valor en la lista **CPU de destino**.</span><span class="sxs-lookup"><span data-stu-id="15b0a-140">On the **Compile** tab, select or clear the **Prefer 32-bit** check box, or, in the **Target CPU** list, choose a value.</span></span>  
  
     <span data-ttu-id="15b0a-141">Para obtener más información, vea [Página Compilar, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="15b0a-141">For more information, see [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="example"></a><span data-ttu-id="15b0a-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15b0a-142">Example</span></span>  

 <span data-ttu-id="15b0a-143">En el ejemplo siguiente se muestra cómo utilizar la opción `-platform` del compilador.</span><span class="sxs-lookup"><span data-stu-id="15b0a-143">The following example illustrates how to use the `-platform` compiler option.</span></span>  
  
```console
vbc -platform:x86 myFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="15b0a-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="15b0a-144">See also</span></span>

- [<span data-ttu-id="15b0a-145">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15b0a-145">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="15b0a-146">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15b0a-146">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="15b0a-147">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="15b0a-147">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
