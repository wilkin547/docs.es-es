---
title: "Cómo: Usar árboles de expresión para crear consultas dinámicas (C#) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 52cd44dd-a3ec-441e-b93a-4eca388119c7
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7de999848870de80996f308affde088088e32e52
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-c"></a>Cómo: Usar árboles de expresión para crear consultas dinámicas (C#)
En LINQ, los árboles de expresión se usan para representar consultas estructuradas destinadas a orígenes de datos que implementan <xref:System.Linq.IQueryable%601>. Por ejemplo, el proveedor LINQ implementa la interfaz <xref:System.Linq.IQueryable%601> para realizar consultas en almacenes de datos relacionales. El compilador de C# compila las consultas dirigidas a estos orígenes de datos en el código que genera un árbol de expresión en tiempo de ejecución. El proveedor de consultas puede después recorrer la estructura de datos del árbol de expresión y convertirla en un lenguaje de consulta adecuado para el origen de datos.  
  
 Los arboles de expresión también se usan en LINQ para representar expresiones lambda que se asignan a variables de tipo <xref:System.Linq.Expressions.Expression%601>.  
  
 En este tema se describe cómo usar árboles de expresión para crear consultas LINQ dinámicas. Las consultas dinámicas son útiles cuando no se conocen los detalles de una consulta en tiempo de compilación. Por ejemplo, es posible que una aplicación proporcione una interfaz de usuario que permita al usuario final especificar uno o más predicados para filtrar los datos. Para poder usar LINQ para realizar consultas, este tipo de aplicación debe usar árboles de expresión para crear la consulta LINQ en tiempo de ejecución.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar árboles de expresión para crear una consulta en un origen de datos `IQueryable` y después ejecutarlo. El código crea un árbol de expresión para representar la consulta siguiente:  
  
 `companies.Where(company => (company.ToLower() == "coho winery" || company.Length > 16)).OrderBy(company => company)`  
  
 Los métodos de generador en el espacio de nombres <xref:System.Linq.Expressions> se usan para crear árboles de expresión que representan las expresiones que constituyen la consulta global. Las expresiones que representan llamadas a los métodos de operador de consulta estándar hacen referencia a las implementaciones <xref:System.Linq.Queryable> de estos métodos. El árbol de expresión final se pasa a la implementación <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> del proveedor del origen de datos de `IQueryable` para crear una consulta ejecutable de tipo `IQueryable`. Los resultados se obtienen enumerando esa variable de consulta.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 En este código se usa un número fijo de expresiones en el predicado que se pasa al método `Queryable.Where`. Pero se puede escribir una aplicación que combine un número variable de expresiones de predicado que dependa de la entrada del usuario. También se pueden variar los operadores de consulta estándar que se llaman en la consulta, dependiendo de la entrada del usuario.  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   Cree un nuevo proyecto de **Aplicación de consola**.  
  
-   Agregue una referencia a System.Core.dll si todavía no existe.  
  
-   Incluya el espacio de nombres System.Linq.Expressions.  
  
-   Copie el código del primer ejemplo y péguelo en el método `Main`.  
  
## <a name="see-also"></a>Vea también  
 [Árboles de expresión (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md)   
 [Cómo: Ejecutar árboles de expresión (C#)](../../../../csharp/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)   
 [Cómo: Especificar dinámicamente filtros con predicado en tiempo de ejecución](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)
