---
title: Relaciones entre tipos en operaciones de consulta LINQ (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- inferring type information [LINQ in C#]
- data sources [LINQ in C#], type relationships
- queries [LINQ in C#], type relationships
- relationships [LINQ in C#]
- type relationships [LINQ in C#]
- variable relationships [LINQ in C#]
- type information inferred [LINQ in C#]
- data transformations [LINQ in C#]
- LINQ [C#], type relationships
ms.assetid: 99118938-d47c-4d7e-bb22-2657a9f95268
ms.openlocfilehash: 154501d666b467c94f5d1dd721f1e2303189c908
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484829"
---
# <a name="type-relationships-in-linq-query-operations-c"></a>Relaciones entre tipos en operaciones de consulta LINQ (C#)
Para escribir las consultas eficazmente, es necesario comprender cómo los tipos de las variables en una operación de consulta completa se relacionan entre sí. Si entiende estas relaciones comprenderá más fácilmente los ejemplos de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] y los ejemplos de código de la documentación. Además, entenderá lo que sucede en segundo plano cuando los tipos de las variables se declaran implícitamente mediante `var`.  
  
 Las operaciones de consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] tienen un establecimiento inflexible de tipos en el origen de datos, en la propia consulta y en la ejecución de la consulta. El tipo de las variables de la consulta debe ser compatible con el tipo de los elementos del origen de datos y con el tipo de la variable de iteración de la instrucción `foreach`. Este establecimiento inflexible de tipos garantiza que los errores de tipos se detectan en tiempo de compilación, cuando aún se pueden corregir antes de que los usuarios los detecten.  
  
 Para mostrar estas relaciones de tipos, en la mayoría de los ejemplos siguientes se usan tipos explícitos para todas las variables. En el último ejemplo se muestra cómo se aplican los mismos principios incluso al usar tipos implícitos mediante [var](../../../../csharp/language-reference/keywords/var.md).  
  
## <a name="queries-that-do-not-transform-the-source-data"></a>Consultas que no transforman los datos de origen  
 La ilustración siguiente muestra una operación de consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to Objects que no realiza ninguna transformación de los datos. El origen contiene una secuencia de cadenas y el resultado de la consulta también es una secuencia de cadenas.  
  
 ![Relación de tipos de datos en una consulta LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_flow1.png "LINQ_flow1")  
  
1.  El argumento de tipo del origen de datos determina el tipo de la variable de rango.  
  
2.  El tipo del objeto que está seleccionado determina el tipo de la variable de consulta. Aquí, `name` es una cadena. Por tanto, la variable de consulta es `IEnumerable<string>`.  
  
3.  La variable de consulta se procesa en iteración en la instrucción `foreach`. Dado que la variable de consulta es una secuencia de cadenas, la variable de iteración también es una cadena.  
  
## <a name="queries-that-transform-the-source-data"></a>Consultas que transforman los datos de origen  
 En la ilustración siguiente se muestra una operación de consulta [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] que realiza una transformación simple de los datos. La consulta usa una secuencia de objetos `Customer` como entrada y selecciona solo la propiedad `Name` en el resultado. Dado que `Name` es una cadena, la consulta genera una secuencia de cadenas como resultado.  
  
 ![Una consulta que transforma el tipo de datos](../../../../csharp/programming-guide/concepts/linq/media/linq_flow2.png "LINQ_flow2")  
  
1.  El argumento de tipo del origen de datos determina el tipo de la variable de rango.  
  
2.  La instrucción `select` devuelve la propiedad `Name` en lugar del objeto `Customer` completo. Dado que `Name` es una cadena, el argumento de tipo de `custNameQuery` es `string`, no `Customer`.  
  
3.  Dado que `custNameQuery` es una secuencia de cadenas, la variable de iteración del bucle `foreach` también debe ser `string`.  
  
 En la ilustración siguiente se muestra una transformación un poco más compleja. La instrucción `select` devuelve un tipo anónimo que captura solo dos miembros del objeto `Customer` original.  
  
 ![Una consulta que transforma el tipo de datos](../../../../csharp/programming-guide/concepts/linq/media/linq_flow3.png "LINQ_flow3")  
  
1.  El argumento de tipo del origen de datos siempre es el tipo de la variable de rango de la consulta.  
  
2.  Dado que la instrucción `select` genera un tipo anónimo, la variable de consulta debe declararse implícitamente mediante `var`.  
  
3.  Dado que el tipo de la variable de consulta es implícito, la variable de iteración del bucle `foreach` también debe ser implícita.  
  
## <a name="letting-the-compiler-infer-type-information"></a>Permitir que el compilador deduzca la información de tipo  
 Aunque debería comprender las relaciones de los tipos en una operación de consulta, tiene la opción de que el compilador le haga todo el trabajo. La palabra clave [var](../../../../csharp/language-reference/keywords/var.md) se puede usar para cualquier variable local en una operación de consulta. La ilustración siguiente es similar al ejemplo número 2 que se ha analizado anteriormente. En cambio, el compilador proporciona el tipo seguro de cada variable en la operación de consulta.  
  
 ![Flujo de tipos con asignación implícita de tipos ](../../../../csharp/programming-guide/concepts/linq/media/linq_flow4.png "LINQ_flow4")  
  
 Para obtener más información sobre `var`, vea [Variables locales con asignación implícita de tipos](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
