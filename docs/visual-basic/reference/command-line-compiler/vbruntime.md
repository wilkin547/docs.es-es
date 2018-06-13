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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d28d0556a662099e4e5e74b22583fc3c8b4c313f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656118"
---
# <a name="-vbruntime"></a><span data-ttu-id="37f89-102">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="37f89-102">-vbruntime</span></span>
<span data-ttu-id="37f89-103">Especifica que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic o con una referencia a una biblioteca de tiempo de ejecución específica.</span><span class="sxs-lookup"><span data-stu-id="37f89-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37f89-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37f89-104">Syntax</span></span>  
  
```  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="37f89-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="37f89-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="37f89-106">Compilar sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="37f89-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="37f89-107">Compilar con una referencia a la biblioteca en tiempo de ejecución de Visual Basic predeterminada.</span><span class="sxs-lookup"><span data-stu-id="37f89-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="37f89-108">Compilar sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic e incrustar la funcionalidad básica de la biblioteca en tiempo de ejecución de Visual Basic en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="37f89-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="37f89-109">Compilar con una referencia a la biblioteca especificada (DLL).</span><span class="sxs-lookup"><span data-stu-id="37f89-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37f89-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="37f89-110">Remarks</span></span>  
 <span data-ttu-id="37f89-111">El `-vbruntime` opción del compilador le permite especificar que el compilador debe compilar sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="37f89-111">The `-vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="37f89-112">Si compila sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic, errores o advertencias se registran en construcciones de código o lenguaje que generan una llamada a una aplicación auxiliar de tiempo de ejecución de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="37f89-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="37f89-113">(Un *aplicación auxiliar de tiempo de ejecución de Visual Basic* es una función definida en Microsoft.VisualBasic.dll a la que se llama en tiempo de ejecución para ejecutar una semántica concreta del lenguaje.)</span><span class="sxs-lookup"><span data-stu-id="37f89-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="37f89-114">El `-vbruntime+` opción produce el mismo comportamiento que se produce si no hay ningún `-vbruntime` ha especificado el modificador.</span><span class="sxs-lookup"><span data-stu-id="37f89-114">The `-vbruntime+` option produces the same behavior that occurs if no `-vbruntime` switch is specified.</span></span> <span data-ttu-id="37f89-115">Puede usar el `-vbruntime+` opción para invalidar anterior `-vbruntime` conmutadores.</span><span class="sxs-lookup"><span data-stu-id="37f89-115">You can use the `-vbruntime+` option to override previous `-vbruntime` switches.</span></span>  
  
 <span data-ttu-id="37f89-116">Mayoría de los objetos de la `My` tipo no están disponibles cuando se usa el `-vbruntime-` o `-vbruntime:path` opciones.</span><span class="sxs-lookup"><span data-stu-id="37f89-116">Most objects of the `My` type are unavailable when you use the `-vbruntime-` or `-vbruntime:path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="37f89-117">Incrustar la funcionalidad básica de tiempo de ejecución de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37f89-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="37f89-118">El `-vbruntime*` opción le permite compilar sin una referencia a una biblioteca en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="37f89-118">The `-vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="37f89-119">En su lugar, la funcionalidad básica de la biblioteca en tiempo de ejecución de Visual Basic se incrusta en el ensamblado de usuario.</span><span class="sxs-lookup"><span data-stu-id="37f89-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="37f89-120">Puede usar esta opción si la aplicación se ejecuta en plataformas que no contienen el tiempo de ejecución de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="37f89-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="37f89-121">Se incrustan los siguientes miembros de tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="37f89-121">The following runtime members are embedded:</span></span>  
  
-   <span data-ttu-id="37f89-122">Clase <xref:Microsoft.VisualBasic.CompilerServices.Conversions></span><span class="sxs-lookup"><span data-stu-id="37f89-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
-   <span data-ttu-id="37f89-123">Método <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29></span><span class="sxs-lookup"><span data-stu-id="37f89-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
-   <span data-ttu-id="37f89-124">Método <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="37f89-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
-   <span data-ttu-id="37f89-125">Método <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29></span><span class="sxs-lookup"><span data-stu-id="37f89-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
-   <span data-ttu-id="37f89-126"><xref:Microsoft.VisualBasic.Constants.vbBack> (constante)</span><span class="sxs-lookup"><span data-stu-id="37f89-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
-   <span data-ttu-id="37f89-127"><xref:Microsoft.VisualBasic.Constants.vbCr> (constante)</span><span class="sxs-lookup"><span data-stu-id="37f89-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
-   <span data-ttu-id="37f89-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> (constante)</span><span class="sxs-lookup"><span data-stu-id="37f89-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
-   <span data-ttu-id="37f89-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> (constante)</span><span class="sxs-lookup"><span data-stu-id="37f89-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
-   <span data-ttu-id="37f89-130"><xref:Microsoft.VisualBasic.Constants.vbLf> (constante)</span><span class="sxs-lookup"><span data-stu-id="37f89-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
-   <span data-ttu-id="37f89-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> (constante)</span><span class="sxs-lookup"><span data-stu-id="37f89-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
-   <span data-ttu-id="37f89-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> (constante)</span><span class="sxs-lookup"><span data-stu-id="37f89-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
-   <span data-ttu-id="37f89-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> (constante)</span><span class="sxs-lookup"><span data-stu-id="37f89-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
-   <span data-ttu-id="37f89-134"><xref:Microsoft.VisualBasic.Constants.vbTab> (constante)</span><span class="sxs-lookup"><span data-stu-id="37f89-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
-   <span data-ttu-id="37f89-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> (constante)</span><span class="sxs-lookup"><span data-stu-id="37f89-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
-   <span data-ttu-id="37f89-136">Algunos objetos de la `My` tipo</span><span class="sxs-lookup"><span data-stu-id="37f89-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="37f89-137">Si se compila utilizando el `-vbruntime*` opción y el código hace referencia a un miembro de la biblioteca en tiempo de ejecución de Visual Basic que no se incrusta con la funcionalidad básica, el compilador devuelve un error que indica que el miembro no está disponible.</span><span class="sxs-lookup"><span data-stu-id="37f89-137">If you compile using the `-vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="37f89-138">Hacer referencia a una biblioteca especificada</span><span class="sxs-lookup"><span data-stu-id="37f89-138">Referencing a specified library</span></span>  
 <span data-ttu-id="37f89-139">Puede usar el `path` argumento para compilar con una referencia a una biblioteca en tiempo de ejecución personalizado en lugar de la biblioteca en tiempo de ejecución de Visual Basic predeterminada.</span><span class="sxs-lookup"><span data-stu-id="37f89-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="37f89-140">Si el valor de la `path` argumento es una ruta de acceso completa a un archivo DLL, el compilador usará ese archivo como la biblioteca en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="37f89-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="37f89-141">Si el valor de la `path` argumento no es una ruta de acceso completa a un archivo DLL, el compilador de Visual Basic buscará la DLL identificada en la carpeta actual en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="37f89-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="37f89-142">A continuación, buscará en la ruta de acceso que ha especificado mediante el uso de la [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) opción del compilador.</span><span class="sxs-lookup"><span data-stu-id="37f89-142">It will then search in the path that you have specified by using the [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="37f89-143">Si el `-sdkpath` no se utiliza la opción del compilador, el compilador buscará la DLL identificada en la carpeta .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="37f89-143">If the `-sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="37f89-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37f89-144">Example</span></span>  
 <span data-ttu-id="37f89-145">En el ejemplo siguiente se muestra cómo utilizar el `-vbruntime` opción de compilar con una referencia a una biblioteca personalizada.</span><span class="sxs-lookup"><span data-stu-id="37f89-145">The following example shows how to use the `-vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="37f89-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="37f89-146">See Also</span></span>  
 [<span data-ttu-id="37f89-147">Núcleo de Visual Basic: nuevo modo de compilación en Visual Studio 2010 SP1</span><span class="sxs-lookup"><span data-stu-id="37f89-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)  
 [<span data-ttu-id="37f89-148">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37f89-148">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="37f89-149">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="37f89-149">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="37f89-150">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="37f89-150">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
