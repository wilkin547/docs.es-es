---
title: "Type Relationships in LINQ Query Operations (C#) | Microsoft Docs"
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
  - "inferring type information [LINQ in C#]"
  - "data sources [LINQ in C#], type relationships"
  - "queries [LINQ in C#], type relationships"
  - "relationships [LINQ in C#]"
  - "type relationships [LINQ in C#]"
  - "variable relationships [LINQ in C#]"
  - "type information inferred [LINQ in C#]"
  - "data transformations [LINQ in C#]"
  - "LINQ [C#], type relationships"
ms.assetid: 99118938-d47c-4d7e-bb22-2657a9f95268
caps.latest.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# Type Relationships in LINQ Query Operations (C#)
Para escribir las consultas eficazmente, es necesario comprender cómo se relacionan entre sí los tipos de las variables en una operación de consulta completa.  Si entiende estas relaciones comprenderá más fácilmente los ejemplos de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] y los ejemplos de código de la documentación.  Además, entenderá lo que sucede en segundo plano cuando los tipos de las variables se declaran implícitamente mediante `var`.  
  
 Las operaciones de consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] están fuertemente tipadas en el origen de datos, en la propia consulta y en la ejecución de la consulta.  El tipo de las variables de la consulta debe ser compatible con el tipo de los elementos del origen de datos y con el tipo de la variable de iteración de la instrucción `foreach`.  Este tipado fuerte garantiza que los errores de tipos se detectan en tiempo de compilación, cuando aún se pueden corregir, antes de que los usuarios los detecten.  
  
 Para mostrar estas relaciones de tipos, en la mayoría de los ejemplos siguientes se utilizan tipos explícitos para todas las variables.  En el último ejemplo se muestra cómo se aplican los mismos principios incluso al utilizar tipos implícitos mediante [var](../../../../csharp/language-reference/keywords/var.md).  
  
## Consultas que no transforman los datos de origen  
 La ilustración siguiente muestra una operación de consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] to Objects que no realiza ninguna transformación de los datos.  El origen contiene una secuencia de cadenas y el resultado de la consulta también es una secuencia de cadenas.  
  
 ![Relación de tipos de datos en una consulta LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq-flow1.png "LINQ\_flow1")  
  
1.  El argumento de tipo del origen de datos determina el tipo de la variable de rango.  
  
2.  El tipo del objeto que está seleccionado determina el tipo de la variable de consulta.  Aquí, `name` es una cadena.  Por lo tanto, la variable de consulta es `IEnumerable`\<string\>.  
  
3.  La variable de consulta se procesa en iteración en la instrucción `foreach`.  Dado que la variable de consulta es una secuencia de cadenas, la variable de iteración también es una cadena.  
  
## Consultas que transforman los datos de origen  
 La ilustración siguiente muestra una operación de consulta [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)] que realiza una transformación simple de los datos.  La consulta utiliza una secuencia de objetos `Customer` como entrada y selecciona sólo la propiedad `Name` en el resultado.  Dado que `Name` es una cadena, la consulta genera una secuencia de cadenas como resultado.  
  
 ![Consulta que transforma el tipo de datos](../../../../csharp/programming-guide/concepts/linq/media/linq-flow2.png "LINQ\_flow2")  
  
1.  El argumento de tipo del origen de datos determina el tipo de la variable de rango.  
  
2.  La instrucción `select` devuelve la propiedad `Name` en lugar del objeto `Customer` completo.  Dado que `Name` es una cadena, el argumento de tipo de `custNameQuery` es `string`, no `Customer`.  
  
3.  Dado que `custNameQuery` es una secuencia de cadenas, la variable de iteración del bucle `foreach` también debe ser `string`.  
  
 La ilustración siguiente muestra una transformación un poco más compleja.  La instrucción `select` devuelve un tipo anónimo que captura sólo dos miembros del objeto `Customer` original.  
  
 ![Consulta que transforma el tipo de datos](../../../../csharp/programming-guide/concepts/linq/media/linq-flow3.png "LINQ\_flow3")  
  
1.  El argumento de tipo del origen de datos siempre es el tipo de la variable de rango de la consulta.  
  
2.  Dado que la instrucción `select` genera un tipo anónimo, el tipo de la variable de consulta debe declararse implícitamente mediante `var`.  
  
3.  Dado que el tipo de la variable de consulta es implícito, la variable de iteración del bucle `foreach` también debe ser implícita.  
  
## Permitir que el compilador deduzca la información de tipo  
 Aunque debería comprender las relaciones de los tipos en una operación de consulta, tiene la opción de que el compilador haga todo el trabajo por usted.  La palabra clave [var](../../../../csharp/language-reference/keywords/var.md) se puede utilizar para cualquier variable local en una operación de consulta.  La ilustración siguiente es similar al ejemplo número 2 antes analizado.  Sin embargo, el compilador suministra el tipo seguro para cada variable de la operación de consulta.  
  
 ![Flujo de tipos con asignación implícita de tipos](../../../../csharp/programming-guide/concepts/linq/media/linq-flow4.png "LINQ\_flow4")  
  
 Para obtener más información sobre `var`, vea [Variables locales con asignación implícita de tipos](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## Vea también  
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Type Relationships in Query Operations \(Visual Basic\)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)