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
ms.openlocfilehash: 8c7789c6af7b82ecb40ecd73d09f64aa1da3fd4b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005058"
---
# <a name="-vbruntime"></a><span data-ttu-id="1d61c-102">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="1d61c-102">-vbruntime</span></span>
<span data-ttu-id="1d61c-103">Especifica que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic o con una referencia a una biblioteca de tiempo de ejecución específica.</span><span class="sxs-lookup"><span data-stu-id="1d61c-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d61c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d61c-104">Syntax</span></span>  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="1d61c-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1d61c-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="1d61c-106">Compile sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1d61c-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="1d61c-107">Compilar con una referencia a la biblioteca en tiempo de ejecución de Visual Basic predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1d61c-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="1d61c-108">Compile sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic e inserte la funcionalidad básica de la biblioteca en tiempo de ejecución de Visual Basic en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1d61c-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="1d61c-109">Compilar con una referencia a la biblioteca especificada (DLL).</span><span class="sxs-lookup"><span data-stu-id="1d61c-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d61c-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1d61c-110">Remarks</span></span>  
 <span data-ttu-id="1d61c-111">La opción del compilador `-vbruntime` le permite especificar que el compilador debe compilar sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1d61c-111">The `-vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="1d61c-112">Si compila sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic, se registran errores o advertencias en construcciones de código o de lenguaje que generan una llamada a una aplicación auxiliar de Visual Basic en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1d61c-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="1d61c-113">(Una *aplicación auxiliar en tiempo de ejecución de Visual Basic* es una función definida en Microsoft. VisualBasic. dll a la que se llama en tiempo de ejecución para ejecutar una semántica específica del lenguaje).</span><span class="sxs-lookup"><span data-stu-id="1d61c-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="1d61c-114">La opción `-vbruntime+` produce el mismo comportamiento que se produce si no se especifica ningún modificador `-vbruntime`.</span><span class="sxs-lookup"><span data-stu-id="1d61c-114">The `-vbruntime+` option produces the same behavior that occurs if no `-vbruntime` switch is specified.</span></span> <span data-ttu-id="1d61c-115">Puede usar la opción `-vbruntime+` para invalidar los conmutadores `-vbruntime` anteriores.</span><span class="sxs-lookup"><span data-stu-id="1d61c-115">You can use the `-vbruntime+` option to override previous `-vbruntime` switches.</span></span>  
  
 <span data-ttu-id="1d61c-116">La mayoría de los objetos del tipo `My` no están disponibles cuando se usan las opciones `-vbruntime-` o `-vbruntime:path`.</span><span class="sxs-lookup"><span data-stu-id="1d61c-116">Most objects of the `My` type are unavailable when you use the `-vbruntime-` or `-vbruntime:path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="1d61c-117">Incrustar Visual Basic funcionalidad básica en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1d61c-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="1d61c-118">La opción `-vbruntime*` le permite compilar sin una referencia a una biblioteca en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1d61c-118">The `-vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="1d61c-119">En su lugar, la funcionalidad básica de la biblioteca en tiempo de ejecución de Visual Basic se incrusta en el ensamblado del usuario.</span><span class="sxs-lookup"><span data-stu-id="1d61c-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="1d61c-120">Puede usar esta opción si la aplicación se ejecuta en plataformas que no contienen el tiempo de ejecución de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1d61c-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="1d61c-121">Los siguientes miembros en tiempo de ejecución están incrustados:</span><span class="sxs-lookup"><span data-stu-id="1d61c-121">The following runtime members are embedded:</span></span>  
  
- <span data-ttu-id="1d61c-122">Clase <xref:Microsoft.VisualBasic.CompilerServices.Conversions></span><span class="sxs-lookup"><span data-stu-id="1d61c-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
- <span data-ttu-id="1d61c-123">Método <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29></span><span class="sxs-lookup"><span data-stu-id="1d61c-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
- <span data-ttu-id="1d61c-124">Método <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="1d61c-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
- <span data-ttu-id="1d61c-125">Método <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29></span><span class="sxs-lookup"><span data-stu-id="1d61c-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
- <span data-ttu-id="1d61c-126"><xref:Microsoft.VisualBasic.Constants.vbBack> (constante)</span><span class="sxs-lookup"><span data-stu-id="1d61c-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
- <span data-ttu-id="1d61c-127"><xref:Microsoft.VisualBasic.Constants.vbCr> (constante)</span><span class="sxs-lookup"><span data-stu-id="1d61c-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
- <span data-ttu-id="1d61c-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> (constante)</span><span class="sxs-lookup"><span data-stu-id="1d61c-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
- <span data-ttu-id="1d61c-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> (constante)</span><span class="sxs-lookup"><span data-stu-id="1d61c-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
- <span data-ttu-id="1d61c-130"><xref:Microsoft.VisualBasic.Constants.vbLf> (constante)</span><span class="sxs-lookup"><span data-stu-id="1d61c-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
- <span data-ttu-id="1d61c-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> (constante)</span><span class="sxs-lookup"><span data-stu-id="1d61c-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
- <span data-ttu-id="1d61c-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> (constante)</span><span class="sxs-lookup"><span data-stu-id="1d61c-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
- <span data-ttu-id="1d61c-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> (constante)</span><span class="sxs-lookup"><span data-stu-id="1d61c-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
- <span data-ttu-id="1d61c-134"><xref:Microsoft.VisualBasic.Constants.vbTab> (constante)</span><span class="sxs-lookup"><span data-stu-id="1d61c-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
- <span data-ttu-id="1d61c-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> (constante)</span><span class="sxs-lookup"><span data-stu-id="1d61c-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
- <span data-ttu-id="1d61c-136">Algunos objetos del tipo `My`</span><span class="sxs-lookup"><span data-stu-id="1d61c-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="1d61c-137">Si se compila con la opción `-vbruntime*` y el código hace referencia a un miembro de la biblioteca en tiempo de ejecución de Visual Basic que no está incrustada con la funcionalidad básica, el compilador devuelve un error que indica que el miembro no está disponible.</span><span class="sxs-lookup"><span data-stu-id="1d61c-137">If you compile using the `-vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="1d61c-138">Hacer referencia a una biblioteca especificada</span><span class="sxs-lookup"><span data-stu-id="1d61c-138">Referencing a specified library</span></span>  
 <span data-ttu-id="1d61c-139">Puede usar el argumento `path` para compilar con una referencia a una biblioteca en tiempo de ejecución personalizada en lugar de la biblioteca en tiempo de ejecución de Visual Basic predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1d61c-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="1d61c-140">Si el valor del argumento `path` es una ruta de acceso completa a un archivo DLL, el compilador usará ese archivo como la biblioteca en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1d61c-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="1d61c-141">Si el valor del argumento `path` no es una ruta de acceso completa a un archivo DLL, el compilador de Visual Basic buscará primero el archivo DLL identificado en la carpeta actual.</span><span class="sxs-lookup"><span data-stu-id="1d61c-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="1d61c-142">A continuación, buscará en la ruta de acceso que ha especificado mediante la opción del compilador [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) .</span><span class="sxs-lookup"><span data-stu-id="1d61c-142">It will then search in the path that you have specified by using the [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="1d61c-143">Si no se utiliza la opción del compilador `-sdkpath`, el compilador buscará el archivo DLL identificado en la carpeta de .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="1d61c-143">If the `-sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d61c-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1d61c-144">Example</span></span>  
 <span data-ttu-id="1d61c-145">En el ejemplo siguiente se muestra cómo usar la opción `-vbruntime` para compilar con una referencia a una biblioteca personalizada.</span><span class="sxs-lookup"><span data-stu-id="1d61c-145">The following example shows how to use the `-vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="1d61c-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d61c-146">See also</span></span>

- [<span data-ttu-id="1d61c-147">Visual Basic Core: nuevo modo de compilación en Visual Studio 2010 SP1</span><span class="sxs-lookup"><span data-stu-id="1d61c-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [<span data-ttu-id="1d61c-148">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1d61c-148">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="1d61c-149">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="1d61c-149">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="1d61c-150">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="1d61c-150">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
