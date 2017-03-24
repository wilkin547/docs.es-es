---
title: "La variable utiliza un tipo de automatización no admitido en Visual Basic | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID458
dev_langs:
- VB
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
caps.latest.revision: 12
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
ms.openlocfilehash: 58403a9aacc00e659807aff83031fe2ac80bbb40
ms.lasthandoff: 03/13/2017

---
# <a name="variable-uses-an-automation-type-not-supported-in-visual-basic"></a>La variable utiliza un tipo de Automation no compatible con Visual Basic
Ha intentado utilizar una variable definida en una biblioteca de tipos o la biblioteca de objetos que tiene un tipo de datos no admite [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Utilizar una variable de un tipo reconocido por [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
     O bien  
  
-   Si se produce este error al usar `FileGet` o `FileGetOBject`, asegúrese de que el archivo que está intentando usar se escribió para con `FilePut` o `FilePutObject`.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)
