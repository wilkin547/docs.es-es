---
title: /optioncompare
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6f602e0b0b23345bf1f5aae843bd44bd2642bc9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="optioncompare"></a><span data-ttu-id="96398-102">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="96398-102">/optioncompare</span></span>
<span data-ttu-id="96398-103">Especifica la forma en que se realizan las comparaciones de cadenas.</span><span class="sxs-lookup"><span data-stu-id="96398-103">Specifies how string comparisons are made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96398-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96398-104">Syntax</span></span>  
  
```  
/optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a><span data-ttu-id="96398-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96398-105">Remarks</span></span>  
 <span data-ttu-id="96398-106">Puede especificar `/optioncompare` en uno de dos formas: `/optioncompare:binary` usar comparaciones de cadenas binarias y `/optioncompare:text` usar comparaciones de cadenas de texto.</span><span class="sxs-lookup"><span data-stu-id="96398-106">You can specify `/optioncompare` in one of two forms: `/optioncompare:binary` to use binary string comparisons, and `/optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="96398-107">De forma predeterminada, el compilador utiliza `/optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="96398-107">By default, the compiler uses `/optioncompare:binary`.</span></span>  
  
 <span data-ttu-id="96398-108">En Microsoft Windows, la página de códigos que se va a usar determina el criterio de ordenación binario.</span><span class="sxs-lookup"><span data-stu-id="96398-108">In Microsoft Windows, the code page being used determines the binary sort order.</span></span> <span data-ttu-id="96398-109">Un criterio de ordenación binario típico es como sigue:</span><span class="sxs-lookup"><span data-stu-id="96398-109">A typical binary sort order is as follows:</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="96398-110">Las comparaciones de cadenas basadas en el texto se basan en un criterio de ordenación de texto entre mayúsculas y minúsculas determinado por la configuración regional del sistema.</span><span class="sxs-lookup"><span data-stu-id="96398-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="96398-111">Un criterio de ordenación de texto habitual es como sigue:</span><span class="sxs-lookup"><span data-stu-id="96398-111">A typical text sort order is as follows:</span></span>  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set-optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="96398-112">Para establecer /optioncompare en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="96398-112">To set /optioncompare in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="96398-113">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="96398-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="96398-114">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="96398-114">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="96398-115">Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="96398-115">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="96398-116">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="96398-116">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="96398-117">Modifique el valor en el **Option Compare** cuadro.</span><span class="sxs-lookup"><span data-stu-id="96398-117">Modify the value in the **Option Compare** box.</span></span>  
  
### <a name="to-set-optioncompare-programmatically"></a><span data-ttu-id="96398-118">Para establecer /optioncompare mediante programación</span><span class="sxs-lookup"><span data-stu-id="96398-118">To set /optioncompare programmatically</span></span>  
  
-   <span data-ttu-id="96398-119">Vea [Option Compare (instrucción)](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="96398-119">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="96398-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="96398-120">Example</span></span>  
 <span data-ttu-id="96398-121">El siguiente código compila `ProjFile.vb` y utiliza comparaciones de cadenas binarias.</span><span class="sxs-lookup"><span data-stu-id="96398-121">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="96398-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="96398-122">See Also</span></span>  
 [<span data-ttu-id="96398-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96398-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="96398-124">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="96398-124">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="96398-125">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="96398-125">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="96398-126">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="96398-126">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="96398-127">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="96398-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="96398-128">Option Compare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="96398-128">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="96398-129">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="96398-129">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
