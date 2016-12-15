---
title: "join (Cl&#225;usula, Referencia de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "join"
  - "join_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "join (cláusula) [C#]"
  - "join (palabra clave) [C#]"
ms.assetid: 76e9df84-092c-41a6-9537-c3f1cbd7f0fb
caps.latest.revision: 29
caps.handback.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# join (Cl&#225;usula, Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La cláusula `join` sirve para asociar elementos de secuencias de origen diferentes que no tienen ninguna relación directa en el modelo de objetos.  El único requisito es que los elementos de cada origen compartan algún valor para el que se pueda comparar la igualdad.  Por ejemplo, un distribuidor de comida podría tener una lista de proveedores de cierto producto y una lista de compradores.  Se puede utilizar una cláusula `join`, por ejemplo, para crear una lista de proveedores y compradores de ese producto que se encuentren en la misma región especificada.  
  
 Una cláusula `join` usa dos secuencias de origen como entrada.  Los elementos de cada secuencia deben ser o contener una propiedad que se pueda comparar con una propiedad correspondiente en la otra secuencia.  La cláusula `join` compara la igualdad de las claves especificadas utilizando la palabra clave especial `equals`.  Todas las combinaciones realizadas por la cláusula `join` son combinaciones de igualdad.  La forma del resultado de una cláusula `join` depende del tipo de combinación específico que se está realizando.  A continuación se indican los tres tipos de combinación más comunes:  
  
-   Combinación interna  
  
-   Combinación agrupada  
  
-   Combinación externa izquierda  
  
## Combinación interna  
 En el ejemplo siguiente se muestra una combinación de igualdad interna simple.  Esta consulta genera una secuencia simple de pares de "nombre de producto \/ categoría".  La misma cadena de categoría aparecerá en varios elementos.  Si un elemento de `categories` no tiene ninguna correspondencia en `products`, esa categoría no aparecerá en los resultados.  
  
 [!code-cs[cscsrefQueryKeywords#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_1.cs)]  
  
 Para obtener más información, vea [Cómo: Realizar combinaciones internas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md).  
  
## Group Join  
 Una cláusula `join` con una expresión `into` se denomina unión agrupada.  
  
 [!code-cs[cscsrefQueryKeywords#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_2.cs)]  
  
 Una unión agrupada genera una secuencia de resultados jerárquica, que asocia los elementos de la secuencia de origen izquierda a uno o más elementos coincidentes de la secuencia de origen derecha.  Una unión agrupada no tiene equivalente en términos relacionales; es esencialmente una secuencia de matrices de objetos.  
  
 Si no se encuentran elementos en la secuencia de origen derecha que coincidan con un elemento del origen izquierdo, la cláusula `join` genera una matriz vacía para ese elemento.  Por consiguiente, la combinación agrupada básicamente sigue siendo una combinación de igualdad interna, con la diferencia de que la secuencia resultante se organiza en grupos.  
  
 Si simplemente selecciona los resultados de una combinación agrupada, puede tener acceso a los elementos, pero no puede identificar la clave según la cual coinciden.  Por lo tanto, generalmente es más útil seleccionar los resultados de la combinación agrupada en un nuevo tipo que también incluya el nombre de la clave, como se mostraba en el ejemplo anterior.  
  
 Por supuesto que también se puede usar el resultado de una combinación agrupada como generador de otra subconsulta:  
  
 [!code-cs[cscsrefQueryKeywords#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_3.cs)]  
  
 Para obtener más información, vea [Cómo: Realizar combinaciones agrupadas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md).  
  
## Combinación externa izquierda  
 En una combinación externa izquierda, se devuelven todos los elementos de la secuencia de origen izquierda, aun cuando no haya elementos correspondientes en la secuencia derecha.  Para realizar una combinación externa izquierda en [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)], utilice el método `DefaultIfEmpty` junto con una combinación agrupada para especificar el elemento derecho predeterminado que se generará si un elemento izquierdo no tiene coincidencias.  Puede utilizar `null` como valor predeterminado para cualquier tipo de referencia o puede especificar un tipo predeterminado definido por el usuario.  En el ejemplo siguiente se muestra un tipo predeterminado definido por el usuario:  
  
 [!code-cs[cscsrefQueryKeywords#27](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_4.cs)]  
  
 Para obtener más información, vea [Cómo: Realizar operaciones de combinación externa izquierda](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md).  
  
## Operador de igualdad  
 Una cláusula `join` realiza una combinación de igualdad.  En otras palabras, las coincidencias sólo se pueden basar en la igualdad de dos claves.  No se admiten otros tipos de comparaciones, como "mayor que" o "distinto de".  Para que quede claro que todas las combinaciones son combinaciones de igualdad, la cláusula `join` utiliza la palabra clave `equals` en lugar del operador `==`.  La palabra clave `equals` sólo se puede utilizar en una cláusula `join` y difiere del operador `==` en un aspecto importante.  Con `equals`, la clave izquierda utiliza la secuencia de origen externa y la clave derecha utiliza el origen interno.  El origen externo sólo está en ámbito en el lado izquierdo de `equals` y la secuencia de origen interna sólo está en ámbito en el lado derecho.  
  
## Combinaciones de desigualdad  
 Puede realizar combinaciones de desigualdad, combinaciones cruzadas y otras operaciones de combinación personalizadas utilizando varias cláusulas `from` para incluir nuevas secuencias en una consulta de manera independiente.  Para obtener más información, vea [Cómo: Realizar operaciones de combinación personalizadas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md).  
  
## Combinaciones de colecciones de objetos frente atablas relacionales  
 En una expresión de consulta [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)], las operaciones de combinación se realizan en colecciones de objetos.  En realidad, las colecciones de objetos no se pueden "combinar" exactamente de la misma manera que dos tablas relacionales.  En [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)], sólo se requieren cláusulas `join` explícitas cuando dos secuencias de origen no están unidas por ninguna relación.  Al trabajar con [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq_md.md)], las tablas de clave externa se representan en el modelo de objetos como propiedades de la tabla principal.  Por ejemplo, en la base de datos Northwind, la tabla de clientes tiene una relación de clave externa con la tabla de pedidos.  Al asignar las tablas al modelo de objetos, la clase Customer tiene una propiedad Orders que contiene la colección de pedidos asociados a ese cliente.  De hecho, la combinación se ha realizado automáticamente.  
  
 Para obtener más información sobre cómo realizar consultas en tablas relacionadas en el contexto de [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq_md.md)], vea [Cómo: Asignar relaciones de base de datos](../Topic/How%20to:%20Map%20Database%20Relationships.md).  
  
## Claves compuestas  
 Puede comprobar la igualdad de varios valores mediante el uso de una clave compuesta.  Para obtener más información, vea [Cómo: Realizar una unión usando claves compuestas](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md).  Las claves compuestas también se pueden utilizar en una cláusula `group`.  
  
## Ejemplo  
 En el ejemplo siguiente se comparan los resultados de una combinación interna, una combinación agrupada y una combinación externa izquierda en los mismos orígenes de datos, utilizando las mismas claves coincidentes.  En estos ejemplos se ha agregado código adicional para que los resultados se vean más claros en la consola.  
  
 [!code-cs[cscsrefQueryKeywords#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_5.cs)]  
  
## Comentarios  
 Una cláusula `join` que no va seguida de `into` se convierte en una llamada al método <xref:System.Linq.Enumerable.Join%2A>.  Una cláusula `join` que va seguida de `into` se convierte en una llamada al método <xref:System.Linq.Enumerable.GroupJoin%2A>.  
  
## Vea también  
 [Palabras clave para consultas \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [group \(cláusula\)](../../../csharp/language-reference/keywords/group-clause.md)   
 [Cómo: Realizar operaciones de combinación externa izquierda](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)   
 [Cómo: Realizar combinaciones internas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)   
 [Cómo: Realizar combinaciones agrupadas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)   
 [Cómo: Ordenar los resultados de una cláusula join](../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)   
 [Cómo: Realizar una unión usando claves compuestas](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md)   
 [Cómo: Instalar bases de datos de ejemplo](../Topic/How%20to:%20Install%20Sample%20Databases.md)