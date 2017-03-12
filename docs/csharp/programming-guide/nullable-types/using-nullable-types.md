---
title: "Utilizar tipos que aceptan valores NULL (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "tipos que aceptan valores NULL [C#], acerca de los tipos que aceptan valores NULL"
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# Utilizar tipos que aceptan valores NULL (Gu&#237;a de programaci&#243;n de C#)
Los tipos que aceptan valores NULL pueden representar todos los valores de un tipo subyacente y un valor [null](../../../csharp/language-reference/keywords/null.md) adicional.  Los tipos que aceptan valores NULL se declaran de dos formas:  
  
 `System.Nullable<T> variable`  
  
 O bien  
  
 `T?  variable`  
  
 `T` es el tipo subyacente del tipo que acepta valores NULL.  `T` puede ser cualquier tipo de valor incluido `struct`; no puede ser tipo de referencia.  
  
 Para obtener un ejemplo de cuándo se podría utilizar un tipo que acepta valores NULL, piense en una variable booleana común que puede tener dos valores: true y false.  No hay ningún valor que signifique "indefinido".  En muchas aplicaciones de programación, en particular en las interacciones de bases de datos, pueden existir variables con un estado indefinido.  Por ejemplo, un campo de una base de datos puede contener los valores true o false, pero también puede que no contenga ningún valor.  Igualmente, los tipos de referencia se pueden establecer en `null` para indicar que no se inicializan.  
  
 Esta disparidad puede crear trabajo de programación extra, con variables adicionales que se utilizan para almacenar información de estado, el uso de valores especiales, etc.  El modificador de tipos que aceptan valores NULL permite a C\# crear variables de tipo de valor que pueden indicar un valor indefinido.  
  
## Ejemplos de tipos que aceptan valores NULL  
 Cualquier tipo de valor se puede utilizar como base para un tipo que acepta valores NULL.  Por ejemplo:  
  
 [!code-cs[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-nullable-types_1.cs)]  
  
## Miembros de tipos que aceptan valores NULL  
 Cada instancia de un tipo que acepta valores NULL tiene dos propiedades públicas de sólo lectura:  
  
-   `HasValue`  
  
     `HasValue` es de tipo `bool`.  Se establece como `true` cuando la variable contiene un valor que no es null.  
  
-   `Value`  
  
     `Value` es del mismo tipo que el tipo subyacente.  Si `HasValue` es `true`, `Value` contiene un valor significativo.  Si `HasValue` es `false`, al tener acceso a `Value` se producirá una excepción <xref:System.InvalidOperationException>.  
  
 En este ejemplo, el miembro `HasValue` se utiliza para comprobar si la variable contiene un valor antes de mostrarlo.  
  
 [!code-cs[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-nullable-types_2.cs)]  
  
 La comprobación de un valor también puede realizarse tal y como se muestra en el siguiente ejemplo:  
  
 [!code-cs[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-nullable-types_3.cs)]  
  
## Conversiones explícitas  
 Un tipo que acepta valores NULL se puede convertir en un tipo normal mediante el uso explícito de la conversión o a través de la propiedad `Value`.  Por ejemplo:  
  
 [!code-cs[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-nullable-types_4.cs)]  
  
 Si se define una conversión definida por el usuario entre dos tipos de datos, la misma conversión se puede utilizar con las versiones que aceptan valores NULL de estos tipos de datos.  
  
## Conversiones implícitas  
 Una variable de tipo que acepta valores NULL puede establecerse como null con la palabra clave `null`, tal y como se muestra en el siguiente ejemplo:  
  
 [!code-cs[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-nullable-types_5.cs)]  
  
 La conversión de un tipo ordinario a un tipo que acepta valores NULL, es implícita.  
  
 [!code-cs[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-nullable-types_6.cs)]  
  
## Operadores  
 Los operadores predefinidos unarios y binarios así como cualquier operador definido por el usuario que exista para los tipos de valor también pueden ser utilizados por los tipos que aceptan valores NULL.  Estos operadores generan un valor null si los operandos son null; de lo contrario, el operador utiliza el valor contenido para calcular el resultado.  Por ejemplo:  
  
 [!code-cs[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-nullable-types_7.cs)]  
  
 Al realizar comparaciones con tipos que aceptan valores NULL, si el valor de uno de estos tipos es null y el del otro tipo no lo es, todas las comparaciones se evalúan como `false`, salvo para `!=` \(desigualdad\).  Es importante no dar por supuesto que, porque una comparación concreta devuelva `false`, el caso contrario devolverá `true`.  En el ejemplo siguiente, 10 no es mayor, menor ni igual que null.  Solo `num1 != num2` se evalúa como `true`.  
  
 [!code-cs[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-nullable-types_8.cs)]  
  
 Una comparación de igualdad de dos tipos que aceptan valores NULL y que son null se evalúa como `true`.  
  
## El Operador  
 El operador `??` define un valor predeterminado que se devuelve cuando un tipo que acepta valores NULL se asigna a un tipo que no acepta valores NULL.  
  
 [!code-cs[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-nullable-types_9.cs)]  
  
 Este operador también se puede utilizar con muchos tipos que no aceptan valores NULL.  Por ejemplo:  
  
 [!code-cs[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-nullable-types_10.cs)]  
  
## El tipotype  
 El tipo `bool?` que acepta valores NULL, puede contener tres valores diferentes: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) y [null](../../../csharp/language-reference/keywords/null.md).  Para obtener información sobre cómo convertir un tipo bool?  en un tipo booleano, vea [Cómo: Convertir con seguridad de bool? en bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).  
  
 Los tipos booleanos que aceptan valores NULL son como el tipo de variable booleano que se utiliza en SQL.  Para asegurarse de que los resultados generados por los operadores `&` y  `|` sean coherentes con el tipo booleano de tres valores de SQL, se proporcionan los siguientes operadores predefinidos:  
  
 `bool?  operator &(bool?  x, bool?  y)`  
  
 `bool?  operator |(bool?  x, bool?  y)`  
  
 Los resultados de estos operadores se muestran en la siguiente tabla:  
  
|X|y|x&y|x&#124;y|  
|-------|-------|---------|--------------|  
|true|true|true|true|  
|true|false|false|true|  
|true|null|null|true|  
|false|true|false|true|  
|false|false|false|false|  
|false|null|false|null|  
|null|true|null|true|  
|null|false|false|null|  
|null|null|null|null|  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)   
 [Aplicar la conversión boxing a tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)   
 [Tipos de valor que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)