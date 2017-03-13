---
title: "C&#243;mo: Declarar y usar propiedades de lectura y escritura (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "obtener el descriptor de acceso [C#], declarar propiedades"
  - "set (descriptor de acceso) [C#]"
  - "propiedades [C#], declarar"
  - "propiedades de lectura/escritura [C#]"
  - "descriptores de acceso [C#], declarar propiedades con"
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# C&#243;mo: Declarar y usar propiedades de lectura y escritura (Gu&#237;a de programaci&#243;n de C#)
Las propiedades proporcionan la comodidad de utilizar miembros de datos públicos sin los riesgos que implica el acceso no protegido y sin control ni comprobación a los datos de un objeto.  Esto se logra a través de los *descriptores de acceso*: métodos especiales que asignan y recuperan los valores del miembro de datos subyacente.  El descriptor de acceso [set](../../../csharp/language-reference/keywords/set.md) permite asignar los miembros de datos y el descriptor de acceso [get](../../../csharp/language-reference/keywords/get.md) recupera los valores de los miembros de datos.  
  
 Este ejemplo muestra una clase `Person` con dos propiedades: `Name` \(cadena\) y `Age` \(entero\).  Ambas propiedades proporcionan descriptores de acceso `get` y `set`, por lo que se consideran propiedades de lectura y escritura.  
  
## Ejemplo  
 [!code-cs[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_1.cs)]  
  
## Programación eficaz  
 En el ejemplo anterior, las propiedades `Name` y `Age` son [public](../../../csharp/language-reference/keywords/public.md) e incluyen un descriptor de acceso `get` y `set`.  Esto permite que cualquier objeto lea y escriba estas propiedades.  Sin embargo, a veces es conveniente excluir uno de los descriptores de acceso.  Por ejemplo, al omitir el descriptor de acceso `set`, la propiedad pasa a ser de sólo lectura:  
  
 [!code-cs[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_2.cs)]  
  
 Opcionalmente, se puede exponer públicamente un descriptor de acceso pero definir el otro como private o protected.  Para obtener más información, vea [Accesibilidad del descriptor de acceso asimétrico \(Guía de programación de C\#\)](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).  
  
 Una vez declaradas las propiedades, se pueden utilizar como si fueran campos de la clase.  Esto permite una sintaxis muy natural, tanto para obtener como para establecer el valor de una propiedad, como se muestra en las siguientes instrucciones:  
  
 [!code-cs[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_3.cs)]  
  
 Observe que, en un método `set` de una propiedad, se dispone de una variable especial `value`.  Esta variable contiene el valor especificado por el usuario, por ejemplo:  
  
 [!code-cs[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_4.cs)]  
  
 Observe la sintaxis tan simple que se utiliza para incrementar la propiedad `Age` de un objeto `Person`:  
  
 [!code-cs[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_5.cs)]  
  
 Si se utilizaron métodos `set` y `get` independientes para modelar las propiedades, el código equivalente tendría el siguiente aspecto:  
  
```  
person.SetAge(person.GetAge() + 1);   
```  
  
 En el siguiente ejemplo, el método `ToString` se reemplaza:  
  
 [!code-cs[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_6.cs)]  
  
 Observe que `ToString` no se utiliza explícitamente en el programa.  Se invoca de forma predeterminada mediante las llamadas `WriteLine`.  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)