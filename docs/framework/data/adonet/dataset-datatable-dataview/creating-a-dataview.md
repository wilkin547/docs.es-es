---
title: Crear un objeto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: b88df66ef2e065d1db8d4033eb1fb0e47ebdd189
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47108720"
---
# <a name="creating-a-dataview"></a>Crear un objeto DataView
Hay dos formas de crear una <xref:System.Data.DataView>. Puede usar el **DataView** constructor, o bien puede crear una referencia a la <xref:System.Data.DataTable.DefaultView%2A> propiedad de la <xref:System.Data.DataTable>. El **DataView** constructor puede estar vacío o puede aceptar también una **DataTable** como un solo argumento, o un **DataTable** junto con los criterios de filtro, los criterios de ordenación y una fila filtro de estado. Para obtener más información acerca de los argumentos adicionales disponibles para su uso con el **DataView**, consulte [ordenar y filtrar datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
 Porque el índice para un **DataView** se compila cuando la **DataView** se crea y cuando cualquiera de los **ordenación**, **RowFilter**, o  **RowStateFilter** se modifican las propiedades, lograr el mejor rendimiento suministra cualquier criterio de ordenación inicial o criterios de filtro como argumentos de constructor al crear el **DataView**. Creación de un **DataView** sin especificar el criterio de ordenación o filtro y, a continuación, establecer el **ordenación**, **RowFilter**, o **RowStateFilter** las propiedades más adelante hace que el índice que se crea al menos dos veces: una vez cuando el **DataView** se crea, y vuelva a cualquiera de las propiedades de ordenación o filtro se modificó.  
  
 Tenga en cuenta que si crea un **DataView** utilizando el constructor que no toma ningún argumento, no podrá usar el **DataView** hasta que haya establecido el **tabla** propiedad .  
  
 En el ejemplo de código siguiente se muestra cómo crear un **DataView** utilizando el **DataView** constructor. Un **RowFilter**, **ordenación** columna, y **DataViewRowState** se suministran junto con el **DataTable**.  
  
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
  
 En el ejemplo de código siguiente se muestra cómo obtener una referencia al valor predeterminado **DataView** de un **DataTable** utilizando el **DefaultView** propiedad de la tabla.  
  
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
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
