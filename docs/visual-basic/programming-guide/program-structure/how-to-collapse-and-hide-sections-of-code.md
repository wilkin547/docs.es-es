---
title: "Cómo: contraer y ocultar secciones de código (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 200a90b6983277d46b6e5c7b27ee4a90ecf88c40
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Cómo: Contraer y ocultar secciones de código (Visual Basic)
El `#Region` directiva permite contraer y ocultar secciones de código en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] archivos. El `#Region` directiva permite especificar un bloque de código que se puede expandir o contraer cuando se utiliza el [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] editor de código. La capacidad para ocultar código de forma selectiva hace los archivos más manejable y más fácil de leer. Para obtener más información, consulte [esquema](https://docs.microsoft.com/visualstudio/ide/outlining).  
  
 `#Region`directivas admiten semántica del bloque de código como `#If...#End If`. Esto significa que no pueden empezar en un bloque y terminar en otro; el inicio y final deben ser del mismo bloque. `#Region`no se admiten directivas dentro de las funciones.  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a>Para contraer y ocultar una sección de código  
  
-   Sitúe la sección de código entre el `#Region` y `#End Region` instrucciones, como en el ejemplo siguiente:  
  
     [!code-vb[VbVbalrConditionalComp Nº&6;](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     El `#Region` bloque puede utilizarse varias veces en un archivo de código; por lo tanto, los usuarios pueden definir sus propios bloques de procedimientos y clases que a su vez, se pueden contraer. `#Region`También pueden anidarse dentro de otros bloques `#Region` bloques.  
  
    > [!NOTE]
    >  Ocultar el código no impide que se está compilando y no afecta a `#If...#End If` instrucciones.  
  
## <a name="see-also"></a>Vea también  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [#Region (directiva)](../../../visual-basic/language-reference/directives/region-directive.md)   
 [#If... Then... #Else directivas](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Esquematización](https://docs.microsoft.com/visualstudio/ide/outlining)
