---
title: -vbruntime
ms.date: 03/13/2018
f1_keywords:
- vbruntime
- -vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
ms.openlocfilehash: 46d4b095d4a2bf9aac9124d5d4b2a09adb347ba1
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085066"
---
# <a name="-vbruntime"></a><span data-ttu-id="8a4e0-102">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="8a4e0-102">-vbruntime</span></span>

<span data-ttu-id="8a4e0-103">Especifica que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic o con una referencia a una biblioteca de tiempo de ejecución específica.</span><span class="sxs-lookup"><span data-stu-id="8a4e0-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a4e0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a4e0-104">Syntax</span></span>  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="8a4e0-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8a4e0-105">Arguments</span></span>  

 \-  
 <span data-ttu-id="8a4e0-106">Se compila sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8a4e0-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="8a4e0-107">Se compila con una referencia a la biblioteca en tiempo de ejecución de Visual Basic predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8a4e0-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="8a4e0-108">Se compila sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic y se inserta la funcionalidad básica de esa biblioteca en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8a4e0-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="8a4e0-109">Se compila con una referencia a la biblioteca especificada (DLL).</span><span class="sxs-lookup"><span data-stu-id="8a4e0-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a4e0-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a4e0-110">Remarks</span></span>  

 <span data-ttu-id="8a4e0-111">La opción de compilación `-vbruntime` permite especificar que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8a4e0-111">The `-vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="8a4e0-112">Si se compila sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic, los errores o las advertencias se registran en construcciones de lenguaje o código que generan una llamada a una aplicación auxiliar en tiempo de ejecución de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8a4e0-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="8a4e0-113">(una *aplicación auxiliar en tiempo de ejecución de Visual Basic* es una función definida en Microsoft.VisualBasic.dll a la que se llama en tiempo de ejecución para ejecutar una semántica de lenguaje específica).</span><span class="sxs-lookup"><span data-stu-id="8a4e0-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="8a4e0-114">La opción `-vbruntime+` produce el mismo comportamiento que sucede cuando no se especifica ningún modificador `-vbruntime`.</span><span class="sxs-lookup"><span data-stu-id="8a4e0-114">The `-vbruntime+` option produces the same behavior that occurs if no `-vbruntime` switch is specified.</span></span> <span data-ttu-id="8a4e0-115">Puede usar la opción `-vbruntime+` para invalidar modificadores `-vbruntime` anteriores.</span><span class="sxs-lookup"><span data-stu-id="8a4e0-115">You can use the `-vbruntime+` option to override previous `-vbruntime` switches.</span></span>  
  
 <span data-ttu-id="8a4e0-116">La mayoría de los objetos de tipo `My` no están disponibles cuando se usan las opciones `-vbruntime-` o `-vbruntime:path`.</span><span class="sxs-lookup"><span data-stu-id="8a4e0-116">Most objects of the `My` type are unavailable when you use the `-vbruntime-` or `-vbruntime:path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="8a4e0-117">Inserción de funcionalidad básica en tiempo de ejecución de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8a4e0-117">Embedding Visual Basic Runtime core functionality</span></span>  

 <span data-ttu-id="8a4e0-118">La opción `-vbruntime*` permite compilar sin una referencia a una biblioteca en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8a4e0-118">The `-vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="8a4e0-119">En su lugar, la funcionalidad básica de la biblioteca en tiempo de ejecución de Visual Basic se inserta en el ensamblado del usuario.</span><span class="sxs-lookup"><span data-stu-id="8a4e0-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="8a4e0-120">Esta opción se puede usar si la aplicación se ejecuta en plataformas que no contienen el tiempo de ejecución de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8a4e0-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="8a4e0-121">Se insertan los siguientes miembros de tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="8a4e0-121">The following runtime members are embedded:</span></span>  
  
- <span data-ttu-id="8a4e0-122">Clase <xref:Microsoft.VisualBasic.CompilerServices.Conversions></span><span class="sxs-lookup"><span data-stu-id="8a4e0-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
- <span data-ttu-id="8a4e0-123">Método <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29></span><span class="sxs-lookup"><span data-stu-id="8a4e0-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
- <span data-ttu-id="8a4e0-124">Método <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="8a4e0-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
- <span data-ttu-id="8a4e0-125">Método <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29></span><span class="sxs-lookup"><span data-stu-id="8a4e0-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
- <span data-ttu-id="8a4e0-126">Constante <xref:Microsoft.VisualBasic.Constants.vbBack></span><span class="sxs-lookup"><span data-stu-id="8a4e0-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
- <span data-ttu-id="8a4e0-127">Constante <xref:Microsoft.VisualBasic.Constants.vbCr></span><span class="sxs-lookup"><span data-stu-id="8a4e0-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
- <span data-ttu-id="8a4e0-128">Constante <xref:Microsoft.VisualBasic.Constants.vbCrLf></span><span class="sxs-lookup"><span data-stu-id="8a4e0-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
- <span data-ttu-id="8a4e0-129">Constante <xref:Microsoft.VisualBasic.Constants.vbFormFeed></span><span class="sxs-lookup"><span data-stu-id="8a4e0-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
- <span data-ttu-id="8a4e0-130">Constante <xref:Microsoft.VisualBasic.Constants.vbLf></span><span class="sxs-lookup"><span data-stu-id="8a4e0-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
- <span data-ttu-id="8a4e0-131">Constante <xref:Microsoft.VisualBasic.Constants.vbNewLine></span><span class="sxs-lookup"><span data-stu-id="8a4e0-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
- <span data-ttu-id="8a4e0-132">Constante <xref:Microsoft.VisualBasic.Constants.vbNullChar></span><span class="sxs-lookup"><span data-stu-id="8a4e0-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
- <span data-ttu-id="8a4e0-133">Constante <xref:Microsoft.VisualBasic.Constants.vbNullString></span><span class="sxs-lookup"><span data-stu-id="8a4e0-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
- <span data-ttu-id="8a4e0-134">Constante <xref:Microsoft.VisualBasic.Constants.vbTab></span><span class="sxs-lookup"><span data-stu-id="8a4e0-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
- <span data-ttu-id="8a4e0-135">Constante <xref:Microsoft.VisualBasic.Constants.vbVerticalTab></span><span class="sxs-lookup"><span data-stu-id="8a4e0-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
- <span data-ttu-id="8a4e0-136">Algunos objetos del tipo `My`</span><span class="sxs-lookup"><span data-stu-id="8a4e0-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="8a4e0-137">Si se compila con la opción `-vbruntime*` y el código hace referencia a un miembro de la biblioteca en tiempo de ejecución de Visual Basic que no tiene insertada la funcionalidad básica, el compilador devuelve un error que indica que el miembro no está disponible.</span><span class="sxs-lookup"><span data-stu-id="8a4e0-137">If you compile using the `-vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="8a4e0-138">Referencia a una biblioteca especificada</span><span class="sxs-lookup"><span data-stu-id="8a4e0-138">Referencing a specified library</span></span>  

 <span data-ttu-id="8a4e0-139">El argumento `path` se puede usar para compilar con una referencia a una biblioteca en tiempo de ejecución personalizada, en lugar de a la biblioteca en tiempo de ejecución de Visual Basic predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8a4e0-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="8a4e0-140">Si el valor del argumento `path` es una ruta de acceso completa a un archivo DLL, el compilador usará ese archivo como la biblioteca en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8a4e0-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="8a4e0-141">Si el valor del argumento `path` no es una ruta de acceso completa a un archivo DLL, el compilador de Visual Basic buscará primero el archivo DLL identificado en la carpeta actual.</span><span class="sxs-lookup"><span data-stu-id="8a4e0-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="8a4e0-142">Después, buscará en la ruta de acceso que se haya especificado, usando para ello la opción de compilador [-sdkpath](sdkpath.md).</span><span class="sxs-lookup"><span data-stu-id="8a4e0-142">It will then search in the path that you have specified by using the [-sdkpath](sdkpath.md) compiler option.</span></span> <span data-ttu-id="8a4e0-143">Si no se usa la opción de compilador `-sdkpath`, el compilador buscará el archivo DLL identificado en la carpeta de .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="8a4e0-143">If the `-sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a4e0-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a4e0-144">Example</span></span>  

 <span data-ttu-id="8a4e0-145">En el siguiente ejemplo se muestra cómo usar la opción `-vbruntime` para compilar con una referencia a una biblioteca personalizada.</span><span class="sxs-lookup"><span data-stu-id="8a4e0-145">The following example shows how to use the `-vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a4e0-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a4e0-146">See also</span></span>

- [<span data-ttu-id="8a4e0-147">Visual Basic Core: nuevo modo de compilación en Visual Studio 2010 SP1</span><span class="sxs-lookup"><span data-stu-id="8a4e0-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [<span data-ttu-id="8a4e0-148">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8a4e0-148">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="8a4e0-149">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a4e0-149">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="8a4e0-150">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="8a4e0-150">-sdkpath</span></span>](sdkpath.md)
