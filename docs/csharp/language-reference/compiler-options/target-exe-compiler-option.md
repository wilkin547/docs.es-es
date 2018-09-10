---
title: -target:exe (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /exe
helpviewer_keywords:
- target compiler options [C#], /target:exe
- /target compiler options [C#], /target:exe
- -target compiler options [C#], /target:exe
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
ms.openlocfilehash: 4a2d3ea2bda56caf6a16f52877ad36b3947357e8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518164"
---
# <a name="-targetexe-c-compiler-options"></a><span data-ttu-id="82747-102">-target:exe (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="82747-102">-target:exe (C# Compiler Options)</span></span>
<span data-ttu-id="82747-103">La opción **-target:winexe** hace que el compilador cree una aplicación de consola ejecutable (EXE).</span><span class="sxs-lookup"><span data-stu-id="82747-103">The **-target:exe** option causes the compiler to create an executable (EXE), console application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82747-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82747-104">Syntax</span></span>  
  
```console  
-target:exe  
```  
  
## <a name="remarks"></a><span data-ttu-id="82747-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="82747-105">Remarks</span></span>  
 <span data-ttu-id="82747-106">La opción **-target:exe** está en vigor de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="82747-106">The **-target:exe** option is in effect by default.</span></span> <span data-ttu-id="82747-107">El archivo ejecutable se creará con la extensión .exe.</span><span class="sxs-lookup"><span data-stu-id="82747-107">The executable file will be created with the .exe extension.</span></span>  
  
 <span data-ttu-id="82747-108">Use [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) para crear un archivo ejecutable de un programa de Windows.</span><span class="sxs-lookup"><span data-stu-id="82747-108">Use [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) to create a Windows program executable.</span></span>  
  
 <span data-ttu-id="82747-109">A menos que se especifique de otro modo con la opción [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), el nombre del archivo de salida toma el nombre del archivo de entrada que contiene el método [Main](../../../csharp/programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="82747-109">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="82747-110">Cuando se especifica en la línea de comandos, se usan todos los archivos hasta la siguiente opción **-out** o **-target:module** para crear el archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="82747-110">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .exe file</span></span>  
  
 <span data-ttu-id="82747-111">Solo se necesita un método **Main** en los archivos de código fuente que se compilan en un archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="82747-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="82747-112">La opción del compilador [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) le permite especificar la clase que contiene el método **Main**, en aquellos casos en los que el código tenga más de una clase con un método **Main**.</span><span class="sxs-lookup"><span data-stu-id="82747-112">The [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) compiler option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="82747-113">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="82747-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="82747-114">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="82747-114">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="82747-115">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="82747-115">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="82747-116">Modifique la propiedad **Tipo de salida**.</span><span class="sxs-lookup"><span data-stu-id="82747-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="82747-117">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="82747-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82747-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="82747-118">Example</span></span>  
 <span data-ttu-id="82747-119">Cada una de las siguientes líneas de comandos compilará `in.cs` y creará `in.exe`:</span><span class="sxs-lookup"><span data-stu-id="82747-119">Each of the following command lines will compile `in.cs`, creating `in.exe`:</span></span>  
  
```console  
csc -target:exe in.cs  
csc in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="82747-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="82747-120">See Also</span></span>  

- [<span data-ttu-id="82747-121">-target (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="82747-121">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
- [<span data-ttu-id="82747-122">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="82747-122">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
