---
title: "C&#243;mo: Crear cadenas mediante un objeto StringBuilder en Visual Basic | Microsoft Docs"
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
  - "StringBuilder (clase)"
  - "cadenas [Visual Basic], mediante StringBuilder"
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# C&#243;mo: Crear cadenas mediante un objeto StringBuilder en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Este ejemplo crea una cadena larga a partir de muchas cadenas más pequeñas mediante la clase <xref:System.Text.StringBuilder>.  La clase <xref:System.Text.StringBuilder> es más eficaz que el operador `&=` para concatenar muchas cadenas.  
  
## Ejemplo  
 En el ejemplo siguiente se crea una instancia de la clase <xref:System.Text.StringBuilder>, se anexan 1.000 cadenas a esa instancia y, a continuación, se devuelve su representación de cadena.  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## Vea también  
 [Utilizar la clase StringBuilder](../Topic/Using%20the%20StringBuilder%20Class%20in%20the%20.NET%20Framework.md)   
 [&\= \(Operador\)](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)   
 [Cadenas](../../../../visual-basic/programming-guide/language-features/strings/index.md)   
 [Crear cadenas nuevas](../Topic/Creating%20New%20Strings%20in%20the%20.NET%20Framework.md)   
 [Manipular cadenas](../Topic/Manipulating%20Strings%20in%20the%20.NET%20Framework.md)   
 [Strings Sample](http://msdn.microsoft.com/es-es/be9e82a3-dc95-4aaa-9396-61b66e467e02)