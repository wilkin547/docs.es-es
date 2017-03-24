---
title: '#Region: directiva | Documentos de Microsoft'
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Region
- vb.#Region
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
caps.latest.revision: 14
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
ms.openlocfilehash: 1c429602a7eee27944f58256992879d25d533d34
ms.lasthandoff: 03/13/2017

---
# <a name="region-directive"></a>#Region: directiva
Contrae y oculta secciones de código en archivos de Visual Basic.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
      #Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`identifier_string`|Obligatorio. Cadena que actúa como título de una región cuando esta se contrae. Las regiones están contraídas de forma predeterminada.|  
|`#End Region`|Finaliza el bloque `#Region`.|  
  
## <a name="remarks"></a>Comentarios  
 La directiva `#Region` permite especificar un bloque de código que se puede expandir o contraer cuando se usa la característica de esquematización del Editor de código de Visual Studio. Puede colocar, o *anidar*, las regiones dentro de otras regiones para agrupar las regiones similar.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la directiva `#Region`.  
  
 [!code-vb[VbVbalrConditionalComp Nº&4;](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [#If... Then... #Else directivas](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Esquematización](https://docs.microsoft.com/visualstudio/ide/outlining)   
 [Contraer y ocultar secciones de código](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
