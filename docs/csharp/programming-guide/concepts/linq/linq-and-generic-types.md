---
title: "LINQ and Generic Types (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "LINQ [C#], generic types"
  - "generic types [LINQ]"
  - "generics [LINQ]"
ms.assetid: 660e3799-25ca-462c-8c4a-8bce04fbb031
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# LINQ and Generic Types (C#)
Las consultas [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] se basan en tipos genéricos, que se incluyeron por primera vez en la versión 2.0 de [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)].  No se requieren conocimientos avanzados de los tipos genéricos para poder empezar a escribir consultas.  Sin embargo, quizás necesite conocer dos conceptos básicos:  
  
1.  Al crear una instancia de una clase de colección genérica, como <xref:System.Collections.Generic.List%601>, la "T" se reemplaza con el tipo de objetos que contendrá la lista.  Por ejemplo, una lista de cadenas se expresa como `List<string>` y una lista de objetos `Customer` se expresa como `List<Customer>`.  Una lista genérica está fuertemente tipada y proporciona muchas ventajas frente a las colecciones que almacenan sus elementos como <xref:System.Object>.  Si intenta agregar `Customer` a `List<string>`, obtendrá un error en tiempo de compilación.  Es fácil utilizar las colecciones genéricas, porque no es necesario realizar conversiones de tipos en tiempo de ejecución.  
  
2.  <xref:System.Collections.Generic.IEnumerable%601> es la interfaz que permite enumerar las clases de colección genéricas mediante la instrucción `foreach`.  Las clases de colección genéricas admiten <xref:System.Collections.Generic.IEnumerable%601> de la misma forma que las clases de colección no genéricas, como <xref:System.Collections.ArrayList>, admiten <xref:System.Collections.IEnumerable>.  
  
 Para obtener más información acerca de los tipos genéricos, vea [Genéricos](../../../../csharp/programming-guide/generics/index.md).  
  
## Variables IEnumerable\<T\> en consultas LINQ  
 Las variables de consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] tienen tipos <xref:System.Collections.Generic.IEnumerable%601> o un tipo derivado, como <xref:System.Linq.IQueryable%601>.  Cuando se encuentre una variable de consulta de tipo `IEnumerable<Customer>`, sólo significa que la consulta, cuando se ejecute, generará una secuencia de cero o más objetos `Customer`.  
  
 [!code-cs[csLINQGettingStarted#34](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_1.cs)]  
  
 Para obtener más información, consulte [Type Relationships in LINQ Query Operations](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
## Permitir al compilador administrar las declaraciones de tipos genéricos  
 Si lo prefiere, puede evitar la sintaxis genérica con el uso de la palabra clave [var](../../../../csharp/language-reference/keywords/var.md).  La palabra clave `var` indica al compilador que deduzca el tipo de una variable de consulta examinando el origen de datos especificado en la cláusula `from`.  En el ejemplo siguiente se genera el mismo código compilado que en el ejemplo anterior:  
  
 [!code-cs[csLINQGettingStarted#35](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_2.cs)]  
  
 La palabra clave `var` es útil cuando el tipo de la variable es obvio o cuando no es tan importante especificar explícitamente los tipos genéricos anidados, como los que se generan en las consultas de grupo.  Por lo general, si utiliza `var`, debe saber que puede dificultar la legibilidad del código para los demás.  Para obtener más información, consulte [Variables locales con asignación implícita de tipos](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## Vea también  
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Genéricos](../../../../csharp/programming-guide/generics/index.md)