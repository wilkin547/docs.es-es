---
title: "Ventajas de los gen&#233;ricos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "genéricos [C#], ventajas"
ms.assetid: 80f037cd-9ea7-48be-bfc1-219bfb2d4277
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# Ventajas de los gen&#233;ricos (Gu&#237;a de programaci&#243;n de C#)
Los tipos genéricos proporcionan la solución a una limitación de las versiones anteriores de Common Language Runtime y del lenguaje C\#, en los que se realiza una generalización mediante la conversión de tipos a y desde el tipo base universal <xref:System.Object>.  Con la creación de una clase genérica, se puede crear una colección que garantiza la seguridad de tipos en tiempo de compilación.  
  
 Las limitaciones del uso de clases de colección no genéricas se pueden demostrar escribiendo un breve programa que utilice la clase de colección <xref:System.Collections.ArrayList> de la biblioteca de clases base de .NET Framework.  <xref:System.Collections.ArrayList> es una clase de colección muy conveniente, que se puede utilizar sin modificar para almacenar tipos de referencia o tipos de valor.  
  
 [!code-cs[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/csharp/benefits-of-generics_1.cs)]  
  
 Pero esta conveniencia tiene su costo.  Cualquier referencia o tipo de valor agregado a un objeto <xref:System.Collections.ArrayList> se convierte implícitamente a <xref:System.Object>.  Si los elementos son tipos de valor, se les debe aplicar la conversión boxing cuando se agregan a la lista y la conversión unboxing cuando se recuperan.  Tanto las operaciones de conversión de tipos como las de conversiones boxing y unboxing reducen el rendimiento; el efecto de las conversiones boxing y unboxing puede ser muy notable en los casos en los que se deben recorrer en iteración colecciones extensas.  
  
 La otra limitación es la ausencia de comprobación de tipos en tiempo de compilación; dado que un objeto <xref:System.Collections.ArrayList> convierte todo a <xref:System.Object>, en tiempo de compilación no hay forma de evitar que el código de cliente haga cosas como la siguiente:  
  
 [!code-cs[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/csharp/benefits-of-generics_2.cs)]  
  
 Aunque es perfectamente válido y a veces intencionado si se crea una colección heterogénea, es probable que la combinación de cadenas y valores `ints` en un objeto <xref:System.Collections.ArrayList> único sea un error de programación, el cual no se detectará hasta el tiempo de ejecución.  
  
 En las versiones 1.0 y 1.1 del lenguaje C\#, se podían evitar los riesgos de utilizar código generalizado en las clases de colección de la biblioteca de clases base de .NET Framework escribiendo colecciones propias específicas del tipo.  Claro está que, como dicha clase no se puede reutilizar para más de un tipo de datos, se pierden las ventajas de la generalización y se debe volver a escribir la clase para cada uno de los tipos que se van a almacenar.  
  
 Lo que <xref:System.Collections.ArrayList> y otras clases similares realmente necesitan es un modo de que el código de cliente especifique, por instancias, el tipo de datos particular que se va a utilizar.  Eso eliminaría la necesidad de convertir a `T:System.Object` y también haría posible que el compilador realizara la comprobación de tipos.  Es decir, <xref:System.Collections.ArrayList> necesita un parámetro de tipo.  Eso es precisamente lo que los tipos genéricos proporcionan.  En la colección genérica <xref:System.Collections.Generic.List%601>, en el espacio de nombres `N:System.Collections.Generic`, la misma operación de agregar elementos a la colección tiene la apariencia siguiente:  
  
 [!code-cs[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/csharp/benefits-of-generics_3.cs)]  
  
 En el código de cliente, la única sintaxis que se agrega con <xref:System.Collections.Generic.List%601> en comparación con <xref:System.Collections.ArrayList> es el argumento de tipo en la declaración y creación de instancias.  A cambio de esta complejidad de codificación ligeramente mayor, se puede crear una lista que no sólo es más segura que <xref:System.Collections.ArrayList>, sino que también es bastante más rápida, en especial cuando los elementos de lista son tipos de valor.  
  
## Vea también  
 <xref:System.Collections.Generic>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Conversión boxing y conversión unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)   
 [Collections Best Practices](http://go.microsoft.com/fwlink/?LinkId=112403)