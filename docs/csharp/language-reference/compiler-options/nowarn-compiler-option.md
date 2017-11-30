---
title: -nowarn (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /nowarn
helpviewer_keywords:
- nowarn compiler option [C#]
- /nowarn compiler option [C#]
- -nowarn compiler option [C#]
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 499203bb4714fa2d07b2c0e42958ffd0e472facc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="nowarn-c-compiler-options"></a><span data-ttu-id="da77b-102">/nowarn (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="da77b-102">/nowarn (C# Compiler Options)</span></span>
<span data-ttu-id="da77b-103">La opción **/nowarn** permite impedir que el compilador muestre una o más advertencias.</span><span class="sxs-lookup"><span data-stu-id="da77b-103">The **/nowarn** option lets you suppress the compiler from displaying one or more warnings.</span></span> <span data-ttu-id="da77b-104">Separe varios números de advertencia con una coma.</span><span class="sxs-lookup"><span data-stu-id="da77b-104">Separate multiple warning numbers with a comma.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da77b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da77b-105">Syntax</span></span>  
  
```console  
/nowarn:number1[,number2,...]  
```  
  
## <a name="arguments"></a><span data-ttu-id="da77b-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="da77b-106">Arguments</span></span>  
 <span data-ttu-id="da77b-107">`number1`, `number2`</span><span class="sxs-lookup"><span data-stu-id="da77b-107">`number1`, `number2`</span></span>  
 <span data-ttu-id="da77b-108">Números de advertencia que quiere que el compilador suprima.</span><span class="sxs-lookup"><span data-stu-id="da77b-108">Warning number(s) that you want the compiler to suppress.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da77b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="da77b-109">Remarks</span></span>  
 <span data-ttu-id="da77b-110">Solo debe especificar la parte numérica del identificador de advertencia.</span><span class="sxs-lookup"><span data-stu-id="da77b-110">You should only specify the numeric part of the warning identifier.</span></span> <span data-ttu-id="da77b-111">Por ejemplo, si quiere suprimir CS0028, puede especificar `/nowarn:28`.</span><span class="sxs-lookup"><span data-stu-id="da77b-111">For example, if you want to suppress CS0028, you could specify `/nowarn:28`.</span></span>  
  
 <span data-ttu-id="da77b-112">El compilador omitirá silenciosamente los números de advertencia pasados a `/nowarn` que eran válidos en versiones anteriores, pero que se han quitado del compilador.</span><span class="sxs-lookup"><span data-stu-id="da77b-112">The compiler will silently ignore warning numbers passed to `/nowarn` that were valid in previous releases, but that have been removed from the compiler.</span></span> <span data-ttu-id="da77b-113">Por ejemplo, CS0679 era válido en el compilador de Visual Studio .NET 2002, pero se ha eliminado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="da77b-113">For example, CS0679 was valid in the compiler in Visual Studio .NET 2002 but was subsequently removed.</span></span>  
  
 <span data-ttu-id="da77b-114">Las advertencias siguientes no se pueden suprimir mediante la opción `/nowarn`:</span><span class="sxs-lookup"><span data-stu-id="da77b-114">The following warnings cannot be suppressed by the `/nowarn` option:</span></span>  
  
-   <span data-ttu-id="da77b-115">Advertencia del compilador (nivel 1) CS2002</span><span class="sxs-lookup"><span data-stu-id="da77b-115">Compiler Warning (level 1) CS2002</span></span>  
  
-   <span data-ttu-id="da77b-116">Advertencia del compilador (nivel 1) CS2023</span><span class="sxs-lookup"><span data-stu-id="da77b-116">Compiler Warning (level 1) CS2023</span></span>  
  
-   <span data-ttu-id="da77b-117">Advertencia del compilador (nivel 1) CS2029</span><span class="sxs-lookup"><span data-stu-id="da77b-117">Compiler Warning (level 1) CS2029</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="da77b-118">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="da77b-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="da77b-119">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="da77b-119">Open the **Properties** page for the project.</span></span> <span data-ttu-id="da77b-120">Para obtener más información, vea [Compilar (Página, Diseñador de proyectos) (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="da77b-120">For details, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="da77b-121">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="da77b-121">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="da77b-122">Modifique la propiedad **Suprimir advertencias**.</span><span class="sxs-lookup"><span data-stu-id="da77b-122">Modify the **Suppress Warnings** property.</span></span>  
  
 <span data-ttu-id="da77b-123">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="da77b-123">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da77b-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="da77b-124">See Also</span></span>  
 [<span data-ttu-id="da77b-125">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="da77b-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="da77b-126">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="da77b-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="da77b-127">Errores del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="da77b-127">C# Compiler Errors</span></span>](../../../csharp/language-reference/compiler-messages/index.md)
