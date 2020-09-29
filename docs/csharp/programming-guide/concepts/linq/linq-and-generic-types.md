---
title: LINQ y tipos genéricos (C#)
description: Obtenga información sobre los conceptos básicos de los tipos genéricos de C# que admiten consultas.  Las consultas LINQ se basan en tipos genéricos.
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], generic types
- generic types [LINQ]
- generics [LINQ]
ms.assetid: 660e3799-25ca-462c-8c4a-8bce04fbb031
ms.openlocfilehash: a71957eabea788fb06195df1ef026390947f013d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170472"
---
# <a name="linq-and-generic-types-c"></a>LINQ y tipos genéricos (C#)

Las consultas LINQ se basan en tipos genéricos incorporados en la versión 2.0 de .NET Framework. No es necesario tener conocimientos avanzados de genéricos para poder empezar a escribir consultas, aunque debería entender dos conceptos básicos:  
  
1. Al crear una instancia de una clase de colección genérica como <xref:System.Collections.Generic.List%601>, reemplace la "T" por el tipo de objetos que contendrá la lista. Por ejemplo, una lista de cadenas se expresa como `List<string>` y una lista de objetos `Customer` se expresa como `List<Customer>`. Las listas genéricas están fuertemente tipadas y ofrecen muchas ventajas respecto a las colecciones que almacenan sus elementos como <xref:System.Object>. Si intenta agregar un `Customer` a una `List<string>`, se producirá un error en tiempo de compilación. Usar colecciones genéricas es fácil porque no es necesario efectuar ninguna conversión de tipos en tiempo de ejecución.  
  
2. <xref:System.Collections.Generic.IEnumerable%601> es la interfaz que permite enumerar las clases de colección genéricas mediante la instrucción `foreach`. Las clases de colección genéricas admiten <xref:System.Collections.Generic.IEnumerable%601> simplemente como clases de colección no genéricas como <xref:System.Collections.ArrayList> admite <xref:System.Collections.IEnumerable>.  
  
 Para obtener más información sobre los genéricos, vea [Genéricos](../../generics/index.md).  
  
## <a name="ienumerablet-variables-in-linq-queries"></a>Variables IEnumerable<T\> en las consultas LINQ  

 Las variables de consulta LINQ tienen el tipo <xref:System.Collections.Generic.IEnumerable%601> o un tipo derivado como <xref:System.Linq.IQueryable%601>. Cuando vea una variable de consulta que tiene el tipo `IEnumerable<Customer>`, significa que, al ejecutarse, la consulta generará una secuencia de cero o más objetos `Customer`.  
  
 [!code-csharp[csLINQGettingStarted#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#34)]  
  
 Para obtener más información, vea [Relaciones entre tipos en operaciones de consulta LINQ](./type-relationships-in-linq-query-operations.md).  
  
## <a name="letting-the-compiler-handle-generic-type-declarations"></a>Permitir que el compilador controle las declaraciones de tipo genérico  

 Si lo prefiere, puede evitar la sintaxis genérica mediante la palabra clave [var](../../../language-reference/keywords/var.md). La palabra clave `var` indica al compilador que infiera el tipo de una variable de consulta examinando el origen de datos especificado en la cláusula `from`. En el ejemplo siguiente se genera el mismo código compilado que en el ejemplo anterior:  
  
 [!code-csharp[csLINQGettingStarted#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#35)]  
  
 La palabra clave `var` es útil cuando el tipo de la variable es obvio o cuando no es tan importante especificar explícitamente los tipos genéricos anidados, como los que generan las consultas de grupo. Le recordamos que, si usa `var`, debe tener presente que puede dificultar la lectura del código a otros usuarios. Para más información, vea [Variables locales con asignación implícita de tipos](../../classes-and-structs/implicitly-typed-local-variables.md).  
  
## <a name="see-also"></a>Vea también

- [Genéricos](../../generics/index.md)
