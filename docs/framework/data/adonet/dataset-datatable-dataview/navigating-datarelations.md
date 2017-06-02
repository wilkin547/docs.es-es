---
title: "Navegar por DataRelations | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Navegar por DataRelations
Una de las principales funciones de una <xref:System.Data.DataRelation> es permitir la navegación de una <xref:System.Data.DataTable> a otra dentro de un <xref:System.Data.DataSet>.  Esto permite recuperar todos los objetos <xref:System.Data.DataRow> relacionados de una **DataTable** cuando se da una única **DataRow** de una **DataTable** relacionada.  Por ejemplo, después de establecer una **DataRelation** entre una tabla de clientes y una tabla de pedidos, es posible recuperar todas las filas de pedidos de una fila de clientes determinada mediante **GetChildRows**.  
  
 En el siguiente ejemplo de código se crea una **DataRelation** entre la tabla **Customers** y la tabla **Orders** de un **DataSet**, y se devuelven todos los pedidos de cada cliente.  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 El ejemplo siguiente se basa en el anterior; se relacionan cuatro tablas y se navega por dichas relaciones.  Como en el ejemplo anterior, **CustomerID** relaciona la tabla **Customers** con la tabla **Orders**.  Para cada cliente de la tabla **Customers** se determinan todas las filas secundarias de la tabla **Orders** con el fin de devolver el número de pedidos que tiene un cliente concreto y sus valores de **OrderID**.  
  
 El ejemplo ampliado también devuelve los valores de las tablas **OrderDetails** y **Products**.  La tabla **Orders** está relacionada con la tabla **OrderDetails** mediante **OrderID** con el fin de determinar, para cada pedido de cliente, qué productos y cantidades se pidieron.  Como la tabla **OrderDetails** sólo contiene el **ProductID** de un producto pedido, **OrderDetails** está relacionada con **Products** mediante **ProductID** para devolver el **ProductName**.  En esta relación, **Products** es la tabla primaria y **Order Details** es la secundaria.  Por lo tanto, al recorrer en iteración la tabla **OrderDetails**, se llama a **GetParentRow** para recuperar el valor de **ProductName** relacionado.  
  
 Hay que tener en cuenta que al crear la **DataRelation** para las tablas **Customers** y **Orders** no se especifica ningún valor para la marca **createConstraints** \(el valor predeterminado es **true**\).  Se supone que todas las filas de la tabla **Orders** tienen un valor **CustomerID** que existe en la tabla primaria **Customers**.  Si un **CustomerID** existe en la tabla **Orders** pero no existe en la tabla **Customers**, una <xref:System.Data.ForeignKeyConstraint> hará que se inicie una excepción.  
  
 Cuando la columna secundaria pueda contener valores no incluidos en la columna primaria, hay que asignar el valor **false** a la marca **createConstraints** cuando se agregue la **DataRelation**.  En el ejemplo, la marca **createConstraints** tiene el valor **false** para la **DataRelation** entre las tablas **Orders** y **OrderDetails**.  Esto permite que la aplicación devuelva todos los registros de la tabla **OrderDetails** y sólo un subconjunto de registros de la tabla **Orders** sin generar una excepción en tiempo de ejecución.  El ejemplo ampliado genera el resultado con el siguiente formato.  
  
```  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 El siguiente ejemplo de código es un ejemplo ampliado en el que se devuelven los valores de las tablas **OrderDetails** y **Products**, y sólo se devuelve un subconjunto de los registros de la tabla **Orders**.  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## Vea también  
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)