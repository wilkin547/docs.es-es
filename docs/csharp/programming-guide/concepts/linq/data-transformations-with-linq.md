---
title: Transformaciones de datos con LINQ (C#)
description: Aprenda a usar consultas LINQ en C# para transformar datos. Puede modificar la secuencia mediante la ordenación y la agrupación, y la creación de tipos mediante la cláusula SELECT.
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], data transformations
- source elements [LINQ in C#]
- joining multiple inputs [LINQ in C#]
- multiple outputs for one output sequence [LINQ in C#]
- subset of source elements [LINQ in C#]
- data sources [LINQ in C#], data transformations
- data transformations [LINQ in C#]
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
ms.openlocfilehash: 6844cf2aa589f7516a9e40bc604c5f907ec6d311
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104015"
---
# <a name="data-transformations-with-linq-c"></a>Transformaciones de datos con LINQ (C#)
Language-Integrated Query (LINQ) no solo es para recuperar datos. También es una herramienta eficaz para transformarlos. Mediante el uso de un consulta LINQ, se puede usar una secuencia de origen como entrada y modificarla de muchas maneras para crear una nueva secuencia de salida. Por medio de ordenaciones y agrupaciones se puede modificar la propia secuencia sin modificar los elementos. Pero quizás la característica más eficaz de las consultas LINQ es la capacidad para crear nuevos tipos. Esto se realiza en la cláusula [select](../../../language-reference/keywords/select-clause.md). Por ejemplo, puede realizar las tareas siguientes:  
  
- Combinar varias secuencias de entrada en una sola secuencia de salida que tiene un tipo nuevo.  
  
- Crear secuencias de salida cuyos elementos estén formados por una o varias propiedades de cada elemento de la secuencia de origen.  
  
- Crear secuencias de salida cuyos elementos estén formados por los resultados de las operaciones realizadas en el origen de datos.  
  
- Crear secuencias de salida en un formato diferente. Por ejemplo, se pueden transformar datos de filas de SQL o archivos de texto en XML.  
  
 Estos son solo algunos ejemplos. Por supuesto, estas transformaciones pueden combinarse de diversas formas en la misma consulta. Además, se puede usar la secuencia de salida de una consulta como la secuencia de entrada para una nueva consulta.  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a>Combinar varias entradas en una secuencia de salida  
 Se puede usar una consulta LINQ para crear una secuencia de salida que contiene los elementos de más de una secuencia de entrada. En el ejemplo siguiente se muestra cómo combinar dos estructuras de datos en memoria, pero se pueden aplicar los mismos principios para combinar datos de XML o de orígenes SQL o DataSet. Supongamos los dos tipos de clase siguientes:  
  
 [!code-csharp[CsLINQGettingStarted#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#7)]  
  
 En el ejemplo siguiente se muestra la consulta:  
  
 [!code-csharp[CSLinqGettingStarted#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#8)]  
  
 Para obtener más información, vea [join (Cláusula)](../../../language-reference/keywords/join-clause.md) y [select (Cláusula)](../../../language-reference/keywords/select-clause.md).  
  
## <a name="selecting-a-subset-of-each-source-element"></a>Seleccionar un subconjunto de cada elemento de origen  
 Hay dos maneras principales de seleccionar un subconjunto de cada elemento de la secuencia de origen:  
  
1. Para seleccionar a un solo miembro del elemento de origen, use la operación de punto. En el ejemplo siguiente, suponga que un objeto `Customer` contiene varias propiedades públicas, incluida una cadena denominada `City`. Cuando se ejecuta, esta consulta genera una secuencia de salida de cadenas.  
  
    ```csharp
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2. Para crear elementos que contengan más de una propiedad del elemento de origen, se puede usar un inicializador de objeto con un objeto con nombre o un tipo anónimo. En el ejemplo siguiente se muestra el uso de un tipo anónimo para encapsular dos propiedades de cada elemento `Customer`:  
  
    ```csharp
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 Para obtener más información, vea [Inicializadores de objeto y de colección](../../classes-and-structs/object-and-collection-initializers.md) y [Tipos anónimos](../../classes-and-structs/anonymous-types.md).  
  
## <a name="transforming-in-memory-objects-into-xml"></a>Transformar objetos en memoria en XML  
 Las consultas LINQ facilitan la transformación de datos entre estructuras de datos en memoria, bases de datos SQL, conjuntos de datos de ADO.NET y documentos o secuencias de XML. En el siguiente ejemplo se transforman objetos de una estructura de datos en memoria en elementos XML.  
  
 [!code-csharp[CsLINQGettingStarted#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#9)]  
  
 El código produce el siguiente resultado de XML:  
  
```xml  
<Root>  
  <student>  
    <First>Svetlana</First>  
    <Last>Omelchenko</Last>  
    <Scores>97,92,81,60</Scores>  
  </student>  
  <student>  
    <First>Claire</First>  
    <Last>O'Donnell</Last>  
    <Scores>75,84,91,39</Scores>  
  </student>  
  <student>  
    <First>Sven</First>  
    <Last>Mortensen</Last>  
    <Scores>88,94,65,91</Scores>  
  </student>  
</Root>  
```  
  
 Para obtener más información, vea [Creating XML Trees (C#)](./creating-xml-trees-linq-to-xml-2.md) (Creación de árboles XML [C#]).  
  
## <a name="performing-operations-on-source-elements"></a>Realizar operaciones en los elementos de origen  
 Es posible que una secuencia de salida no contenga ningún elemento o propiedades de elemento de la secuencia de origen. En su lugar, es posible que la salida sea una secuencia de valores que se calcula usando los elementos de origen como argumentos de entrada.

 La consulta siguiente tomará una secuencia de números que representan radios de círculos, calculará el área de cada radio y devolverá una secuencia de salida que contenga cadenas con el formato del área calculada.

 Se dará formato a cada cadena de la secuencia de salida mediante la [interpolación de cadenas](../../../language-reference/tokens/interpolated.md). Una cadena interpolada presentará un elemento `$` delante de las comillas de apertura de la cadena, y las operaciones se pueden realizar entre llaves colocadas dentro de la cadena interpolada. Tras realizar las operaciones, se concatenarán los resultados.
  
> [!NOTE]
> No se admite llamar a métodos en expresiones de consulta si la consulta se va a convertir a otro dominio. Por ejemplo, no se puede llamar a un método normal de C# en [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] porque SQL Server no tiene contexto para él. En cambio, se pueden asignar procedimientos almacenados a los métodos y llamar a los primeros. Para obtener más información, vea [Procedimientos almacenados](../../../../framework/data/adonet/sql/linq/stored-procedures.md).  
  
 [!code-csharp[CsLINQGettingStarted#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#10)]  
  
## <a name="see-also"></a>Vea también

- [Language Integrated Query (LINQ) (C#)](./index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)
- [LINQ to XML (C#)](./linq-to-xml-overview.md)
- [Expresiones de consulta LINQ](../../../linq/index.md)
- [select (cláusula)](../../../language-reference/keywords/select-clause.md)
