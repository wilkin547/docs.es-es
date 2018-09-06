---
title: Directivas de Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: 38d54feae5cf7bf41a825d1f6000811e2b56f319
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43736612"
---
# <a name="directives-visual-basic"></a><span data-ttu-id="d247b-102">Directivas de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d247b-102">Directives (Visual Basic)</span></span>
<span data-ttu-id="d247b-103">Los temas en esta sección documentan las directivas del compilador de código fuente de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d247b-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d247b-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d247b-104">In This Section</span></span>  
 <span data-ttu-id="d247b-105">[#Const (directiva)](../../../visual-basic/language-reference/directives/const-directive.md) : definir una constante del compilador</span><span class="sxs-lookup"><span data-stu-id="d247b-105">[#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="d247b-106">[#ExternalSource (directiva)](../../../visual-basic/language-reference/directives/externalsource-directive.md) --indicar una asignación entre líneas de código fuente y texto externo al código fuente</span><span class="sxs-lookup"><span data-stu-id="d247b-106">[#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="d247b-107">[#If... Then... #Else directivas](../../../visual-basic/language-reference/directives/if-then-else-directives.md) --compilar bloques de código seleccionados</span><span class="sxs-lookup"><span data-stu-id="d247b-107">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="d247b-108">[#Region (directiva)](../../../visual-basic/language-reference/directives/region-directive.md) : contraer y ocultar secciones de código en el editor de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d247b-108">[#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="d247b-109">**#Disable, #Enable** : deshabilita y habilita advertencias específicas para regiones de código.</span><span class="sxs-lookup"><span data-stu-id="d247b-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="d247b-110">También puede deshabilitar y habilitar una lista separada por comas de códigos de advertencia.</span><span class="sxs-lookup"><span data-stu-id="d247b-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d247b-111">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="d247b-111">Related Sections</span></span>  
 [<span data-ttu-id="d247b-112">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d247b-112">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
  
 [<span data-ttu-id="d247b-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d247b-113">Visual Basic</span></span>](../../../visual-basic/index.md)
