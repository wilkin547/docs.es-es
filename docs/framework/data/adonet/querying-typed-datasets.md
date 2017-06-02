---
title: "Consultar DataSets con establecimiento de tipos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Consultar DataSets con establecimiento de tipos
Si el esquema de <xref:System.Data.DataSet> se conoce en tiempo de diseño de la aplicación, se recomienda usar un <xref:System.Data.DataSet> con tipo al utilizar [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  Un <xref:System.Data.DataSet> con tipo es una clase que se deriva de un <xref:System.Data.DataSet>.  Como tal, hereda todos los métodos, eventos y propiedades de un <xref:System.Data.DataSet>.  Además, un <xref:System.Data.DataSet> con tipo proporciona métodos, eventos y propiedades fuertemente tipados.  Esto significa que se puede tener acceso a tablas y columnas por su nombre, en lugar de utilizar métodos de una colección.  Esto hace que las consultas sean más sencillas y más legibles.  Para obtener más información, consulta [DataSets con establecimiento de tipos](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] también admite las consultas en un <xref:System.Data.DataSet> con tipo.  Con un <xref:System.Data.DataSet> con tipo no hay que usar el método <xref:System.Data.DataRowExtensions.Field%2A> genérico o el método <xref:System.Data.DataRowExtensions.SetField%2A> para tener acceso a los datos de la columna.  Los nombres de propiedad están disponibles en el tiempo de compilación porque la información de tipo se incluye en <xref:System.Data.DataSet>. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] proporciona acceso a valores de columna como tipo correcto para que los errores de no coincidencia de tipos se detecten cuando se compile el código en lugar de en tiempo de ejecución.  
  
 Antes de poder empezar a consultar un <xref:System.Data.DataSet> con tipo se debe generar la clase usando el Diseñador de DataSet de [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  Para obtener más información, consulta [Cómo: Crear un conjunto de datos con tipo](../Topic/Create%20and%20configure%20datasets%20in%20Visual%20Studio.md).  
  
## Ejemplo  
 En el siguiente ejemplo se muestra una consulta sobre un <xref:System.Data.DataSet> con tipo:  
  
```csharp  
var query = from o in orders  
            where o.OnlineOrderFlag == true  
            select new { o.SalesOrderID,  
                         o.OrderDate,  
                         o.SalesOrderNumber };  
  
foreach(var order in query)   
{  
    Console.WriteLine("{0}\t{1:d}\t{2}",   
order.SalesOrderID,   
order.OrderDate,   
order.SalesOrderNumber);  
}  
```  
  
```vb  
Dim orders = ds.Tables("SalesOrderHeader")  
  
Dim query = _  
       From o In orders _  
       Where o.OnlineOrderFlag = True _  
       Select New {SalesOrderID := o.SalesOrderID, _  
                   OrderDate := o.OrderDate, _  
                   SalesOrderNumber := o.SalesOrderNumber}  
  
For Each Dim onlineOrder In query  
 Console.WriteLine("{0}\t{1:d}\t{2}", _  
 onlineOrder.SalesOrderID, _  
 onlineOrder.OrderDate, _  
 onlineOrder.SalesOrderNumber)  
Next  
```  
  
## Vea también  
 [Consultar DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)   
 [Consultas entre tablas](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)   
 [Consultas de tabla única](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)