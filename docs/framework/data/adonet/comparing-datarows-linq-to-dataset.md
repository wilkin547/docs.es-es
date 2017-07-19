---
title: "Comparar DataRows (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8fe0eadf-297b-487c-8d4b-7816753c2883
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Comparar DataRows (LINQ to DataSet)
[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] define varios operadores de conjuntos para comparar elementos de origen y ver si son iguales.  [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] proporciona los siguientes operadores de conjuntos:  
  
-   <xref:System.Linq.Enumerable.Distinct%2A>  
  
-   <xref:System.Linq.Enumerable.Union%2A>  
  
-   <xref:System.Linq.Enumerable.Intersect%2A>  
  
-   <xref:System.Linq.Enumerable.Except%2A>  
  
 Estos operadores comparan elementos origen llamando a los métodos <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> y <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> de cada colección de elementos.  En el caso de <xref:System.Data.DataRow>, estos operadores realizan una comparación de referencia, lo que en general no constituye un comportamiento ideal para operaciones de conjunto en datos tabulares.  Para las operaciones de conjuntos, por lo general deseará determinar si los valores del elemento son iguales o no a las referencias del elemento.  Por ello, se ha agregado la clase <xref:System.Data.DataRowComparer> a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  Esta clase se puede utilizar para comparar valores de fila.  
  
 La clase <xref:System.Data.DataRowComparer> contiene una implementación de comparación del valor para <xref:System.Data.DataRow>, de modo que esta clase se puede utilizar para operaciones de conjuntos como <xref:System.Linq.Enumerable.Distinct%2A>.  No se puede crear una instancia directamente de esta clase. En su lugar, debe utilizarse la propiedad <xref:System.Data.DataRowComparer.Default%2A> para devolver una instancia de <xref:System.Data.DataRowComparer>.  Entonces, se llama al método <xref:System.Data.DataRowComparer.Equals%2A> y los dos objetos <xref:System.Data.DataRow> que se van a comparar se pasan como parámetros de entrada.  El método <xref:System.Data.DataRowComparer.Equals%2A> devuelve `true` si los conjuntos ordenados de valores de columna de ambos objetos <xref:System.Data.DataRow> son iguales; de lo contrario, devuelve `false`.  
  
## Ejemplo  
 Este ejemplo usa `Intersect` para devolver contactos que aparecen en ambas tablas.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
### Ejemplo  
 El ejemplo siguiente compara dos filas y obtiene sus códigos hash.  
  
 [!code-vb[DP LINQ to DataSet Examples#CompareDifferentRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#comparedifferentrows)]  
  
## Vea también  
 <xref:System.Data.DataRowComparer>   
 [Cargar datos en DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)   
 [Ejemplos de LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)