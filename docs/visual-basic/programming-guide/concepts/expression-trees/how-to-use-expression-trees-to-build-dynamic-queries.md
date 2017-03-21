---
title: "Cómo: usar árboles de expresión para crear consultas dinámicas (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8d69be78a9f3568535dffe54e21af80c6eb12f70
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-visual-basic"></a>Cómo: usar árboles de expresión para crear consultas dinámicas (Visual Basic)
En LINQ, árboles de expresión se utilizan para representar consultas estructuradas que orígenes de destino de datos que implementan <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> Por ejemplo, el proveedor LINQ implementa el <xref:System.Linq.IQueryable%601>interfaz para realizar consultas en almacenes de datos relacionales.</xref:System.Linq.IQueryable%601> El compilador de Visual Basic compila las consultas dirigidas a tales orígenes de datos en el código que genera un árbol de expresión en tiempo de ejecución. El proveedor de consultas puede atravesar la estructura de datos del árbol de expresión y convertirla en un lenguaje de consulta adecuado para el origen de datos.  
  
 Árboles de expresión también se utilizan en LINQ para representar expresiones lambda que se asignan a variables de tipo <xref:System.Linq.Expressions.Expression%601>.</xref:System.Linq.Expressions.Expression%601>  
  
 En este tema se describe cómo utilizar árboles de expresión para crear consultas dinámicas de LINQ. Las consultas dinámicas son útiles cuando no se conocen los detalles de una consulta en tiempo de compilación. Por ejemplo, una aplicación podría proporcionar una interfaz de usuario que permite al usuario final especificar uno o más predicados para filtrar los datos. Para usar LINQ para consultar, este tipo de aplicación debe utilizar árboles de expresión para crear la consulta LINQ en tiempo de ejecución.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar árboles de expresión para construir una consulta contra una `IQueryable` origen de datos y, a continuación, ejecútelo. El código crea un árbol de expresión para representar la consulta siguiente:  
  
 `companies.Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16).OrderBy(Function(company) company)`  
  
 Los métodos de fábrica en el <xref:System.Linq.Expressions>espacio de nombres se utilizan para crear árboles de expresiones que representan las expresiones que constituyen la consulta global.</xref:System.Linq.Expressions> Las expresiones que representan llamadas a métodos de operador de consulta estándar hacen referencia a la <xref:System.Linq.Queryable>implementaciones de estos métodos.</xref:System.Linq.Queryable> El árbol de expresión final se pasa a la <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29>implementación del proveedor de la `IQueryable` el origen de datos para crear una consulta ejecutable de tipo `IQueryable`.</xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> Los resultados se obtienen enumerando esa variable de consulta.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Este código utiliza un número fijo de expresiones en el predicado que se pasa a la `Queryable.Where` (método). Sin embargo, puede escribir una aplicación que combina un número variable de expresiones de predicado que depende de la entrada del usuario. También puede variar los operadores de consulta estándar que se llaman en la consulta, dependiendo de la entrada del usuario.  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   Crear un nuevo **aplicación de consola** proyecto.  
  
-   Si no se hace referencia, agregue una referencia a System.Core.dll.  
  
-   Incluir el espacio de nombres System.Linq.Expressions.  
  
-   Copie el código del ejemplo y péguelo en el `Main` `Sub` procedimiento.  
  
## <a name="see-also"></a>Vea también  
 [Árboles de expresión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)   
 [Cómo: Ejecutar árboles de expresión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)
