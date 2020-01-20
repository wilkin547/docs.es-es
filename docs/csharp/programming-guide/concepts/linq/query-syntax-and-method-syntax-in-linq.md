---
title: Sintaxis de consultas y sintaxis de métodos en LINQ (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], query syntax vs. method syntax
- queries [LINQ in C#], syntax comparisons
ms.assetid: eedd6dd9-fec2-428c-9581-5b8783810ded
ms.openlocfilehash: 17280daaf98010245bbd019652a2a46d7f66ab59
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635501"
---
# <a name="query-syntax-and-method-syntax-in-linq-c"></a>Sintaxis de consultas y sintaxis de métodos en LINQ (C#)
La mayoría de las consultas de la documentación introductoria de Language Integrated Query (LINK) se escribe con la sintaxis de consulta declarativa de LINQ. Pero la sintaxis de consulta debe traducirse en llamadas de método para .NET Common Language Runtime (CLR) al compilar el código. Estas llamadas de método invocan los operadores de consulta estándar, que tienen nombres tales como `Where`, `Select`, `GroupBy`, `Join`, `Max` y `Average`. Puede llamarlas directamente con la sintaxis de método en lugar de la sintaxis de consulta.  
  
 La sintaxis de consulta y la sintaxis de método son idénticas desde el punto de vista semántico, pero muchos usuarios creen que la sintaxis de consulta es mucho más sencilla y fácil de leer. Algunos métodos deben expresarse como llamadas de método. Por ejemplo, debe usar una llamada de método para expresar una consulta que recupera el número de elementos que cumplen una condición especificada. También debe usar una llamada de método para una consulta que recupera el elemento que tiene el valor máximo de una secuencia de origen. La documentación de referencia de los operadores de consulta estándar del espacio de nombres <xref:System.Linq> generalmente usa la sintaxis de método. Por consiguiente, incluso cuando empiece a escribir consultas de LINK, resulta útil estar familiarizado con el uso de la sintaxis de método en las consultas y en las propias expresiones de consulta.  
  
## <a name="standard-query-operator-extension-methods"></a>Métodos de extensión de operador de consulta estándar  
 En el ejemplo siguiente se muestra una *expresión de consulta* sencilla y la consulta equivalente desde el punto de vista semántico que se escribe como *consulta basada en métodos*.  
  
 [!code-csharp[csLINQGettingStarted#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#22)]  
  
 El resultado de los dos ejemplos es idéntico. Como puede ver, el tipo de variable de consulta es el mismo en ambos formularios: <xref:System.Collections.Generic.IEnumerable%601>.  
  
 Para entender la consulta basada en métodos, vamos a examinarla más detenidamente. En el lado derecho de la expresión, observe que la cláusula `where` ahora se expresa como un método de instancia en el objeto `numbers`, que, como recordará, tiene un tipo de `IEnumerable<int>`. Si está familiarizado con la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>, sabe que no tiene un método `Where`. Pero si se invoca la lista de finalización de IntelliSense en el IDE de Visual Studio, verá no solo un método `Where`, sino muchos otros métodos tales como `Select`, `SelectMany`, `Join` y `Orderby`. Estos son todos los operadores de consulta estándar.  
  
 ![Captura de pantalla en la que se muestran todos los operadores de consulta estándar de IntelliSense.](./media/query-syntax-and-method-syntax-in-linq/standard-query-operators.png)  
  
 Aunque parece que <xref:System.Collections.Generic.IEnumerable%601> se haya redefinido para incluir estos métodos adicionales, en realidad no es el caso. Los operadores de consulta estándar se implementan como un nuevo tipo de método denominado *método de extensión*. Los métodos de extensión "extienden" un tipo existente; se pueden llamar como si fueran métodos de instancia en el tipo. Los operadores de consulta estándar extienden <xref:System.Collections.Generic.IEnumerable%601> y esta es la razón por la que la puede escribir `numbers.Where(...)`.  
  
 Para empezar a usar LINK, lo único que realmente debe saber sobre los métodos de extensión es cómo incluirlos en el ámbito de la aplicación mediante el uso correcto de directivas `using`. Desde el punto de vista de la aplicación, un método de extensión y un método de instancia normal son iguales.  
  
 Para obtener más información sobre los métodos de extensión, vea [Extension Methods](../../classes-and-structs/extension-methods.md) (Métodos de extensión). Para obtener más información sobre los operadores de consulta estándar, vea [Información general sobre operadores de consulta estándar (C#)](./standard-query-operators-overview.md). Algunos proveedores de LINK, como [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], implementan sus propios operadores de consulta estándar y otros métodos de extensión además de <xref:System.Collections.Generic.IEnumerable%601>.  
  
## <a name="lambda-expressions"></a>Expresiones lambda  
 En el ejemplo anterior, observe que la expresión condicional (`num % 2 == 0`) se pasa como argumento insertado al método `Where`: `Where(num => num % 2 == 0).` Esta expresión insertada se denomina expresión lambda. Se trata de una forma cómoda de escribir código que, de lo contrario, tendría que escribirse de forma más compleja como un método anónimo, un delegado genérico o un árbol de expresión. En C#, `=>` es el operador lambda, que se lee como "va a". La `num` situada a la izquierda del operador es la variable de entrada que corresponde a `num` en la expresión de consulta. El compilador puede deducir el tipo de `num` porque sabe que `numbers` es un tipo <xref:System.Collections.Generic.IEnumerable%601> genérico. El cuerpo de la expresión lambda es exactamente igual que la expresión de la sintaxis de consulta o de cualquier otra expresión o instrucción de C#; puede incluir llamadas de método y otra lógica compleja. El "valor devuelto" es simplemente el resultado de la expresión.  
  
 Para empezar a usar LINK, no es necesario emplear muchas expresiones lambda. Pero determinadas consultas solo se pueden expresar en sintaxis de método y algunas requieren expresiones lambda. Cuando esté más familiarizado con las expresiones lambda, verá que se trata de una herramienta eficaz y flexible del cuadro de herramientas de LINK. Para obtener más información, vea [Expresiones lambda](../../statements-expressions-operators/lambda-expressions.md).  
  
## <a name="composability-of-queries"></a>Capacidad de composición de consultas  
 En el ejemplo de código anterior, tenga en cuenta que el método `OrderBy` se invoca mediante el operador de punto en la llamada a `Where`. `Where` crea una secuencia filtrada y, luego, `Orderby` actúa en dicha secuencia ordenándola. Dado que las consultas devuelven un `IEnumerable`, redáctelas con la sintaxis de método encadenando las llamadas de método. Es lo que el compilador hace en segundo plano cuando se escriben consultas con la sintaxis de consulta. Y dado que una variable de consulta no almacena los resultados de la consulta, puede modificarla o usarla como base para una nueva consulta en cualquier momento, incluso después de que se haya ejecutado.  
