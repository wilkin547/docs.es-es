---
title: Directivas
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: b5fcf3cb8801bc99dd2096c28cc41ebefeb34592
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410002"
---
# <a name="directives-visual-basic"></a><span data-ttu-id="19077-102">Directivas de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19077-102">Directives (Visual Basic)</span></span>

<span data-ttu-id="19077-103">Los temas en esta sección documentan las directivas del compilador de código fuente de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="19077-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="19077-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="19077-104">In This Section</span></span>  

 <span data-ttu-id="19077-105">[Directiva de #Const](const-directive.md) : definir una constante del compilador</span><span class="sxs-lookup"><span data-stu-id="19077-105">[#Const Directive](const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="19077-106">[Directiva de #ExternalSource](externalsource-directive.md) : indicar una asignación entre líneas de código fuente y texto externo al origen</span><span class="sxs-lookup"><span data-stu-id="19077-106">[#ExternalSource Directive](externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="19077-107">[#If... Then... #Else directivas](if-then-else-directives.md) : compilar bloques de código seleccionados</span><span class="sxs-lookup"><span data-stu-id="19077-107">[#If...Then...#Else Directives](if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="19077-108">[Directiva de #Region](region-directive.md) : contraer y ocultar secciones de código en el editor de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="19077-108">[#Region Directive](region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="19077-109">**#Disable, #Enable** : deshabilitar y habilitar advertencias específicas para las regiones de código.</span><span class="sxs-lookup"><span data-stu-id="19077-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="19077-110">También puede deshabilitar y habilitar una lista separada por comas de códigos de advertencia.</span><span class="sxs-lookup"><span data-stu-id="19077-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="19077-111">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="19077-111">Related Sections</span></span>  

 [<span data-ttu-id="19077-112">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19077-112">Visual Basic Language Reference</span></span>](../index.md)  
  