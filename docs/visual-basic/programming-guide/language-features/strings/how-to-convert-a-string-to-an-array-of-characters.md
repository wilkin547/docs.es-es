---
title: "C&#243;mo: Convertir una cadena en una matriz de caracteres en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "matrices [Visual Basic], convertir cadenas en"
  - "matrices de caracteres, convertir cadenas"
  - "ejemplos [Visual Basic], conversión de cadenas"
  - "conversión de cadenas [Visual Basic], matrices"
  - "cadenas [Visual Basic], convertir en matrices"
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Convertir una cadena en una matriz de caracteres en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

En ocasiones es útil tener información sobre los caracteres de una cadena y de su posición dentro de la misma, como cuando se está analizando una cadena.  Este ejemplo muestra cómo se puede obtener una matriz de los caracteres que contiene una cadena llamando al método <xref:System.String.ToCharArray%2A> de la cadena.  
  
## Ejemplo  
 Este ejemplo muestra cómo dividir una cadena en una matriz de caracteres \(`Char`\), y cómo dividir una cadena en una matriz `String` de sus caracteres de texto Unicode.  El motivo de esta distinción es que los caracteres de texto Unicode pueden constar de dos o más caracteres `Char` \(como un par suplente o una secuencia de caracteres combinada\).  Para obtener más información, vea <xref:System.Globalization.TextElementEnumerator> y el "Estándar Unicode" en la dirección http:\/\/www.unicode.org.  
  
 [!code-vb[VbVbalrStrings#75](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_1.vb)]  
  
## Ejemplo  
 Es más difícil dividir una cadena en sus caracteres de texto Unicode, pero es necesario hacerlo si necesita información sobre la representación visual de una cadena.  Este ejemplo utiliza el método <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> para obtener información sobre los caracteres de texto Unicode que constituyen una cadena.  
  
 [!code-vb[VbVbalrStrings#76](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_2.vb)]  
  
## Vea también  
 <xref:System.String.Chars%2A>   
 <xref:System.Globalization.StringInfo?displayProperty=fullName>   
 [Cómo: Obtener acceso a caracteres de cadenas](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)   
 [Conversión entre cadenas y otros tipos de datos en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)   
 [Cadenas](../../../../visual-basic/programming-guide/language-features/strings/index.md)