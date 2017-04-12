---
title: Nothing y cadenas en Visual Basic | Documentos de Microsoft
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
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 56fc47ba2523825224aae3264e965d462cf4c3b6
ms.lasthandoff: 03/13/2017

---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing y cadenas en Visual Basic
El [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] en tiempo de ejecución y la [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] evaluar `Nothing` diferente cuando se trata de cadenas.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>En tiempo de ejecución de Visual Basic y .NET Framework  
 Considere el ejemplo siguiente:  
  
 [!code-vb[VbVbalrStrings&#47;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 El [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] normalmente se evalúa en tiempo de ejecución `Nothing` como una cadena vacía (""). El [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] no es así, sin embargo y producirá una excepción cuando intenta realizar una operación de cadena en `Nothing`.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
