---
title: -target:winexe (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /target:winexe
dev_langs:
- CSharp
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: afb49fc6d45cc904c97988ab1b569f37a4e44a51
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="targetwinexe-c-compiler-options"></a><span data-ttu-id="b74f3-102">/target:winexe (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="b74f3-102">/target:winexe (C# Compiler Options)</span></span>
<span data-ttu-id="b74f3-103">La opción **/target:winexe** hace que el compilador cree un programa de Windows ejecutable (EXE).</span><span class="sxs-lookup"><span data-stu-id="b74f3-103">The **/target:winexe** option causes the compiler to create an executable (EXE), Windows program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b74f3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b74f3-104">Syntax</span></span>  
  
```console  
/target:winexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="b74f3-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b74f3-105">Remarks</span></span>  
 <span data-ttu-id="b74f3-106">El archivo ejecutable se creará con la extensión .exe.</span><span class="sxs-lookup"><span data-stu-id="b74f3-106">The executable file will be created with the .exe extension.</span></span> <span data-ttu-id="b74f3-107">Un programa de Windows es aquel que ofrece una interfaz de usuario de la biblioteca de .NET Framework o con las API Win32.</span><span class="sxs-lookup"><span data-stu-id="b74f3-107">A Windows program is one that provides a user interface from either the .NET Framework library or with the Win32 APIs.</span></span>  
  
 <span data-ttu-id="b74f3-108">Use [/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md) para crear una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="b74f3-108">Use [/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md) to create a console application.</span></span>  
  
 <span data-ttu-id="b74f3-109">A menos que se especifique con la opción [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), el archivo de salida toma el nombre del archivo de entrada que contiene el método [Main](../../../csharp/programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="b74f3-109">Unless otherwise specified with the [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="b74f3-110">Cuando se especifica en la línea de comandos, se usan todos los archivos hasta la siguiente opción **/out** o [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) para crear el programa de Windows.</span><span class="sxs-lookup"><span data-stu-id="b74f3-110">When specified at the command line, all files until the next **/out** or [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) option are used to create the Windows program.</span></span>  
  
 <span data-ttu-id="b74f3-111">Solo se necesita un método **Main** en los archivos de código fuente que se compilan en un archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="b74f3-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="b74f3-112">La opción [/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) permite especificar la clase que contiene el método **Main**, en aquellos casos en los que el código tenga más de una clase con un método **Main**.</span><span class="sxs-lookup"><span data-stu-id="b74f3-112">The [/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="b74f3-113">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b74f3-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="b74f3-114">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b74f3-114">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="b74f3-115">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="b74f3-115">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="b74f3-116">Modifique la propiedad **Tipo de salida**.</span><span class="sxs-lookup"><span data-stu-id="b74f3-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="b74f3-117">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="b74f3-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b74f3-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b74f3-118">Example</span></span>  
 <span data-ttu-id="b74f3-119">Compile `in.cs` en un programa de Windows:</span><span class="sxs-lookup"><span data-stu-id="b74f3-119">Compile `in.cs` into a Windows program:</span></span>  
  
```console  
csc /target:winexe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="b74f3-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b74f3-120">See Also</span></span>  
 <span data-ttu-id="b74f3-121">[/target (C# Compiler Options)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  (/target [Opciones del compilador de C#])</span><span class="sxs-lookup"><span data-stu-id="b74f3-121">[/target (C# Compiler Options)](../../../csharp/language-reference/compiler-options/target-compiler-option.md) </span></span>  
 [<span data-ttu-id="b74f3-122">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="b74f3-122">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)

