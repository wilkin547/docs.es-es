---
title: '#Directiva Region'
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
ms.openlocfilehash: cd53a6079c1564a8c73a0a1a6273fc166d18d3e6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409950"
---
# <a name="region-directive"></a>#Region (Directiva)

Contrae y oculta secciones de código en archivos de Visual Basic.  
  
## <a name="syntax"></a>Sintaxis  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`identifier_string`|Obligatorio. Cadena que actúa como título de una región cuando esta se contrae. Las regiones están contraídas de forma predeterminada.|  
|`#End Region`|Finaliza el bloque `#Region`.|  
  
## <a name="remarks"></a>Observaciones  

 La directiva `#Region` permite especificar un bloque de código que se puede expandir o contraer cuando se usa la característica de esquematización del Editor de código de Visual Studio. Puede colocar, o *anidar*, regiones en otras regiones para agrupar regiones similares.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa la directiva `#Region`.  
  
 [!code-vb[VbVbalrConditionalComp#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>Consulte también

- [#If...Then...#Else (directivas)](if-then-else-directives.md)
- [esquematizar](/visualstudio/ide/outlining)
- [Procedimiento Contracción y ocultación de secciones de código](../../programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
