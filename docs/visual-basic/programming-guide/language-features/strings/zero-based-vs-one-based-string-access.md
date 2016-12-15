---
title: "Acceso de base cero y de base uno a a cadenas en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "cadenas [Visual Basic], indizar"
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Acceso de base cero y de base uno a a cadenas en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

En este tema se compara cómo [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] y [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] proporcionan acceso a los caracteres de una cadena.  [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] siempre proporciona acceso basado en cero a los caracteres de una cadena, mientras que [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona acceso basado en cero y basado en uno, dependiendo de la función.  
  
## Basado en uno  
 Para obtener un ejemplo de una función de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] basada en uno, observe la función `Mid`.  Toma un argumento que indica la posición de carácter en la que comenzará la subcadena, a partir de la posición 1.  El método <xref:System.String.Substring%2A?displayProperty=fullName> de [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] toma un índice del carácter de la cadena donde debe empezar la subcadena, a partir de la posición 0.  Así, si tiene la cadena "ABCDE", los caracteres individuales se numeran 1,2,3,4,5 para su uso con la función `Mid`, pero 0,1,2,3,4 para su uso con el método <xref:System.String.Substring%2A?displayProperty=fullName>.  
  
## Basado en cero  
 Para obtener un ejemplo de una función de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] basada en cero, observe la función `Split`.  Divide una cadena y devuelve una matriz que contiene las subcadenas.  El método <xref:System.String.Split%2A?displayProperty=fullName> de [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] también divide una cadena y devuelve una matriz que contiene las subcadenas.  Puesto que la función `Split` y el método <xref:System.String.Split%2A> devuelven matrices de [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)], deben ser estar basados en cero.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>   
 <xref:Microsoft.VisualBasic.Strings.Split%2A>   
 <xref:System.String.Substring%2A>   
 <xref:System.String.Split%2A>   
 [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)