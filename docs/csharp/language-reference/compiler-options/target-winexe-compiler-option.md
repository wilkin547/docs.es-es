---
title: -target:winexe (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e155c64689f34c89443c7ff0a3dee38d6c190fcc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="targetwinexe-c-compiler-options"></a><span data-ttu-id="bf59a-102">/target:winexe (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="bf59a-102">/target:winexe (C# Compiler Options)</span></span>
<span data-ttu-id="bf59a-103">La opción **/target:winexe** hace que el compilador cree un programa de Windows ejecutable (EXE).</span><span class="sxs-lookup"><span data-stu-id="bf59a-103">The **/target:winexe** option causes the compiler to create an executable (EXE), Windows program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf59a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf59a-104">Syntax</span></span>  
  
```console  
/target:winexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="bf59a-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf59a-105">Remarks</span></span>  
 <span data-ttu-id="bf59a-106">El archivo ejecutable se creará con la extensión .exe.</span><span class="sxs-lookup"><span data-stu-id="bf59a-106">The executable file will be created with the .exe extension.</span></span> <span data-ttu-id="bf59a-107">Un programa de Windows es aquel que ofrece una interfaz de usuario de la biblioteca de .NET Framework o con las API Win32.</span><span class="sxs-lookup"><span data-stu-id="bf59a-107">A Windows program is one that provides a user interface from either the .NET Framework library or with the Win32 APIs.</span></span>  
  
 <span data-ttu-id="bf59a-108">Use [/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md) para crear una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="bf59a-108">Use [/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md) to create a console application.</span></span>  
  
 <span data-ttu-id="bf59a-109">A menos que se especifique con la opción [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), el archivo de salida toma el nombre del archivo de entrada que contiene el método [Main](../../../csharp/programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="bf59a-109">Unless otherwise specified with the [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="bf59a-110">Cuando se especifica en la línea de comandos, se usan todos los archivos hasta la siguiente opción **/out** o [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) para crear el programa de Windows.</span><span class="sxs-lookup"><span data-stu-id="bf59a-110">When specified at the command line, all files until the next **/out** or [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) option are used to create the Windows program.</span></span>  
  
 <span data-ttu-id="bf59a-111">Solo se necesita un método **Main** en los archivos de código fuente que se compilan en un archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="bf59a-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="bf59a-112">La opción [/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) permite especificar la clase que contiene el método **Main**, en aquellos casos en los que el código tenga más de una clase con un método **Main**.</span><span class="sxs-lookup"><span data-stu-id="bf59a-112">The [/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="bf59a-113">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bf59a-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="bf59a-114">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="bf59a-114">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="bf59a-115">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="bf59a-115">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="bf59a-116">Modifique la propiedad **Tipo de salida**.</span><span class="sxs-lookup"><span data-stu-id="bf59a-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="bf59a-117">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf59a-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf59a-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf59a-118">Example</span></span>  
 <span data-ttu-id="bf59a-119">Compile `in.cs` en un programa de Windows:</span><span class="sxs-lookup"><span data-stu-id="bf59a-119">Compile `in.cs` into a Windows program:</span></span>  
  
```console  
csc /target:winexe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf59a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf59a-120">See Also</span></span>  
 [<span data-ttu-id="bf59a-121">/target (opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="bf59a-121">/target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [<span data-ttu-id="bf59a-122">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="bf59a-122">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
