---
title: "Modificadores de acceso (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "modificadores de acceso [C#], acerca de"
  - "Lenguaje C#, modificadores de acceso"
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
caps.latest.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 32
---
# Modificadores de acceso (Gu&#237;a de programaci&#243;n de C#)
Todos los tipos y miembros de tipo tienen un nivel de accesibilidad, que controla si pueden utilizarse por otro código de su ensamblado u otros ensamblados.  Puede utilizar los modificadores de acceso siguientes para especificar la accesibilidad de un tipo o miembro al declararlo:  
  
 [public](../../../csharp/language-reference/keywords/public.md)  
 Puede obtener acceso al tipo o miembro cualquier otro código del mismo ensamblado o de otro ensamblado que haga referencia a éste.  
  
 [private](../../../csharp/language-reference/keywords/private.md)  
 Solamente puede obtener acceso al tipo o miembro código de la misma clase o struct.  
  
 [protected](../../../csharp/language-reference/keywords/protected.md)  
 Solamente puede obtener acceso al tipo o miembro el código de la misma clase o struct, o bien de una clase derivada de dicha clase.  
  
 [internal](../../../csharp/language-reference/keywords/internal.md)  
 Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado, pero no de un ensamblado distinto.  
  
 `protected internal`  
 Puede obtener acceso al tipo o miembro cualquier código del ensamblado en el que se declara, o bien desde una clase derivada de otro ensamblado.  El acceso desde otro ensamblado debe realizarse dentro de una declaración de clase derivada de la clase en la que se declara el elemento interno protegido y a través de una instancia del tipo de clase derivada.  
  
 En los ejemplos siguientes se muestra cómo especificar modificadores de acceso en un tipo y un miembro:  
  
 [!code-cs[csProgGuideObjects#72](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_1.cs)]  
  
 No todos los tipos o miembros pueden utilizar todos los modificadores de acceso en todos los contextos. Además, en algunos casos, la accesibilidad de un miembro de tipo está restringida por la accesibilidad de su tipo contenedor.  En las secciones siguientes se proporcionan más detalles sobre la accesibilidad.  
  
## Accesibilidad a clases y structs  
 Las clases y struct declarados directamente en un espacio de nombres \(es decir, que no se anidan dentro de otras clases o structs\) pueden ser públicos o internos.  Si no se especifica un modificador de acceso, internal es el valor predeterminado.  
  
 Los miembros de struct, incluyendo clases y structs anidados, pueden declararse como públicos, internos o privados.  Los miembros de clase \(incluyendo clases y structs anidados\) pueden ser públicos, internos protegidos, protegidos, internos o privados.  El nivel de acceso para los miembros de clase y los miembros de struct, incluyendo clases y structs anidados, es privado de forma predeterminada.  No se puede obtener acceso a tipos anidados privados desde fuera del tipo contenedor.  
  
 Las clases derivadas no pueden tener mayor accesibilidad que sus tipos base.  En otras palabras, no puede tener una clase pública `B` que se derive de una clase interna `A`.  Si se permitiera, `A` se haría pública, porque se puede obtener acceso a todos los miembros internos o protegidos de `A` desde la clase derivada.  
  
 Puede permitir a otros ensamblados concretos el acceso a sus tipos internos utilizando el atributo InternalsVisibleTo.  Para obtener más información, vea [Ensamblados de confianza](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Accesibilidad de un miembro de clase y struct  
 Los miembros de clase \(incluyendo clases y structs anidados\) pueden declararse con cualquiera de los cinco tipos de acceso.  Los miembros de struct no pueden declararse como protegidos porque los structs no admiten la herencia.  
  
 Normalmente, la accesibilidad de un miembro no es mayor que la accesibilidad del tipo que lo contiene.  Sin embargo, un miembro público de una clase interna podría ser accesible desde fuera del ensamblado si el miembro implementa los métodos de interfaz o invalida los métodos virtuales definidos en una clase base pública.  
  
 El tipo de cualquier miembro que sea un campo, propiedad o evento debe ser al menos tan accesible como el miembro en sí.  De igual forma, el tipo de valor devuelto y los tipos de parámetro de cualquier miembro que sea un método, indizador o delegado deben ser al menos tan accesibles como el miembro en sí.  Por ejemplo, no puede tener un método público `M` que devuelva una clase `C` a menos que `C` sea también pública.  De igual forma, no puede tener una propiedad protegida de tipo `A` si `A` se declara como privado.  
  
 Los operadores definidos por el usuario siempre deben declararse como públicos.  Para obtener más información, vea [operador](../../../csharp/language-reference/keywords/operator.md).  
  
 Los destructores no pueden tener modificadores de accesibilidad.  
  
 Para establecer el nivel de acceso para un miembro de clase o struct, agregue la palabra clave adecuada a la declaración del miembro, como se muestra en el ejemplo siguiente.  
  
 [!code-cs[csProgGuideObjects#73](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_2.cs)]  
  
> [!NOTE]
>  El nivel de accesibilidad interno protegido significa protegido O interno, no protegido E interno.  Es decir, se puede tener acceso a un miembro interno protegido desde cualquier clase del mismo ensamblado, incluidas las clases derivadas.  Para limitar la accesibilidad sólo a clases derivadas en el mismo ensamblado, declare la propia clase como interna y declare sus miembros como protegidos.  
  
## Otros tipos  
 Las interfaces declaradas directamente en un espacio de nombres pueden declararse como públicas o internas y, al igual que las clases y structs, el valor predeterminado de las interfaces es el acceso interno.  Los miembros de interfaz son siempre públicos porque el propósito de una interfaz es permitir que otros tipos tengan acceso a una clase o struct.  No se pueden aplicar modificadores de acceso a los miembros de interfaz.  
  
 Los miembros de enumeración son siempre públicos y no se puede aplicar ningún modificador de acceso.  
  
 Los delegados se comportan como las clases y structs.  De forma predeterminada, tienen acceso interno cuando se declara directamente en un espacio de nombres y acceso privado cuando se anidan.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Interfaces](../../../csharp/programming-guide/interfaces/index.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [clase](../../../csharp/language-reference/keywords/class.md)   
 [struct](../../../csharp/language-reference/keywords/struct.md)   
 [interfaz](../../../csharp/language-reference/keywords/interface.md)