---
title: Crear un objeto DataView
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1a8529c317025dbabd9c7467557b244b2f452a77
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="creating-a-dataview"></a>Crear un objeto DataView
Hay dos formas de crear una <xref:System.Data.DataView>. Puede usar el **DataView** constructor, o puede crear una referencia a la <xref:System.Data.DataTable.DefaultView%2A> propiedad de la <xref:System.Data.DataTable>. El **DataView** constructor puede estar vacío o puede aceptar también un **DataTable** como un argumento único, o un **DataTable** junto con los criterios de filtro, criterios de ordenación y una fila filtro de estado. Para obtener más información acerca de los argumentos adicionales disponibles para su uso con el **DataView**, consulte [ordenar y filtrar datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
 Dado que el índice de un **DataView** se compila cuando el **DataView** se crea y cuando se da alguna de la **ordenación**, **RowFilter**, o  **RowStateFilter** se modifican propiedades, conseguirá un rendimiento óptimo suministra cualquier criterio inicial de ordenación o criterios de filtrado como argumentos del constructor al crear el **DataView**. Crear un **DataView** sin especificar el criterio de ordenación o filtro y, a continuación, establecer el **ordenación**, **RowFilter**, o **RowStateFilter** propiedades más adelante hace que el índice que se crea al menos dos veces: una vez cuando el **DataView** se crea, y otra cuando cualquiera de las propiedades de ordenación o filtro se modifica.  
  
 Tenga en cuenta que si crea un **DataView** utilizando el constructor que no toma ningún argumento, no podrá usar la **DataView** hasta que haya establecido la **tabla** propiedad .  
  
 En el ejemplo de código siguiente se muestra cómo crear un **DataView** mediante la **DataView** constructor. A **RowFilter**, **ordenación** columna, y **DataViewRowState** se suministran junto con el **DataTable**.  
  
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
  
 En el ejemplo de código siguiente se muestra cómo obtener una referencia a la predeterminada **DataView** de un **DataTable** mediante la **DefaultView** propiedad de la tabla.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [Objetos DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Ordenación y filtrado de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 [Objetos DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
