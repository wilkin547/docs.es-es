---
title: "Crear DataView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Crear DataView
Hay dos formas de crear una <xref:System.Data.DataView>.  Puede utilizar el constructor **DataView** o puede crear una referencia a la propiedad <xref:System.Data.DataTable.DefaultView%2A> de la <xref:System.Data.DataTable>.  El constructor **DataView** puede estar vacío o puede aceptar también **DataTable** como único argumento o **DataTable** junto con el criterio de filtro o de ordenación, y un filtro de estado de fila.  Para obtener más información sobre los argumentos adicionales disponibles para su uso con **DataView**, vea [Ordenar y filtrar datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
 Como el índice de una **DataView** se crea al mismo tiempo que **DataView** y cuando se modifica alguna de las propiedades **Sort**, **RowFilter** o **RowStateFilter**, conseguirá un rendimiento óptimo si suministra cualquier criterio inicial de ordenación o filtro como argumentos del constructor al crear la **DataView**.  Al crear una **DataView** sin especificar criterios de ordenación o de filtro y establecer posteriormente las propiedades **Sort**, **RowFilter** o **RowStateFilter** hace que el índice se construya dos veces como mínimo: una vez al crear la **DataView** y la otra cuando se modifica cualquiera de las propiedades de ordenación y filtrado.  
  
 Tenga en cuenta que si crea la **DataView** con el constructor que no toma ningún argumento, no podrá utilizar la **DataView** hasta que no establezca la propiedad **Table**.  
  
 En el ejemplo de código siguiente se muestra cómo crear una **DataView** con el constructor **DataView**.  Con la **DataTable** se suministran un **RowFilter**, una columna **Sort** y un **DataViewRowState**.  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],   
    "Country = 'USA'",   
    "ContactName",   
    DataViewRowState.CurrentRows);  
```  
  
 En el siguiente ejemplo de código se muestra cómo obtener una referencia a la **DataView** predeterminada de una **DataTable** mediante la propiedad **DefaultView** de la tabla.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## Vea también  
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataView>   
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [Ordenar y filtrar datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)