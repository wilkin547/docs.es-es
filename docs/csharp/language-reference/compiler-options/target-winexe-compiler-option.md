---
title: -target:winexe (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: 981f1b0b6ca9f708bb022a3662ab181a4f472040
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606380"
---
# <a name="-targetwinexe-c-compiler-options"></a><span data-ttu-id="23ca7-102">-target:winexe (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="23ca7-102">-target:winexe (C# Compiler Options)</span></span>
<span data-ttu-id="23ca7-103">La opción **-target:winexe** hace que el compilador cree un programa de Windows ejecutable (EXE).</span><span class="sxs-lookup"><span data-stu-id="23ca7-103">The **-target:winexe** option causes the compiler to create an executable (EXE), Windows program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23ca7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23ca7-104">Syntax</span></span>  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="23ca7-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="23ca7-105">Remarks</span></span>  
 <span data-ttu-id="23ca7-106">El archivo ejecutable se creará con la extensión .exe.</span><span class="sxs-lookup"><span data-stu-id="23ca7-106">The executable file will be created with the .exe extension.</span></span> <span data-ttu-id="23ca7-107">Un programa de Windows es aquel que ofrece una interfaz de usuario de la biblioteca de .NET Framework o con las API Windows.</span><span class="sxs-lookup"><span data-stu-id="23ca7-107">A Windows program is one that provides a user interface from either the .NET Framework library or with the Windows APIs.</span></span>  
  
 <span data-ttu-id="23ca7-108">Use [-target:exe](./target-exe-compiler-option.md) para crear una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="23ca7-108">Use [-target:exe](./target-exe-compiler-option.md) to create a console application.</span></span>  
  
 <span data-ttu-id="23ca7-109">A menos que se especifique de otro modo con la opción [-out](./out-compiler-option.md), el nombre del archivo de salida toma el nombre del archivo de entrada que contiene el método [Main](../../programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="23ca7-109">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="23ca7-110">Cuando se especifica en la línea de comandos, se usan todos los archivos hasta la siguiente opción **-out** o [-target](./target-compiler-option.md) para crear el programa de Windows.</span><span class="sxs-lookup"><span data-stu-id="23ca7-110">When specified at the command line, all files until the next **-out** or [-target](./target-compiler-option.md) option are used to create the Windows program.</span></span>  
  
 <span data-ttu-id="23ca7-111">Solo se necesita un método **Main** en los archivos de código fuente que se compilan en un archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="23ca7-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="23ca7-112">La opción [-main](./main-compiler-option.md) permite especificar la clase que contiene el método **Main**, en aquellos casos en los que el código tenga más de una clase con un método **Main**.</span><span class="sxs-lookup"><span data-stu-id="23ca7-112">The [-main](./main-compiler-option.md) option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="23ca7-113">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="23ca7-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="23ca7-114">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="23ca7-114">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="23ca7-115">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="23ca7-115">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="23ca7-116">Modifique la propiedad **Tipo de salida**.</span><span class="sxs-lookup"><span data-stu-id="23ca7-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="23ca7-117">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="23ca7-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23ca7-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="23ca7-118">Example</span></span>  
 <span data-ttu-id="23ca7-119">Compile `in.cs` en un programa de Windows:</span><span class="sxs-lookup"><span data-stu-id="23ca7-119">Compile `in.cs` into a Windows program:</span></span>  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="23ca7-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="23ca7-120">See also</span></span>

- [<span data-ttu-id="23ca7-121">-target (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="23ca7-121">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="23ca7-122">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="23ca7-122">C# Compiler Options</span></span>](./index.md)
