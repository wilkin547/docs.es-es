---
title: "Nombres de atributos y elementos XML declarados (Visual Basic) | Microsoft Docs"
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
  - "nombres de atributos [XML in Visual Basic]"
  - "declaraciones [XML en Visual Basic]"
  - "nombres de elementos [XML in Visual Basic]"
  - "nombres en literales XML"
  - "literales XML [Visual Basic], nombres de elementos"
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Nombres de atributos y elementos XML declarados (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

En este tema se proporcionan las instrucciones de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] para denominar elementos XML y atributos en literales XML. En un literal XML, se puede especificar un nombre local o un nombre completo.  Un nombre completo se compone de un prefijo de espacio de nombres XML, dos puntos y un nombre local.  Para obtener más información sobre los prefijos de espacio de nombres XML, vea [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## Reglas  
 El nombre local de un elemento o atributo en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] debe adherirse a las reglas siguientes.  
  
-   Puede comenzar con un espacio de nombres.  Debe comenzar por un carácter alfabético o un signo de subrayado \(`_`\).  
  
-   Debe contener únicamente caracteres alfabéticos, dígitos decimales, subrayados, puntos \(.\) y guiones \(\-\).  
  
-   No puede superar los 1,024 caracteres de longitud.  
  
-   Los dos puntos que aparecen en los nombres indican la demarcación del espacio de nombres.  Por consiguiente, únicamente se pueden usar los dos puntos para especificar un espacio de nombres XML de un nombre determinado.  
  
 Además, debe adherirse a la instrucción siguiente.  
  
-   La especificación de XML 1.0 se reserva todos los nombres que comienzan con la cadena "xml", ya sea en mayúsculas o minúsculas.  Por consiguiente, no use esos nombres para los nombres de elemento y atributo.  
  
### Directrices sobre longitud de nombres  
 A efectos prácticos, los nombres debe ser tan cortos como sea posible aunque tienen que identificar claramente la naturaleza del elemento.  Esto mejora la legibilidad de su código y reduce la longitud de línea y el tamaño del archivo de origen.  
  
 Sin embargo, los nombres no deben ser tan cortos que no describan adecuadamente el elemento o cómo lo usa el código.  Esto es importante para la legibilidad del código.  Si otro usuario intenta entenderlo o si el propio usuario lo examina después de mucho tiempo de haberlo escrito, unos nombres de elemento adecuados pueden ahorrar mucho tiempo.  
  
## Distinguir mayúsculas de minúsculas en los nombres  
 Los nombres de los elementos XML distinguen entre mayúsculas y minúsculas.  Es decir, cuando el compilador de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compara dos nombres cuya única diferencia está en las mayúsculas o minúsculas, los interpreta como nombres distintos.  Por ejemplo, interpreta `ABC` y `abc` como nombres que hacen referencia a distintos elementos.  
  
## Espacios de nombres XML  
 Al crear un literal de elemento XML, puede especificar el prefijo de espacio de nombres XML para el nombre de elemento.  Para obtener más información, vea [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## Vea también  
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)