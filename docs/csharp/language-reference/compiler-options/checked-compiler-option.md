---
title: -checked (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /checked
dev_langs:
- CSharp
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
caps.latest.revision: 20
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
ms.openlocfilehash: 63ba89ec42748ccea065bf0fd258fb559abca099
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="checked-c-compiler-options"></a><span data-ttu-id="f3420-102">/checked (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="f3420-102">/checked (C# Compiler Options)</span></span>
<span data-ttu-id="f3420-103">La opción **/checked** especifica si una instrucción aritmética de enteros que produce un valor fuera del intervalo del tipo de datos y que no está en el ámbito de las palabras clave [checked](../../../csharp/language-reference/keywords/checked.md) o [unchecked](../../../csharp/language-reference/keywords/unchecked.md) provocará una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f3420-103">The **/checked** option specifies whether an integer arithmetic statement that results in a value that is outside the range of the data type, and that is not in the scope of a [checked](../../../csharp/language-reference/keywords/checked.md) or [unchecked](../../../csharp/language-reference/keywords/unchecked.md) keyword, causes a run-time exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3420-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3420-104">Syntax</span></span>  
  
```console  
/checked[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="f3420-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f3420-105">Remarks</span></span>  
 <span data-ttu-id="f3420-106">Una instrucción de aritmética de enteros que está en el ámbito de la palabra clave `checked` o `unchecked` no está sujeta al efecto de la opción **/checked**.</span><span class="sxs-lookup"><span data-stu-id="f3420-106">An integer arithmetic statement that is in the scope of a `checked` or `unchecked` keyword is not subject to the effect of the **/checked** option.</span></span>  
  
 <span data-ttu-id="f3420-107">Si una instrucción de aritmética de enteros que no está en el ámbito de la palabra clave `checked` o `unchecked` produce un valor fuera del intervalo del tipo de datos, y si se usa **/checked+** (**/checked**) en la compilación, la instrucción provoca una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f3420-107">If an integer arithmetic statement that is not in the scope of a `checked` or `unchecked` keyword results in a value outside the range of the data type, and **/checked+** (**/checked**) is used in the compilation, that statement causes an exception at run time.</span></span> <span data-ttu-id="f3420-108">Si se usa **/checked-** en la compilación, la instrucción no produce una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f3420-108">If **/checked-** is used in the compilation, that statement does not cause an exception at run time.</span></span>  
  
 <span data-ttu-id="f3420-109">El valor predeterminado para esta opción es **/checked-**.</span><span class="sxs-lookup"><span data-stu-id="f3420-109">The default value for this option is **/checked-**.</span></span> <span data-ttu-id="f3420-110">Un escenario habitual para el uso de **/checked-** es la compilación de aplicaciones de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="f3420-110">One scenario for using **/checked-** is in building large applications.</span></span> <span data-ttu-id="f3420-111">A veces se usan herramientas automatizadas para generar compilar estas aplicaciones, y estas herramientas podrían establecer automáticamente **/checked** en +.</span><span class="sxs-lookup"><span data-stu-id="f3420-111">Sometimes automated tools are used to build such applications, and such a tool might automatically set **/checked** to +.</span></span> <span data-ttu-id="f3420-112">Para reemplazar el valor predeterminado global de la herramienta, especifique **/checked-**.</span><span class="sxs-lookup"><span data-stu-id="f3420-112">You can override the tool's global default by specifying **/checked-**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f3420-113">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f3420-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="f3420-114">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f3420-114">Open the project's **Properties** page.</span></span> <span data-ttu-id="f3420-115">Para obtener más información, consulte [Compilar (Página, Diseñador de proyectos) (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="f3420-115">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="f3420-116">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="f3420-116">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="f3420-117">Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="f3420-117">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="f3420-118">Modifique la propiedad **Comprobar el desbordamiento y subdesbordamiento aritmético**.</span><span class="sxs-lookup"><span data-stu-id="f3420-118">Modify the **Check for arithmetic overflow/underflow** property.</span></span>  
  
 <span data-ttu-id="f3420-119">Para acceder a esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span><span class="sxs-lookup"><span data-stu-id="f3420-119">To access this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3420-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3420-120">Example</span></span>  
 <span data-ttu-id="f3420-121">El comando siguiente compila `t2.cs`.</span><span class="sxs-lookup"><span data-stu-id="f3420-121">The following command compiles `t2.cs`.</span></span> <span data-ttu-id="f3420-122">El uso de `/checked` en el comando especifica que cualquier instrucción de aritmética de enteros del archivo que no esté en el ámbito de la palabra clave `checked` o `unchecked` y que produzca un valor fuera del intervalo del tipo de datos provocará una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f3420-122">The use of `/checked` in the command specifies that any integer arithmetic statement in the file that is not in the scope of a `checked` or `unchecked` keyword, and that results in a value that is outside the range of the data type, causes an exception at run time.</span></span>  
  
```console  
csc t2.cs /checked  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3420-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3420-123">See Also</span></span>  
 <span data-ttu-id="f3420-124">[Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="f3420-124">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 <span data-ttu-id="f3420-125">[Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties) </span><span class="sxs-lookup"><span data-stu-id="f3420-125">[Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties) </span></span>  
 [<span data-ttu-id="f3420-126">Introducción al Diseñador de proyectos</span><span class="sxs-lookup"><span data-stu-id="f3420-126">Introduction to the Project Designer</span></span>](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)

