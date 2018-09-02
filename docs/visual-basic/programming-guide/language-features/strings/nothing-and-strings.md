---
title: Nothing y cadenas en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: d03781209f0f9b021d540bd251c6c6025ad21422
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43425216"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing y cadenas en Visual Basic
El tiempo de ejecución de Visual Basic y [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluar `Nothing` forma diferente cuando se trata de cadenas.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>En tiempo de ejecución de Visual Basic y .NET Framework  
 Considere el ejemplo siguiente:  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 Normalmente, se evalúa como el runtime de Visual Basic `Nothing` como una cadena vacía (""). El [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] no lo hace, sin embargo y producirá una excepción cuando se intenta realizar una operación de cadena en `Nothing`.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
