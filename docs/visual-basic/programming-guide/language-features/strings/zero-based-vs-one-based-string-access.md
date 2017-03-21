---
title: De base cero. Acceso basado en una cadena en Visual Basic | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
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
ms.openlocfilehash: 6cd2cab888bf336151ed26968119431f4ffc75f4
ms.lasthandoff: 03/13/2017

---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>De base cero. Acceso basado en una cadena en Visual Basic
Este tema se compara cómo [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] y [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] proporcionan acceso a los caracteres de una cadena. El [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] siempre proporciona acceso basado en cero a los caracteres de una cadena, mientras que [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona acceso basado en cero y basado en uno, dependiendo de la función.  
  
## <a name="one-based"></a>Basado en uno  
 Para obtener un ejemplo de base uno [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] función, considere la `Mid` (función). Toma un argumento que indica la posición del carácter en el que comenzará la subcadena, empezando por la posición 1. El [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Substring%2A?displayProperty=fullName>método toma un índice del carácter de la cadena en la que la subcadena debe iniciar, empezando por la posición 0.</xref:System.String.Substring%2A?displayProperty=fullName> Por lo tanto, si tiene una cadena "ABCDE", los caracteres individuales se numeran 1,2,3,4,5 para su uso con el `Mid` función, pero 0,1,2,3,4 para su uso con el <xref:System.String.Substring%2A?displayProperty=fullName>método.</xref:System.String.Substring%2A?displayProperty=fullName>  
  
## <a name="zero-based"></a>Basado en cero  
 Para obtener un ejemplo basado en cero [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] función, considere la `Split` (función). Divide una cadena y devuelve una matriz que contiene las subcadenas. El [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Split%2A?displayProperty=fullName>método también divide una cadena y devuelve una matriz que contiene las subcadenas.</xref:System.String.Split%2A?displayProperty=fullName> Dado que la `Split` (función) y <xref:System.String.Split%2A>método devuelven [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] matrices, deben ser basado en cero.</xref:System.String.Split%2A>  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A></xref:Microsoft.VisualBasic.Strings.Mid%2A>   
 <xref:Microsoft.VisualBasic.Strings.Split%2A></xref:Microsoft.VisualBasic.Strings.Split%2A>   
 <xref:System.String.Substring%2A></xref:System.String.Substring%2A>   
 <xref:System.String.Split%2A></xref:System.String.Split%2A>   
 [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
