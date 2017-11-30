---
title: Vs basado en cero. Acceso basado en una cadena en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 911f063d6ca9a3f5d88a1f50d9df7f908a488f66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Vs basado en cero. Acceso basado en una cadena en Visual Basic
Este tema se compara cómo [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] y [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] proporcionan acceso a los caracteres de una cadena. El [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] siempre proporciona acceso basado en cero a los caracteres de una cadena, mientras que [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] proporciona acceso basado en cero y basado en uno, dependiendo de la función.  
  
## <a name="one-based"></a>Basado en uno  
 Para obtener un ejemplo de una base uno [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] funcionar, tenga en cuenta el `Mid` función. Toma un argumento que indica la posición del carácter en el que comenzará la subcadena, empezando por la posición 1. El [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> método toma un índice del carácter en la cadena a la que la subcadena consiste en iniciar, empezando por la posición 0. Por lo tanto, si tiene una cadena "ABCDE", los caracteres individuales se numeran 1,2,3,4,5 para su uso con el `Mid` función, pero 0,1,2,3,4 para su uso con el <xref:System.String.Substring%2A?displayProperty=nameWithType> método.  
  
## <a name="zero-based"></a>Basado en cero  
 Para obtener un ejemplo de una base cero [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] funcionar, tenga en cuenta el `Split` función. Divide una cadena y devuelve una matriz que contiene las subcadenas. El [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> método también divide una cadena y devuelve una matriz que contiene las subcadenas. Dado que la `Split` función y <xref:System.String.Split%2A> devuelto del método [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] matrices, deben ser basado en cero.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:System.String.Substring%2A>  
 <xref:System.String.Split%2A>  
 [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
