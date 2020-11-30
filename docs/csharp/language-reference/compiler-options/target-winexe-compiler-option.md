---
description: -target:winexe (Opciones del compilador de C#)
title: -target:winexe (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: 6e14a2aac427c7adfd69f66eaf624816b75f6ea2
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "91168938"
---
# <a name="-targetwinexe-c-compiler-options"></a><span data-ttu-id="834ee-103">-target:winexe (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="834ee-103">-target:winexe (C# Compiler Options)</span></span>

<span data-ttu-id="834ee-104">La opción **-target:winexe** hace que el compilador cree un programa de Windows ejecutable (EXE).</span><span class="sxs-lookup"><span data-stu-id="834ee-104">The **-target:winexe** option causes the compiler to create an executable (EXE), Windows program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="834ee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="834ee-105">Syntax</span></span>  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="834ee-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="834ee-106">Remarks</span></span>  

 <span data-ttu-id="834ee-107">El archivo ejecutable se creará con la extensión .exe.</span><span class="sxs-lookup"><span data-stu-id="834ee-107">The executable file will be created with the .exe extension.</span></span> <span data-ttu-id="834ee-108">Un programa de Windows es el que ofrece una interfaz de usuario de la biblioteca de .NET o con las API Windows.</span><span class="sxs-lookup"><span data-stu-id="834ee-108">A Windows program is one that provides a user interface from either the .NET library or with the Windows APIs.</span></span>  
  
 <span data-ttu-id="834ee-109">Use [-target:exe](./target-exe-compiler-option.md) para crear una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="834ee-109">Use [-target:exe](./target-exe-compiler-option.md) to create a console application.</span></span>  
  
 <span data-ttu-id="834ee-110">A menos que se especifique de otro modo con la opción [-out](./out-compiler-option.md), el nombre del archivo de salida toma el nombre del archivo de entrada que contiene el método [Main](../../programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="834ee-110">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="834ee-111">Cuando se especifica en la línea de comandos, se usan todos los archivos hasta la siguiente opción **-out** o [-target](./target-compiler-option.md) para crear el programa de Windows.</span><span class="sxs-lookup"><span data-stu-id="834ee-111">When specified at the command line, all files until the next **-out** or [-target](./target-compiler-option.md) option are used to create the Windows program.</span></span>  
  
 <span data-ttu-id="834ee-112">Solo se necesita un método **Main** en los archivos de código fuente que se compilan en un archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="834ee-112">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="834ee-113">La opción [-main](./main-compiler-option.md) permite especificar la clase que contiene el método **Main**, en aquellos casos en los que el código tenga más de una clase con un método **Main**.</span><span class="sxs-lookup"><span data-stu-id="834ee-113">The [-main](./main-compiler-option.md) option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="834ee-114">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="834ee-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="834ee-115">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="834ee-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="834ee-116">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="834ee-116">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="834ee-117">Modifique la propiedad **Tipo de salida**.</span><span class="sxs-lookup"><span data-stu-id="834ee-117">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="834ee-118">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="834ee-118">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="834ee-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="834ee-119">Example</span></span>  

 <span data-ttu-id="834ee-120">Compile `in.cs` en un programa de Windows:</span><span class="sxs-lookup"><span data-stu-id="834ee-120">Compile `in.cs` into a Windows program:</span></span>  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="834ee-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="834ee-121">See also</span></span>

- [<span data-ttu-id="834ee-122">-target (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="834ee-122">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="834ee-123">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="834ee-123">C# Compiler Options</span></span>](./index.md)
