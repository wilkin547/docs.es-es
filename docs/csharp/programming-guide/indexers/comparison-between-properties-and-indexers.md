---
title: "Comparaci&#243;n entre propiedades e indizadores (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "indizadores [C#], propiedades"
  - "propiedades [C#], frente a indizadores"
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Comparaci&#243;n entre propiedades e indizadores (Gu&#237;a de programaci&#243;n de C#)
Los indizadores son similares a las propiedades.  A excepción de las diferencias que se muestran en la tabla siguiente, todas las reglas definidas para los descriptores de acceso de propiedades también son válidas para los descriptores de acceso de indizadores.  
  
|Propiedad.|Indizador|  
|----------------|---------------|  
|Permite llamar a los métodos como si fueran miembros de datos públicos.|Permite obtener acceso a los elementos de una colección interna de un objeto utilizando la notación de matrices en el propio objeto.|  
|Se obtiene acceso a través de un nombre sencillo.|Se obtiene acceso a través de un índice.|  
|Puede ser un miembro estático o de instancia.|Debe ser un miembro de instancia.|  
|Los descriptores de acceso [get](../../../csharp/language-reference/keywords/get.md) de una propiedad no tienen parámetros.|Los descriptores de acceso `get` de un indizador tienen la misma lista de parámetros formales que el indizador.|  
|Los descriptores de acceso [set](../../../csharp/language-reference/keywords/set.md) de una propiedad contienen el parámetro implícito `value`.|Los descriptores de acceso `set` de un indizador tienen la misma lista de parámetros formales que el indizador, además del parámetro [value](../../../csharp/language-reference/keywords/value.md).|  
|Admite la sintaxis abreviada con [Propiedades autoimplementadas](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).|No admite la sintaxis abreviada.|  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Indizadores](../../../csharp/programming-guide/indexers/index.md)   
 [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)