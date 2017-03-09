---
title: "Restricciones de tipos de par&#225;metros (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "genéricos [C#], restricciones de tipo"
  - "restricciones de tipo [C#]"
  - "parámetros de tipo [C#], restricciones"
  - "parámetro de tipo sin enlazar [C#]"
ms.assetid: 141b003e-1ddb-4e1c-bcb2-e1c3870e6a51
caps.latest.revision: 41
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 41
---
# Restricciones de tipos de par&#225;metros (Gu&#237;a de programaci&#243;n de C#)
Cuando se define una clase genérica, se pueden aplicar restricciones a las clases de tipos que el código de cliente puede usar para argumentos de tipo cuando crea una instancia de la clase.  Si el código de cliente intenta crear una instancia de la clase con un tipo que no está permitido por una restricción, el resultado es un error de compilación.  Estas limitaciones se llaman restricciones.  Las restricciones se especifican mediante la palabra clave contextual `where`.  En la siguiente tabla se muestran los seis tipos de restricción:  
  
|Restricción|Descripción|  
|-----------------|-----------------|  
|where T: struct|El argumento de tipo debe ser un tipo de valor.  Se puede especificar cualquier tipo de valor excepto <xref:System.Nullable>.  Para obtener más información, consulte [Utilizar tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/using-nullable-types.md).|  
|where T : class|El argumento de tipo debe ser un tipo de referencia; esto se aplica también a cualquier tipo de clase, interfaz, delegado o matriz.|  
|where T : new\(\)|El argumento de tipo debe tener un constructor público sin parámetros.  Cuando se utiliza la restricción `new()` con otras restricciones, debe especificarse en último lugar.|  
|where T : \<nombre de clase base\>|El argumento de tipo debe ser la clase base especificada, o bien debe derivarse de la misma.|  
|where T: \<nombre de interfaz\>|El argumento de tipo debe ser o implementar la interfaz especificada.  Se pueden especificar varias restricciones de interfaz.  La interfaz con restricciones también puede ser genérica.|  
|where T : U|El argumento de tipo proporcionado para T debe ser o derivar del argumento proporcionado para U.|  
  
## Por qué utilizar restricciones  
 Si desea examinar un elemento en una lista genérica para determinar si es válido o compararlo con otro elemento, el compilador debe tener alguna garantía de que el operador o método que tiene que llamar será compatible con cualquier argumento de tipo que el código de cliente pudiera especificar.  Esta garantía se obtiene al aplicar una o más restricciones a la definición de clase genérica.  Por ejemplo, la restricción de clase base le indica al compilador que sólo los objetos de este tipo o derivados de éste se usarán como argumentos de tipo.  Una vez que el compilador tiene esta garantía, puede permitir que se llame a los métodos de ese tipo en la clase genérica.  Las restricciones se aplican mediante la palabra clave contextual `where`.  En el siguiente ejemplo de código se muestra la funcionalidad que se puede agregar a la clase `GenericList<T>` \(en [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)\) mediante la aplicación de una restricción de clase base.  
  
 [!code-cs[csProgGuideGenerics#11](../../../csharp/programming-guide/generics/codesnippet/csharp/constraints-on-type-para_1.cs)]  
  
 La restricción permite a la clase genérica utilizar la propiedad `Employee.Name`, ya que está garantizado que todos los elementos de tipo T son un objeto `Employee` o un objeto que se hereda de `Employee`.  
  
 Se pueden aplicar varias restricciones al mismo parámetro de tipo y las propias restricciones pueden ser tipos genéricos, como se ve a continuación:  
  
 [!code-cs[csProgGuideGenerics#12](../../../csharp/programming-guide/generics/codesnippet/csharp/constraints-on-type-para_2.cs)]  
  
 Al restringir el parámetro de tipo, se aumenta el número de operaciones permitidas y el método llama a aquellas admitidas por el tipo de restricción y todos los tipos de su jerarquía de herencia.  Por lo tanto, al diseñar clases o métodos genéricos, si se va a realizar cualquier operación en los miembros genéricos más allá de una simple asignación o se va a llamar a cualquier método que no está admitido por `System.Object`, será necesario aplicar restricciones al parámetro de tipo.  
  
 Al aplicar la restricción `where T : class`, evite utilizar los operadores `!=` y `==` en el parámetro de tipo porque estos operadores sólo comprobarán la identidad de la referencia, pero no la igualdad de valores.  Esto es aplicable aunque estos operadores se sobrecarguen en un tipo que se utiliza como argumento.  El código siguiente ilustra este punto; el resultado es false aunque la clase <xref:System.String> sobrecargue el operador `==`.  
  
 [!code-cs[csProgGuideGenerics#13](../../../csharp/programming-guide/generics/codesnippet/csharp/constraints-on-type-para_3.cs)]  
  
 La razón de este comportamiento es que, en tiempo de compilación, el compilador sabe que T es un tipo de referencia y que, por lo tanto, debe usar los operadores predeterminados que son válidos para todos los tipos de referencia.  Si necesita probar la igualdad de valores, la forma recomendada es aplicar también la restricción `where T : IComparable<T>` e implementar esa interfaz en cualquier clase que se vaya a utilizar para construir la clase genérica.  
  
## Restringir varios parámetros  
 Pueden aplicar restricciones a varios parámetros, así como varias restricciones a un solo parámetro, como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideGenerics#64](../../../csharp/programming-guide/generics/codesnippet/csharp/constraints-on-type-para_4.cs)]  
  
## Parámetros de tipo sin delimitar  
 Los parámetros de tipo que no tienen restricciones, como T en la clase pública `SampleClass<T>{}`, se denominan parámetros de tipo sin delimitar.  Los parámetros de tipo sin delimitar tienen las siguientes reglas:  
  
-   No se pueden utilizar los operadores `!=` ni `==`, porque no existe ninguna garantía de que el argumento de tipo concreto admitirá estos operadores.  
  
-   Pueden convertirse a o desde `System.Object`, o bien convertirse explícitamente en cualquier tipo de interfaz.  
  
-   Se pueden comparar con [null](../../../csharp/language-reference/keywords/null.md).  Si un parámetro sin delimitar se compara con `null`, la comparación siempre devolverá false si el argumento de tipo es un tipo de valor.  
  
## Parámetros de tipo como restricciones  
 El uso de un parámetro de tipo genérico como restricción es útil cuando una función de miembro con su propio parámetro de tipo tiene que restringir ese parámetro al parámetro del tipo que lo contiene, como se muestra en el siguiente ejemplo:  
  
 [!code-cs[csProgGuideGenerics#14](../../../csharp/programming-guide/generics/codesnippet/csharp/constraints-on-type-para_5.cs)]  
  
 En el ejemplo anterior, `T` es una restricción de tipo en el contexto del método `Add` y un parámetro de tipo sin delimitar en el contexto de la clase `List`.  
  
 Los parámetros de tipo también se pueden usar como restricciones en las definiciones de clases genéricas.  Tenga en cuenta que el parámetro de tipo debe declararse dentro de los corchetes angulares junto con cualquier otro parámetro de tipo:  
  
 [!code-cs[csProgGuideGenerics#15](../../../csharp/programming-guide/generics/codesnippet/csharp/constraints-on-type-para_6.cs)]  
  
 La utilidad de los parámetros de tipo como restricciones con clases genéricas es muy limitada, porque el compilador no puede suponer nada acerca del parámetro de tipo excepto que se deriva de `System.Object`.  Utilice los parámetros de tipo como restricciones en clases genéricas en escenarios en los que desee exigir una relación de herencia entre dos parámetros de tipo.  
  
## Vea también  
 <xref:System.Collections.Generic>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Clases genéricas](../../../csharp/programming-guide/generics/generic-classes.md)   
 [Restricción new](../../../csharp/language-reference/keywords/new-constraint.md)