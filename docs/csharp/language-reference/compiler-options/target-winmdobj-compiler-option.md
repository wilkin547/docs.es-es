---
title: -target:winmdobj (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
ms.openlocfilehash: 4000394a35c8990d3c5793c1313fc768a61c3271
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608971"
---
# <a name="-targetwinmdobj-c-compiler-options"></a><span data-ttu-id="0158f-102">-target:winmdobj (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="0158f-102">-target:winmdobj (C# Compiler Options)</span></span>
<span data-ttu-id="0158f-103">Si usa la opción del compilador **-target:winmdobj**, el compilador crea un archivo .winmdobj intermedio que se puede convertir en un archivo binario de Windows Runtime (.winmd).</span><span class="sxs-lookup"><span data-stu-id="0158f-103">If you use the **-target:winmdobj** compiler option, the compiler creates an intermediate .winmdobj file that you can convert to a Windows Runtime binary (.winmd) file.</span></span> <span data-ttu-id="0158f-104">A continuación, pueden usar el archivo .winmd programas de JavaScript y C++, además de los programas de lenguajes administrados.</span><span class="sxs-lookup"><span data-stu-id="0158f-104">The .winmd file can then be consumed by JavaScript and C++ programs, in addition to managed language programs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0158f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0158f-105">Syntax</span></span>  
  
```console  
-target:winmdobj  
```  
  
## <a name="remarks"></a><span data-ttu-id="0158f-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0158f-106">Remarks</span></span>  
 <span data-ttu-id="0158f-107">El valor **winmdobj** indica al compilador que un módulo intermedio es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0158f-107">The **winmdobj** setting signals to the compiler that an intermediate module is required.</span></span> <span data-ttu-id="0158f-108">En respuesta, Visual Studio compila la biblioteca de clases de C# como archivo .winmdobj.</span><span class="sxs-lookup"><span data-stu-id="0158f-108">In response, Visual Studio compiles the C# class library as a .winmdobj file.</span></span> <span data-ttu-id="0158f-109">El archivo .winmdobj se puede alimentar entonces a través de la herramienta de exportación <xref:Microsoft.Build.Tasks.WinMDExp> para producir un archivo de metadatos de Windows (.winmd).</span><span class="sxs-lookup"><span data-stu-id="0158f-109">The .winmdobj file can then be fed through the <xref:Microsoft.Build.Tasks.WinMDExp> export tool to produce a Windows metadata (.winmd) file.</span></span> <span data-ttu-id="0158f-110">El archivo .winmd contiene el código de la biblioteca original y los metadatos de WinMD que usan JavaScript o C++ y Windows en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0158f-110">The .winmd file contains both the code from the original library and the WinMD metadata that is used by JavaScript or C++ and by the Windows Runtime.</span></span>  
  
 <span data-ttu-id="0158f-111">La salida de un archivo compilado mediante la opción del compilador **-target:winmdobj** solo sirve para usarse como entrada de la herramienta de exportación WimMDExp; no se hace referencia directa al propio archivo .winmdobj.</span><span class="sxs-lookup"><span data-stu-id="0158f-111">The output of a file that’s compiled by using the **-target:winmdobj** compiler option is designed to be used only as input for the WimMDExp export tool; the .winmdobj file itself isn’t referenced directly.</span></span>  
  
 <span data-ttu-id="0158f-112">A menos que use la opción [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), el nombre del archivo de salida adopta el nombre del primer archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="0158f-112">Unless you use the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span> <span data-ttu-id="0158f-113">No se requiere un método [Main](../../../csharp/programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="0158f-113">A [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method isn’t required.</span></span>  
  
 <span data-ttu-id="0158f-114">Si especifica la opción -target:winmdobj en un símbolo del sistema, todos los archivos hasta la siguiente opción **-out** o [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) se usan para crear el programa de Windows.</span><span class="sxs-lookup"><span data-stu-id="0158f-114">If you specify the -target:winmdobj option at a command prompt, all files until the next **-out** or [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) option are used to create the Windows program.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-ide-for-a-windows-store-app"></a><span data-ttu-id="0158f-115">Para establecer esta opción del compilador en el IDE de Visual Studio para una aplicación de la Tienda Windows</span><span class="sxs-lookup"><span data-stu-id="0158f-115">To set this compiler option in the Visual Studio IDE for a Windows Store app</span></span>  
  
1.  <span data-ttu-id="0158f-116">En el **Explorador de soluciones**, abra el menú contextual del proyecto y, después, pulse **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0158f-116">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="0158f-117">Pulse la pestaña **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="0158f-117">Choose the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="0158f-118">En la lista **Tipo de resultado**, pulse **Archivo WinMD**.</span><span class="sxs-lookup"><span data-stu-id="0158f-118">In the **Output type** list, choose **WinMD File**.</span></span>  
  
     <span data-ttu-id="0158f-119">La opción **Archivo WinMD** solo está disponible para las plantillas de aplicación de [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0158f-119">The **WinMD File** option is available only for [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] app templates.</span></span>  
  
 <span data-ttu-id="0158f-120">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="0158f-120">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0158f-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0158f-121">Example</span></span>  
 <span data-ttu-id="0158f-122">El comando siguiente compila `filename.cs` en un archivo .winmdobj intermedio.</span><span class="sxs-lookup"><span data-stu-id="0158f-122">The following command compiles `filename.cs` into an intermediate .winmdobj file.</span></span>  
  
```console  
csc -target:winmdobj filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="0158f-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0158f-123">See also</span></span>

- [<span data-ttu-id="0158f-124">-target (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="0158f-124">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [<span data-ttu-id="0158f-125">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="0158f-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
