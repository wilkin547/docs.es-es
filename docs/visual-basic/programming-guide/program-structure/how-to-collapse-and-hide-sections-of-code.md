---
title: 'Cómo: Contraer y ocultar secciones de código (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4497c9586182cca9e2be97dc39e5ccb242725d25
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Cómo: Contraer y ocultar secciones de código (Visual Basic)
El `#Region` directiva permite contraer y ocultar secciones de código en archivos de Visual Basic. El `#Region` directiva le permite especificar un bloque de código que se puede expandir o contraer cuando se utiliza el editor de código de Visual Studio. La capacidad para ocultar selectivamente el código hace que los archivos sean más y más fácil de leer. Para obtener más información, vea [Esquematización](/visualstudio/ide/outlining).  
  
 `#Region` directivas admiten la semántica de bloque de código como `#If...#End If`. Esto significa que no se pueden iniciar en un bloque y terminar en otro; en el mismo bloque deben ser el inicio y fin. `#Region` no se admiten directivas dentro de las funciones.  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a>Para contraer y ocultar una sección de código  
  
-   Sitúe la sección de código entre la `#Region` y `#End Region` instrucciones, como en el ejemplo siguiente:  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     El `#Region` bloque puede usarse varias veces en un archivo de código; por lo tanto, los usuarios pueden definir sus propios bloques de procedimientos y las clases que a su vez, se pueden contraer. `#Region` También pueden anidarse dentro de otros bloques `#Region` bloques.  
  
    > [!NOTE]
    >  Oculta el código no evita que se está compilando y no afecta a `#If...#End If` instrucciones.  
  
## <a name="see-also"></a>Vea también  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [#Region (directiva)](../../../visual-basic/language-reference/directives/region-directive.md)  
 [#If...Then...#Else (directivas)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Esquematización](/visualstudio/ide/outlining)
