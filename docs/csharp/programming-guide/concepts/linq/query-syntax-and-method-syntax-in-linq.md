---
title: "Query Syntax and Method Syntax in LINQ (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "LINQ [C#], query syntax vs. method syntax"
  - "queries [LINQ in C#], syntax comparisons"
ms.assetid: eedd6dd9-fec2-428c-9581-5b8783810ded
caps.latest.revision: 30
caps.handback.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Query Syntax and Method Syntax in LINQ (C#)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

La mayoría de las consultas en la documentación introductoria query language Integrated query \([!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]\) se escriben utilizando la sintaxis declarativa de la consulta LINQ.  Sin embargo, la sintaxis de la consulta se debe traducir en llamadas a métodos para Common Language Runtime \(CLR\) .NET cuando se compila el código.  Estas llamadas a métodos invocan los operadores de consulta estándar, que tienen nombres como `Where`, `Select`, `GroupBy`, `Join`, `Max`, y `Average`.  Puede llamarlas directamente con sintaxis de método en lugar de sintaxis de consulta.  
  
 La sintaxis de consulta y la sintaxis de método son semánticamente idénticas, pero muchas personas encuentra la sintaxis de consulta más sencilla y más fácil de leer.  Algunas consultas deben expresarse como llamadas a método.  Por ejemplo, debe utilizar una llamada al método para expresar una consulta que recupera el número de elementos que coinciden con una condición especificada.  También debe utilizar una llamada al método para una consulta que recupera el elemento que tiene el valor máximo de una secuencia de origen.  En la documentación de referencia de los operadores de consulta estándar en el espacio de nombres <xref:System.Linq> generalmente se utiliza la sintaxis de método.  Por consiguiente, aunque esté empezando a escribir consultas [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], le resultará útil estar familiarizado con el uso de la sintaxis de método en consultas y en expresiones de consulta.  
  
## Métodos de extensión de operador de consulta estándar  
 En el ejemplo siguiente se muestra una *expresión de consulta* simple y la consulta semánticamente equivalente, escrita como *consulta basada en método*.  
  
 [!code-cs[csLINQGettingStarted#22](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/query-syntax-and-method-syntax-in-linq_1.cs)]  
  
 El resultado de los dos ejemplos es idéntico.  Puede ver que el tipo de la variable de consulta es el mismo en ambos formatos: <xref:System.Collections.Generic.IEnumerable%601>.  
  
 Para entender la consulta basada en método, examinémosla más de cerca.  En el lado derecho de la expresión, observe que la cláusula `where` se expresa ahora como un método de instancia en el objeto `numbers`, que, como recordará, es de tipo `IEnumerable<int>`.  Si está familiarizado con la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>, sabrá que no tiene un método `Where`.  Sin embargo, si invoca la lista de finalización de IntelliSense en el IDE de Visual Studio, verá no sólo un método `Where`, sino muchos otros métodos, como `Select`, `SelectMany`, `Join` y `Orderby`.  Éstos son todos los operadores de consulta estándar.  
  
 ![Operadores de consulta estándar en Intellisense](../../../../csharp/programming-guide/concepts/linq/media/standardqueryops.png "StandardQueryOps")  
  
 Aunque parece que <xref:System.Collections.Generic.IEnumerable%601> se ha redefinido para incluir estos métodos adicionales, no es así.  Los operadores de consulta estándar se implementan como un nuevo tipo de método denominado *método de extensión*.  Los métodos de extensión "extienden" un tipo existente; se pueden llamar como si fueran métodos de instancia en el tipo.  Los operadores de consulta estándar extienden <xref:System.Collections.Generic.IEnumerable%601> y por eso puede escribir `numbers.Where(...)`.  
  
 Para empezar a utilizar [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], todo lo que realmente tiene que saber sobre los métodos de extensión es cómo incluirlos en el ámbito en su aplicación utilizando las directivas `using` correctas.  Esto se explica además en [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  Desde el punto de vista de la aplicación, un método de extensión y un método de instancia normal son iguales.  
  
 Para obtener más información acerca de los métodos de extensión, vea [Métodos de extensión](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  Para obtener más información sobre los operadores de consulta estándar, vea [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  Algunos proveedores [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], como [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] y [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], implementan sus propios operadores de consulta estándar y métodos de extensión adicionales para otros tipos además de <xref:System.Collections.Generic.IEnumerable%601>.  
  
## Expresiones lambda  
 En el ejemplo anterior, observe que la expresión condicional \(`num % 2 == 0`\) se pasa como argumento en línea al método de `Where` : la expresión insertada de `Where(num => num % 2 == 0).` This se denomina expresión lambda.  Es una manera sencilla de escribir código que de lo contrario sería más complejo y debería escribirse como método anónimo, delegado genérico o árbol de expresión.  En C\#, `=>` es el operador lambda, que se lee como "va a".  El elemento `num` que está a la izquierda del operador es la variable de entrada que corresponde a `num` en la expresión de consulta.  El compilador puede deducir el tipo de `num` porque sabe que `numbers` es un tipo <xref:System.Collections.Generic.IEnumerable%601> genérico.  El cuerpo de una expresión lambda es exactamente igual que el de una expresión en sintaxis de consulta o cualquier otra expresión o instrucción de C\#; puede incluir llamadas a método y otra lógica compleja.  El "valor devuelto" es tan solo el resultado de la expresión.  
  
 Para iniciarse en [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], no es necesario utilizar muchas expresiones lambda.  Sin embargo, ciertas consultas sólo se pueden expresar en sintaxis de método y algunas requieren el uso de expresiones lambda.  Una vez que esté más familiarizado con las expresiones lambda, verá que son una herramienta eficaz y flexible en su cuadro de herramientas [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)].  Para obtener más información, consulte [Expresiones lambda](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
## Combinabilidad de las consultas  
 En el ejemplo de código anterior, observe que se invoca el método `OrderBy` usando el operador de punto en la llamada a `Where`.  `Where` crea una secuencia filtrada y, a continuación, `Orderby` actúa en esa secuencia ordenándola.  Dado que las consultas devuelven `IEnumerable`, en la sintaxis de método se combinan concatenando las llamadas a método.  Esto es lo que el compilador hace en segundo plano cuando se escriben consultas en sintaxis de consulta.  Y, dado que una variable de consulta no almacena los resultados de la consulta, puede modificarla o utilizarla en cualquier momento como base para una nueva consulta, incluso después de haberla ejecutado.  
  
## Vea también  
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)