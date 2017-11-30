---
title: "Sintaxis de consultas y sintaxis de métodos en LINQ (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- LINQ [C#], query syntax vs. method syntax
- queries [LINQ in C#], syntax comparisons
ms.assetid: eedd6dd9-fec2-428c-9581-5b8783810ded
caps.latest.revision: "30"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0127ee0815c4ba6a697456fe45bd373bcf9ba4e4
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="query-syntax-and-method-syntax-in-linq-c"></a>Sintaxis de consultas y sintaxis de métodos en LINQ (C#)
La mayoría de las consultas de la documentación introductoria de Language Integrated Query ([!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]) se escribe con la sintaxis de consulta declarativa de LINQ. Pero la sintaxis de consulta debe traducirse en llamadas de método para .NET Common Language Runtime (CLR) al compilar el código. Estas llamadas de método invocan los operadores de consulta estándar, que tienen nombres tales como `Where`, `Select`, `GroupBy`, `Join`, `Max` y `Average`. Puede llamarlas directamente con la sintaxis de método en lugar de la sintaxis de consulta.  
  
 La sintaxis de consulta y la sintaxis de método son idénticas desde el punto de vista semántico, pero muchos usuarios creen que la sintaxis de consulta es mucho más sencilla y fácil de leer. Algunos métodos deben expresarse como llamadas de método. Por ejemplo, debe usar una llamada de método para expresar una consulta que recupera el número de elementos que cumplen una condición especificada. También debe usar una llamada de método para una consulta que recupera el elemento que tiene el valor máximo de una secuencia de origen. La documentación de referencia de los operadores de consulta estándar del espacio de nombres <xref:System.Linq> generalmente usa la sintaxis de método. Por consiguiente, incluso cuando empiece a escribir consultas de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], resulta útil estar familiarizado con cómo se usa la sintaxis de método en consultas y en las propias expresiones de consulta.  
  
## <a name="standard-query-operator-extension-methods"></a>Métodos de extensión de operador de consulta estándar  
 En el ejemplo siguiente se muestra una *expresión de consulta* sencilla y la consulta equivalente desde el punto de vista semántico que se escribe como *consulta basada en métodos*.  
  
 [!code-csharp[csLINQGettingStarted#22](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/query-syntax-and-method-syntax-in-linq_1.cs)]  
  
 El resultado de los dos ejemplos es idéntico. Como puede ver, el tipo de variable de consulta es el mismo en ambos formularios: <xref:System.Collections.Generic.IEnumerable%601>.  
  
 Para entender la consulta basada en métodos, vamos a examinarla más detenidamente. En el lado derecho de la expresión, observe que la cláusula `where` ahora se expresa como un método de instancia en el objeto `numbers`, que, como recordará, tiene un tipo de `IEnumerable<int>`. Si está familiarizado con la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>, sabe que no tiene un método `Where`. Pero si se invoca la lista de finalización de IntelliSense en el IDE de Visual Studio, verá no solo un método `Where`, sino muchos otros métodos tales como `Select`, `SelectMany`, `Join` y `Orderby`. Estos son todos los operadores de consulta estándar.  
  
 ![Operadores de consulta estándar en Intellisense](../../../../csharp/programming-guide/concepts/linq/media/standardqueryops.png "StandardQueryOps")  
  
 Aunque parece que <xref:System.Collections.Generic.IEnumerable%601> se haya redefinido para incluir estos métodos adicionales, en realidad no es el caso. Los operadores de consulta estándar se implementan como un nuevo tipo de método denominado *método de extensión*. Los métodos de extensión "extienden" un tipo existente; se pueden llamar como si fueran métodos de instancia en el tipo. Los operadores de consulta estándar extienden <xref:System.Collections.Generic.IEnumerable%601> y esta es la razón por la que la puede escribir `numbers.Where(...)`.  
  
 Para empezar a usar [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], lo único que realmente debe saber sobre los métodos de extensión es cómo incluirlos en el ámbito de la aplicación mediante el uso correcto de directivas `using`. Desde el punto de vista de la aplicación, un método de extensión y un método de instancia normal son iguales.  
  
 Para obtener más información sobre los métodos de extensión, vea [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md) (Métodos de extensión). Para obtener más información sobre los operadores de consulta estándar, vea [Información general sobre operadores de consulta estándar (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md). Algunos proveedores de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], como [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], implementan sus propios operadores de consulta estándar y otros métodos de extensión además de <xref:System.Collections.Generic.IEnumerable%601>.  
  
## <a name="lambda-expressions"></a>Expresiones lambda  
 En el ejemplo anterior, observe que la expresión condicional (`num % 2 == 0`) se pasa como argumento insertado al método `Where`: `Where(num => num % 2 == 0).` Esta expresión insertada se denomina expresión lambda. Se trata de una forma cómoda de escribir código que, de lo contrario, tendría que escribirse de forma más compleja como un método anónimo, un delegado genérico o un árbol de expresión. En C#, `=>` es el operador lambda, que se lee como "va a". La `num` situada a la izquierda del operador es la variable de entrada que corresponde a `num` en la expresión de consulta. El compilador puede deducir el tipo de `num` porque sabe que `numbers` es un tipo <xref:System.Collections.Generic.IEnumerable%601> genérico. El cuerpo de la expresión lambda es exactamente igual que la expresión de la sintaxis de consulta o de cualquier otra expresión o instrucción de C#; puede incluir llamadas de método y otra lógica compleja. El "valor devuelto" es simplemente el resultado de la expresión.  
  
 Para empezar a usar [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], no es necesario emplear muchas expresiones lambda. Pero determinadas consultas solo se pueden expresar en sintaxis de método y algunas requieren expresiones lambda. Cuando esté más familiarizado con las expresiones lambda, verá que se trata de una herramienta eficaz y flexible del cuadro de herramientas de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. Para obtener más información, vea [Expresiones lambda](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
## <a name="composability-of-queries"></a>Capacidad de composición de consultas  
 En el ejemplo de código anterior, tenga en cuenta que el método `OrderBy` se invoca mediante el operador de punto en la llamada a `Where`. `Where` crea una secuencia filtrada y, luego, `Orderby` actúa en dicha secuencia ordenándola. Dado que las consultas devuelven un `IEnumerable`, redáctelas con la sintaxis de método encadenando las llamadas de método. Es lo que el compilador hace en segundo plano cuando se escriben consultas con la sintaxis de consulta. Y dado que una variable de consulta no almacena los resultados de la consulta, puede modificarla o usarla como base para una nueva consulta en cualquier momento, incluso después de que se haya ejecutado.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
