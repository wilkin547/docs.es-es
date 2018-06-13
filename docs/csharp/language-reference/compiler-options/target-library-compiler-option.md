---
title: -target:library (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
ms.openlocfilehash: 39f6ad5839f7ca12b023502a3fc1ccde52e70899
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33215354"
---
# <a name="-targetlibrary-c-compiler-options"></a><span data-ttu-id="b2004-102">-target:library (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="b2004-102">-target:library (C# Compiler Options)</span></span>
<span data-ttu-id="b2004-103">La opción **-target:library** hace que el compilador cree una biblioteca de vínculos dinámicos (DLL) en lugar de un archivo ejecutable (EXE).</span><span class="sxs-lookup"><span data-stu-id="b2004-103">The **-target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2004-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2004-104">Syntax</span></span>  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="b2004-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b2004-105">Remarks</span></span>  
 <span data-ttu-id="b2004-106">El archivo DLL se creará con la extensión .dll.</span><span class="sxs-lookup"><span data-stu-id="b2004-106">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="b2004-107">A menos que se especifique lo contrario con la opción [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), el archivo de salida adopta el nombre del primer archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="b2004-107">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="b2004-108">Cuando se especifica en la línea de comandos, se usan todos los archivos hasta la siguiente opción **-out** o **-target:module** para crear el archivo .dll.</span><span class="sxs-lookup"><span data-stu-id="b2004-108">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="b2004-109">Al compilar un archivo .dll, no es necesario un método [Main](../../../csharp/programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="b2004-109">When building a .dll file, a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="b2004-110">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b2004-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="b2004-111">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b2004-111">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="b2004-112">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="b2004-112">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="b2004-113">Modifique la propiedad **Tipo de salida**.</span><span class="sxs-lookup"><span data-stu-id="b2004-113">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="b2004-114">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2004-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2004-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2004-115">Example</span></span>  
 <span data-ttu-id="b2004-116">Compilación de `in.cs` y creación de `in.dll`:</span><span class="sxs-lookup"><span data-stu-id="b2004-116">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2004-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2004-117">See Also</span></span>  
 [<span data-ttu-id="b2004-118">-target (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="b2004-118">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [<span data-ttu-id="b2004-119">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="b2004-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
