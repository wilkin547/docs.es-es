---
title: Directivas
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: b5e857198351b30c0d7a38dce1a9e6d1209b5258
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838148"
---
# <a name="directives-visual-basic"></a><span data-ttu-id="22e9c-102">Directivas de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="22e9c-102">Directives (Visual Basic)</span></span>

<span data-ttu-id="22e9c-103">Los temas en esta sección documentan las directivas del compilador de código fuente de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="22e9c-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22e9c-104">Esta sección</span><span class="sxs-lookup"><span data-stu-id="22e9c-104">In This Section</span></span>  

 <span data-ttu-id="22e9c-105">[Directiva de #Const](../../../visual-basic/language-reference/directives/const-directive.md) : definir una constante del compilador</span><span class="sxs-lookup"><span data-stu-id="22e9c-105">[#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="22e9c-106">[Directiva de #ExternalSource](../../../visual-basic/language-reference/directives/externalsource-directive.md) : indicar una asignación entre líneas de código fuente y texto externo al origen</span><span class="sxs-lookup"><span data-stu-id="22e9c-106">[#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="22e9c-107">[#If... Then... #Else directivas](../../../visual-basic/language-reference/directives/if-then-else-directives.md) : compilar bloques de código seleccionados</span><span class="sxs-lookup"><span data-stu-id="22e9c-107">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="22e9c-108">[Directiva de #Region](../../../visual-basic/language-reference/directives/region-directive.md) : contraer y ocultar secciones de código en el editor de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="22e9c-108">[#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="22e9c-109">**#Disable, #Enable** : deshabilitar y habilitar advertencias específicas para las regiones de código.</span><span class="sxs-lookup"><span data-stu-id="22e9c-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="22e9c-110">También puede deshabilitar y habilitar una lista separada por comas de códigos de advertencia.</span><span class="sxs-lookup"><span data-stu-id="22e9c-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="22e9c-111">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="22e9c-111">Related Sections</span></span>  

 [<span data-ttu-id="22e9c-112">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="22e9c-112">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
  