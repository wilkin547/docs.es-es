---
title: LINQ y tipos genéricos (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], generic types
- generic types [LINQ]
- generics [LINQ]
ms.assetid: 660e3799-25ca-462c-8c4a-8bce04fbb031
ms.openlocfilehash: f9bb4ec21685d21d0975529c7460944b5f0f9fc6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="linq-and-generic-types-c"></a>LINQ y tipos genéricos (C#)
Las consultas [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] se basan en tipos genéricos, introducidos en la versión 2.0 de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. No es necesario tener conocimientos avanzados de genéricos para poder empezar a escribir consultas, aunque debería entender dos conceptos básicos:  
  
1.  Al crear una instancia de una clase de colección genérica como <xref:System.Collections.Generic.List%601>, reemplace la "T" por el tipo de objetos que contendrá la lista. Por ejemplo, una lista de cadenas se expresa como `List<string>` y una lista de objetos `Customer` se expresa como `List<Customer>`. Las listas genéricas están fuertemente tipadas y ofrecen muchas ventajas respecto a las colecciones que almacenan sus elementos como <xref:System.Object>. Si intenta agregar un `Customer` a una `List<string>`, se producirá un error en tiempo de compilación. Usar colecciones genéricas es fácil porque no es necesario efectuar ninguna conversión de tipos en tiempo de ejecución.  
  
2.  <xref:System.Collections.Generic.IEnumerable%601> es la interfaz que permite enumerar las clases de colección genéricas mediante la instrucción `foreach`. Las clases de colección genéricas admiten <xref:System.Collections.Generic.IEnumerable%601> simplemente como clases de colección no genéricas como <xref:System.Collections.ArrayList> admite <xref:System.Collections.IEnumerable>.  
  
 Para obtener más información sobre los genéricos, vea [Genéricos](../../../../csharp/programming-guide/generics/index.md).  
  
## <a name="ienumerablet-variables-in-linq-queries"></a>Variables IEnumerable<T\> en las consultas LINQ  
 Las variables de consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] tienen el tipo <xref:System.Collections.Generic.IEnumerable%601> o un tipo derivado como <xref:System.Linq.IQueryable%601>. Cuando vea una variable de consulta que tiene el tipo `IEnumerable<Customer>`, significa que, al ejecutarse, la consulta generará una secuencia de cero o más objetos `Customer`.  
  
 [!code-csharp[csLINQGettingStarted#34](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_1.cs)]  
  
 Para obtener más información, vea [Type Relationships in LINQ Query Operations](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md) (Relaciones entre tipos en las operaciones de consulta LINQ).  
  
## <a name="letting-the-compiler-handle-generic-type-declarations"></a>Permitir que el compilador controle las declaraciones de tipo genérico  
 Si lo prefiere, puede evitar la sintaxis genérica mediante la palabra clave [var](../../../../csharp/language-reference/keywords/var.md). La palabra clave `var` indica al compilador que infiera el tipo de una variable de consulta examinando el origen de datos especificado en la cláusula `from`. En el ejemplo siguiente se genera el mismo código compilado que en el ejemplo anterior:  
  
 [!code-csharp[csLINQGettingStarted#35](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_2.cs)]  
  
 La palabra clave `var` es útil cuando el tipo de la variable es obvio o cuando no es tan importante especificar explícitamente los tipos genéricos anidados, como los que generan las consultas de grupo. Le recordamos que, si usa `var`, debe tener presente que puede dificultar la lectura del código a otros usuarios. Para obtener más información, vea [Variables locales con asignación implícita de tipos](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Genéricos](../../../../csharp/programming-guide/generics/index.md)
