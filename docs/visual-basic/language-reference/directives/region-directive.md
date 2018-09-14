---
title: '#Directiva de región (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
ms.openlocfilehash: 204b53751fce4f9a3e038ae7c44634522d54657c
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "45519934"
---
# <a name="region-directive"></a>#Region (Directiva)
Contrae y oculta secciones de código en archivos de Visual Basic.  
  
## <a name="syntax"></a>Sintaxis  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`identifier_string`|Requerido. Cadena que actúa como título de una región cuando esta se contrae. Las regiones están contraídas de forma predeterminada.|  
|`#End Region`|Finaliza el bloque `#Region`.|  
  
## <a name="remarks"></a>Comentarios  
 La directiva `#Region` permite especificar un bloque de código que se puede expandir o contraer cuando se usa la característica de esquematización del Editor de código de Visual Studio. Puede colocar, o *anidar*, las regiones dentro de otras regiones para agrupar regiones similares.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la directiva `#Region`.  
  
 [!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [#If...Then...#Else (directivas)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Esquematización](/visualstudio/ide/outlining)  
 [Contraer y ocultar secciones de código](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
