---
title: "Indizadores (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.indexers"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, indizadores"
  - "indizadores [C#]"
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
caps.latest.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 29
---
# Indizadores (Gu&#237;a de programaci&#243;n de C#)
Los indizadores permiten indizar las instancias de una clase o struct como matrices.  Son similares a [propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md), excepto en que sus descriptores de acceso usan parámetros.  
  
 En el ejemplo siguiente se define una clase genérica y se le proporcionan los métodos de descriptor de acceso simples [get](../../../csharp/language-reference/keywords/get.md) y [set](../../../csharp/language-reference/keywords/set.md) como un medio de asignar y recuperar valores.  La clase `Program` crea una instancia de esta clase para almacenar cadenas.  
  
 [!code-cs[csProgGuideIndexers#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/index_1.cs)]  
  
> [!NOTE]
>  Para obtener más ejemplos, vea [Secciones relacionadas](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).  
  
## Definiciones de cuerpos de expresión  
 Es habitual tener indizadores que simplemente devuelvan de inmediato el resultado de una expresión.  Hay un acceso directo de sintaxis para definir estos indizadores con `=>`:  
  
```c#  
public Customer this[long id] => store.LookupCustomer(id);  
  
```  
  
 El indizador debe ser de solo lectura y no se usa la palabra clave de descriptor de acceso `get`.  
  
## Información general sobre los indizadores  
  
-   Los indizadores permiten indizar objetos de manera similar a como se hace con las matrices.  
  
-   Un descriptor de acceso `get` devuelve un valor.  Un descriptor de acceso `set` asigna un valor.  
  
-   La palabra clave [this](../../../csharp/language-reference/keywords/this.md) se usa para definir los indizadores.  
  
-   La palabra clave [value](../../../csharp/language-reference/keywords/value.md) se usa para definir el valor asignado por el indizador `set`.  
  
-   Los indizadores no tienen que ser indizados por un valor entero; depende de usted cómo definir el mecanismo de búsqueda concreto.  
  
-   Los indizadores se pueden sobrecargar.  
  
-   Los indizadores pueden tener más de un parámetro formal, por ejemplo, al tener acceso a una matriz bidimensional.  
  
##  <a name="BKMK_RelatedSections"></a> Secciones relacionadas  
  
-   [Utilizar indizadores](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [Indizadores en interfaces](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [Comparación entre propiedades e indizadores](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [Restringir la accesibilidad del descriptor de acceso](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)