---
title: "C&#243;mo: Validar cadenas que representan fechas u horas (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "String (tipo de datos), validación"
  - "cadenas [Visual Basic], validar"
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# C&#243;mo: Validar cadenas que representan fechas u horas (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El ejemplo de código siguiente establece un valor `Boolean` que indica si una cadena representa una fecha o una hora válida.  
  
## Ejemplo  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/visualbasic/how-to-validate-strings-_1.vb)]  
  
## Compilar el código  
 Reemplace `("01/01/03")` y `"9:30 PM"` con la fecha y hora que desea validar.  Puede reemplazar la cadena con otra cadena codificada, con una variable `String` o con un método que devuelve una cadena, como `InputBox`.  
  
## Programación eficaz  
 Utilice este método para validar la cadena antes de intentar convertir el objeto `String` en una variable `DateTime`.  Si comprueba previamente la fecha o la hora, puede evitar generar una excepción en tiempo de ejecución.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Information.IsDate%2A>   
 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>   
 [Validar cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)