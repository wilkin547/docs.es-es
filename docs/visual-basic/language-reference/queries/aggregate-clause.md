---
title: "Aggregate (Cl&#225;usula, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryAggregateIn"
  - "vb.QueryAggregate"
  - "vb.QueryAggregateInto"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Aggregate (cláusula)"
  - "Aggregate (instrucción)"
  - "consultas [Visual Basic], Agregar"
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# Aggregate (Cl&#225;usula, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Aplica una o más funciones de agregado a una colección.  
  
## Sintaxis  
  
```  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`element`|Obligatorio.  Variable usada para recorrer en iteración los elementos de la colección.|  
|`type`|Opcional.  Tipo de `element`.  Si no se especifica ningún tipo, el tipo de `element` se deduce de `collection`.|  
|`collection`|Obligatorio.  Hace referencia a la colección en la que funciona.|  
|`clause`|Opcional.  Una o más cláusulas de consulta, como una cláusula `Where`, que van a refinar el resultado de la consulta al que se va a aplicar la cláusula o cláusulas agregadas.|  
|`expressionList`|Obligatorio.  Una o más expresiones separadas por coma que identifican una función de agregado que se va a aplicar a la colección.  Puede aplicar un alias a una función de agregado para especificar un nombre de miembro para el resultado de la consulta.  Si no se proporciona ningún alias, se utiliza el nombre de la función de agregado.  Para obtener ejemplos, vea la sección sobre funciones de agregado más adelante en este tema.|  
  
## Comentarios  
 La cláusula `Aggregate` se puede utilizar para incluir las funciones de agregado en las consultas.  Las funciones de agregado realizan comprobaciones y cálculos sobre un conjunto de valores y devuelven un valor único.  Puede tener acceso al valor calculado utilizando un miembro del tipo del resultado de la consulta.  Las funciones de agregado estándar que puede usar son las funciones `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min` y `Sum`.  Los programadores que están familiarizados con agregados en SQL, también están familiarizados con estas funciones.  Se describen en la sección siguiente de este tema.  
  
 El resultado de una función de agregado se incluye en el resultado de la consulta como campo del tipo del resultado de la consulta.  Puede proporcionar un alias para que el resultado de la función de agregado especifique el nombre del miembro del tipo del resultado de la consulta que contendrá el valor agregado.  Si no se proporciona ningún alias, se utiliza el nombre de la función de agregado.  
  
 La cláusula `Aggregate` puede iniciar una consulta o se puede incluir como cláusula adicional de una consulta.  Si la cláusula `Aggregate` inicia una consulta, el resultado es un solo valor que es el resultado de la función de agregado especificada en la cláusula `Into`.  Si más de una función de agregado se especifica en la cláusula `Into`, la consulta devuelve un tipo único con una propiedad independiente para hacer referencia al resultado de cada función de agregado de la cláusula `Into`.  Si la cláusula `Aggregate` se incluye como cláusula adicional en una consulta, el tipo devuelto en la colección de consultas tendrá una propiedad independiente para hacer referencia al resultado de cada función de agregado de la cláusula `Into`.  
  
## Funciones de agregado  
 La lista siguiente describe las funciones de agregado estándar que se pueden utilizar con la cláusula `Aggregate`.  
  
|||  
|-|-|  
|Función|Descripción|  
|`All`|Devuelve `true` si todos los elementos de la colección cumplen una condición especificada; de lo contrario, devuelve `false`.  A continuación, se muestra un ejemplo:<br /><br /> [!code-vb[VbSimpleQuerySamples#5](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#5)]|  
|`Any`|Devuelve `true` si cualquier elemento de la colección cumplen una condición especificada; de lo contrario, devuelve `false`.  A continuación, se muestra un ejemplo:<br /><br /> [!code-vb[VbSimpleQuerySamples#6](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#6)]|  
|`Average`|Calcula la media de todos los elementos de la colección o calcula la expresión proporcionada para todos los elementos en la colección.  A continuación, se muestra un ejemplo:<br /><br /> [!code-vb[VbSimpleQuerySamples#7](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#7)]|  
|`Count`|Cuenta el número de elementos de la colección.  Puede proporcionar una expresión `Boolean` opcional para contar sólo el número de elementos de la colección que cumplen una condición.  A continuación, se muestra un ejemplo:<br /><br /> [!code-vb[VbSimpleQuerySamples#8](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#8)]|  
|`Group`|Hace referencia a los resultados de la consulta agrupados como resultado de una cláusula `Group By` o `Group Join` La función `Group` sólo es válida en la cláusula `Into` de `Group By` o la cláusula `Group Join` Para obtener más información y ejemplos, vea [Group By \(Cláusula\)](../../../visual-basic/language-reference/queries/group-by-clause.md) y [Group Join \(Cláusula\)](../../../visual-basic/language-reference/queries/group-join-clause.md).|  
|`LongCount`|Cuenta el número de elementos de la colección.  Puede proporcionar una expresión `Boolean` opcional para contar sólo el número de elementos de la colección que cumplen una condición.  Devuelve el resultado como valor de tipo `Long`.  Para obtener un ejemplo, vea la función de agregado `Count`.|  
|`Max`|Calcula el valor máximo de la colección o una expresión proporcionada para todos los elementos de la colección.  A continuación, se muestra un ejemplo:<br /><br /> [!code-vb[VbSimpleQuerySamples#9](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#9)]|  
|`Min`|Calcula el valor mínimo de la colección o una expresión proporcionada para todos los elementos de la colección.  A continuación, se muestra un ejemplo:<br /><br /> [!code-vb[VbSimpleQuerySamples#10](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#10)]|  
|`Sum`|Calcula la suma de todos los elementos de la colección o la expresión proporcionada para todos los elementos en la colección.  A continuación, se muestra un ejemplo:<br /><br /> [!code-vb[VbSimpleQuerySamples#15](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#15)]|  
  
## Ejemplo  
 El ejemplo de código siguiente muestra cómo utilizar la cláusula `Aggregate` para aplicar funciones de agregado al resultado de una consulta.  
  
 [!code-vb[VbSimpleQuerySamples#4](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#4)]  
  
## Crear funciones de agregado definidas por el usuario  
 Puede incluir sus propias funciones de agregado personalizadas en una expresión de consulta agregando métodos de extensión al tipo <xref:System.Collections.Generic.IEnumerable%601>.  Después, el método personalizado puede realizar un cálculo u operación en la colección enumerable que ha hecho referencia a la función de agregado.  Para obtener más información acerca de los métodos de extensión, vea [métodos de extensión.](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
 El ejemplo de código siguiente muestra una función de agregado personalizada que calcula el valor medio de una colección de números, por ejemplo.  Hay dos sobrecargas del método de extensión `Median`.  La primera sobrecarga acepta, como entrada, una colección de tipo `IEnumerable(Of Double)`.  Si se llama a la función de agregado `Median` para un campo de consulta de tipo `Double`, se llamará a este método.  La segunda sobrecarga del método `Median` puede pasar cualquier tipo genérico.  La sobrecarga genérica del método `Median` toma un segundo parámetro que hace referencia a la expresión lambda `Func(Of T, Double)` para proyectar un valor para un tipo \(de una colección\) como el valor correspondiente de tipo `Double`.  Después delega el cálculo del valor medio en la otra sobrecarga del método `Median`.  Para obtener más información sobre las expresiones lambda, vea [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbSimpleQuerySamples#18](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/UserDefinedAggregates.vb#18)]  
  
 El ejemplo de código siguiente muestra consultas del ejemplo que llaman a la función de agregado `Median` en una colección de tipo `Integer` y una colección de tipo `Double`.  La consulta que llama a la función de agregado `Median` en la colección de tipo `Double` llama a la sobrecarga del método `Median` que acepta, como entrada, una colección de tipo `Double`.  La consulta que llama a la función de agregado `Median` en la colección de tipo `Integer` llama a la sobrecarga genérica del método `Median`.  
  
 [!code-vb[VbSimpleQuerySamples#19](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/UserDefinedAggregates.vb#19)]  
  
## Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)   
 [Select \(Cláusula\)](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From \(Cláusula\)](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Where \(Cláusula\)](../../../visual-basic/language-reference/queries/where-clause.md)   
 [Group By \(Cláusula\)](../../../visual-basic/language-reference/queries/group-by-clause.md)