---
title: -target:library (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /dll
dev_langs:
- CSharp
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
caps.latest.revision: 12
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
ms.openlocfilehash: c54599a3badf65fe6d53f74f71fde58772afa6c2
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="targetlibrary-c-compiler-options"></a><span data-ttu-id="3676a-102">/target:library (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="3676a-102">/target:library (C# Compiler Options)</span></span>
<span data-ttu-id="3676a-103">La opción **/target:library** hace que el compilador cree una biblioteca de vínculos dinámicos (DLL) en lugar de un archivo ejecutable (EXE).</span><span class="sxs-lookup"><span data-stu-id="3676a-103">The **/target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3676a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3676a-104">Syntax</span></span>  
  
```console  
/target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="3676a-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3676a-105">Remarks</span></span>  
 <span data-ttu-id="3676a-106">El archivo DLL se creará con la extensión .dll.</span><span class="sxs-lookup"><span data-stu-id="3676a-106">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="3676a-107">A menos que se especifique lo contrario con la opción [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), el archivo de salida adopta el nombre del primer archivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="3676a-107">Unless otherwise specified with the [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="3676a-108">Cuando se especifica en la línea de comandos, se usan todos los archivos hasta la siguiente opción **/out** o **/target:module** para crear el archivo .dll.</span><span class="sxs-lookup"><span data-stu-id="3676a-108">When specified at the command line, all files up to the next **/out** or **/target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="3676a-109">Al compilar un archivo .dll, no es necesario un método [Main](../../../csharp/programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="3676a-109">When building a .dll file, a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="3676a-110">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3676a-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="3676a-111">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3676a-111">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="3676a-112">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="3676a-112">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="3676a-113">Modifique la propiedad **Tipo de salida**.</span><span class="sxs-lookup"><span data-stu-id="3676a-113">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="3676a-114">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="3676a-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3676a-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3676a-115">Example</span></span>  
 <span data-ttu-id="3676a-116">Compilación de `in.cs` y creación de `in.dll`:</span><span class="sxs-lookup"><span data-stu-id="3676a-116">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc /target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="3676a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3676a-117">See Also</span></span>  
 <span data-ttu-id="3676a-118">[/target (C# Compiler Options)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  (/target [Opciones del compilador de C#])</span><span class="sxs-lookup"><span data-stu-id="3676a-118">[/target (C# Compiler Options)](../../../csharp/language-reference/compiler-options/target-compiler-option.md) </span></span>  
 [<span data-ttu-id="3676a-119">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="3676a-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)

