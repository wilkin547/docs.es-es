---
title: Crear un objeto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 391c071f19149e9690c9121b1094aef5bfa605cd
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203847"
---
# <a name="creating-a-dataview"></a>Crear un objeto DataView
Hay dos formas de crear una <xref:System.Data.DataView>. Puede usar el constructor **DataView** o puede crear una referencia a la <xref:System.Data.DataTable.DefaultView%2A> propiedad de. <xref:System.Data.DataTable> El constructor de **DataView** puede estar vacío o puede tomar un **DataTable** como un solo argumento, o un **DataTable** junto con criterios de filtro, criterios de ordenación y un filtro de estado de fila. Para obtener más información sobre los argumentos adicionales disponibles para su uso con **DataView**, vea [ordenar y filtrar datos](sorting-and-filtering-data.md).  
  
 Dado que el índice de una **DataView** se genera cuando se crea la **DataView** y cuando se modifica cualquiera de las propiedades **Sort**, **RowFilter**o **RowStateFilter** , se obtiene el mejor rendimiento al proporcionar cualquier criterio de ordenación o filtrado como argumentos del constructor al crear **DataView**. Crear una **DataView** sin especificar criterios de ordenación o de filtro y, a continuación, establecer las propiedades **Sort**, **RowFilter**o **RowStateFilter** más adelante hace que el índice se compile al menos dos veces: una vez cuando **DataView** es se crea y de nuevo cuando se modifica cualquiera de las propiedades de ordenación o filtro.  
  
 Tenga en cuenta que si crea una **DataView** con el constructor que no toma ningún argumento, no podrá usar la **DataView** hasta que haya establecido la propiedad de **tabla** .  
  
 En el ejemplo de código siguiente se muestra cómo crear una **DataView** mediante el constructor **DataView** . Se proporcionan un **RowFilter**, una columna de **ordenación** y un **DataViewRowState** junto con la **DataTable**.  
  
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
  
 En el ejemplo de código siguiente se muestra cómo obtener una referencia a la **DataView** predeterminada de un **DataTable** mediante la propiedad **DefaultView** de la tabla.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [Objetos DataView](dataviews.md)
- [Ordenación y filtrado de datos](sorting-and-filtering-data.md)
- [Objetos DataTable](datatables.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
