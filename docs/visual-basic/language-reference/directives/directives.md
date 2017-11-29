---
title: Directivas de Visual Basic
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8219f17f1b8093b4d02b370c7b008101923b1873
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="directives-visual-basic"></a><span data-ttu-id="42566-102">Directivas de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="42566-102">Directives (Visual Basic)</span></span>
<span data-ttu-id="42566-103">Los temas en esta sección documentan las directivas del compilador de código fuente de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="42566-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="42566-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="42566-104">In This Section</span></span>  
 <span data-ttu-id="42566-105">[#Const (directiva)](../../../visual-basic/language-reference/directives/const-directive.md) : definir una constante del compilador</span><span class="sxs-lookup"><span data-stu-id="42566-105">[#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="42566-106">[#ExternalSource (directiva)](../../../visual-basic/language-reference/directives/externalsource-directive.md) --indica una asignación entre líneas de código fuente y texto externo al código fuente</span><span class="sxs-lookup"><span data-stu-id="42566-106">[#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="42566-107">[#If... Then... #Else directivas](../../../visual-basic/language-reference/directives/if-then-else-directives.md) : compilan bloques de código seleccionados</span><span class="sxs-lookup"><span data-stu-id="42566-107">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="42566-108">[#Region (directiva)](../../../visual-basic/language-reference/directives/region-directive.md) : contrae y oculta secciones de código en el editor de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="42566-108">[#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="42566-109">**#Disable, #Enable** : deshabilita y habilita advertencias específicas para regiones de código.</span><span class="sxs-lookup"><span data-stu-id="42566-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="42566-110">También puede deshabilitar y habilitar una lista separada por comas de códigos de advertencia.</span><span class="sxs-lookup"><span data-stu-id="42566-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="42566-111">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="42566-111">Related Sections</span></span>  
 [<span data-ttu-id="42566-112">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="42566-112">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
  
 [<span data-ttu-id="42566-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="42566-113">Visual Basic</span></span>](../../../visual-basic/index.md)
