---
title: "Transformaciones de datos con LINQ (C#) | Microsoft Docs"
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
  - "LINQ [C#], transformación de datos"
  - "elementos de origen [LINQ en C#]"
  - "combinar varias entradas [LINQ en C#]"
  - "varias salidas para una sola secuencia de salida [LINQ en C#]"
  - "subconjunto de elementos de origen [LINQ en C#]"
  - "orígenes de datos [LINQ en C#], transformaciones de datos"
  - "transformaciones de datos [LINQ en C#]"
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Transformaciones de datos con LINQ (C#)
[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)] no trata simplemente de la recuperación de datos.  También es una herramienta eficaz para transformarlos.  Mediante una consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)], puede utilizar una secuencia de origen como entrada y modificarla de muchas maneras para crear una nueva secuencia de salida.  Puede modificar la propia secuencia sin modificar los elementos con operaciones de ordenación y agrupación. Pero quizás la característica más eficaz de las consultas de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] es la capacidad de crear nuevos tipos.  Esto se logra en la cláusula [select](../../../../csharp/language-reference/keywords/select-clause.md).  Por ejemplo, puede realizar las tareas siguientes:  
  
-   Combinar varias secuencias de entrada en una sola secuencia de salida que tiene un tipo nuevo.  
  
-   Crear secuencias de salida cuyos elementos estén formados por una o varias propiedades de cada elemento de la secuencia de origen.  
  
-   Crear secuencias de salida cuyos elementos estén formados por los resultados de operaciones realizadas en los datos de origen.  
  
-   Crear secuencias de salida en un formato diferente.  Por ejemplo, puede transformar datos de filas SQL o archivos de texto en XML.  
  
 Éstos son sólo algunos ejemplos.  De hecho, estas transformaciones se pueden combinar de varias maneras en la misma consulta.  Además, la secuencia de salida de una consulta se puede utilizar como secuencia de entrada para una nueva consulta.  
  
## Combinar varias entradas en una sola secuencia de salida  
 Puede utilizar una consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] para crear una secuencia de salida que contenga elementos de más de una secuencia de entrada.  En el ejemplo siguiente se muestra cómo combinar dos estructuras de datos en memoria, pero se pueden aplicar los mismos principios para combinar datos de orígenes XML, SQL o de conjunto de datos.  Supongamos que tenemos los dos tipos de clases siguientes:  
  
 [!code-cs[CsLINQGettingStarted#7](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#7)]  
  
 En el ejemplo siguiente se muestra la consulta:  
  
 [!code-cs[CSLinqGettingStarted#8](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#8)]  
  
 Para obtener más información, consulte [join \(cláusula\)](../../../../csharp/language-reference/keywords/join-clause.md) y [select \(cláusula\)](../../../../csharp/language-reference/keywords/select-clause.md).  
  
## Seleccionar un subconjunto de cada elemento de origen  
 Principalmente existen dos maneras de seleccionar un subconjunto de cada elemento de la secuencia de origen:  
  
1.  Para seleccionar un solo miembro del elemento de origen, utilice la operación con punto.  En el ejemplo siguiente, supongamos que un objeto `Customer` contiene varias propiedades públicas que incluyen una cadena denominada `City`.  Cuando se ejecuta, esta consulta generará una secuencia de salida de cadenas.  
  
    ```  
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2.  Para crear elementos que contienen más de una propiedad del elemento de origen, puede utilizar un inicializador de objeto con un objeto con nombre o un tipo anónimo.  En el ejemplo siguiente se muestra el uso de un tipo anónimo para encapsular dos propiedades de cada elemento `Customer`:  
  
    ```  
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 Para obtener más información, consulte [Inicializadores de objeto y colección](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) y [Tipos anónimos](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
## Transformar objetos en memoria en XML  
 Las consultas [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] hacen que sea fácil transformar los datos entre estructuras de datos en memoria, bases de datos SQL, conjuntos de datos [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado-md.md)] y documentos o secuencias XML.  En el ejemplo siguiente se transforman los objetos de una estructura de datos en memoria en elementos XML.  
  
 [!code-cs[CsLINQGettingStarted#9](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#9)]  
  
 El código genera el siguiente resultado XML:  
  
```  
< Root>  
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
  
 Para obtener más información, vea [Crear árboles XML en C\#](../Topic/Creating%20XML%20Trees%20in%20C%23%20\(LINQ%20to%20XML\)1.md).  
  
## Realizar operaciones con elementos de origen  
 Es posible que una secuencia de salida no contenga elementos o propiedades de elemento de la secuencia de origen.  Por el contrario, la salida podría ser una secuencia de valores que se calcula utilizando los elementos de origen como argumentos de entrada.  Cuando se ejecuta la siguiente consulta simple, genera una secuencia de cadenas cuyos valores representan un cálculo basado en la secuencia de origen de elementos de tipo `double`.  
  
> [!NOTE]
>  No se permite llamar a métodos en las expresiones de consulta si la consulta se va a convertir en otro dominio.  Por ejemplo, no puede llamar a un método normal de C\# en [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)] porque SQL Server no tiene contexto para el mismo.  Sin embargo, puede asignar procedimientos almacenados a los métodos y después llamar a los primeros.  Para obtener más información, consulte [Procedimientos almacenados](../Topic/Stored%20Procedures.md).  
  
 [!code-cs[CsLINQGettingStarted#10](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#10)]  
  
## Vea también  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [LINQ a SQL](../Topic/LINQ%20to%20SQL.md)   
 [LINQ to DataSet](../Topic/LINQ%20to%20DataSet.md)   
 [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)   
 [Expresiones de consulta LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [select \(cláusula\)](../../../../csharp/language-reference/keywords/select-clause.md)   
 [Cómo: Combinar datos con cláusulas Join](../../../../visual-basic/programming-guide/language-features/linq/how-to-combine-data-with-linq-by-using-joins.md)