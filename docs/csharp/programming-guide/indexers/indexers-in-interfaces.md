---
title: "Indizadores en interfaces (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "descriptores de acceso [C#], indizadores"
  - "indizadores [C#], en interfaces"
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# Indizadores en interfaces (Gu&#237;a de programaci&#243;n de C#)
Las propiedades se pueden declarar en una [interfaz](../../../csharp/language-reference/keywords/interface.md).  Los descriptores de acceso de los indizadores de interfaz se diferencian de los descriptores de acceso de los indizadores de [clase](../../../csharp/language-reference/keywords/class.md) en los siguientes aspectos:  
  
-   Los descriptores de acceso de interfaz no utilizan modificadores.  
  
-   Un identificador de acceso de interfaz no tiene cuerpo.  
  
 Así, el propósito del descriptor de acceso es indicar si el indizador es de lectura y escritura, de sólo lectura o de sólo escritura.  
  
 A continuación se muestra un ejemplo de descriptor de acceso de un indizador de interfaz:  
  
 [!code-cs[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/indexers-in-interfaces_1.cs)]  
  
 La firma de un indizador debe ser diferente de las firmas de los demás indizadores declarados en la misma interfaz.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo se implementan indizadores de interfaz:  
  
 [!code-cs[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/indexers-in-interfaces_2.cs)]  
  
 En el ejemplo anterior, se podría usar la implementación de miembro de interfaz explícito mediante el nombre completo del miembro de interfaz.  Por ejemplo:  
  
```  
public string ISomeInterface.this   
{   
}   
```  
  
 Sin embargo, el nombre completo sólo es necesario para evitar la ambigüedad cuando la clase implementa más de una interfaz con la misma firma de indizador.  Por ejemplo, si una clase  `Employee` implementa dos interfaces, `ICitizen` y `IEmployee`, y ambas tienen la misma firma de indizador, será necesario implementar explícitamente el miembro de interfaz.  Es decir, la siguiente declaración de indizador:  
  
```  
public string IEmployee.this   
{   
}   
```  
  
 implementa el indizador en la interfaz `IEmployee`, mientras que la declaración:  
  
```  
public string ICitizen.this   
{   
}   
```  
  
 implementa el indizador en la interfaz `ICitizen`.  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Indizadores](../../../csharp/programming-guide/indexers/index.md)   
 [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Interfaces](../../../csharp/programming-guide/interfaces/index.md)