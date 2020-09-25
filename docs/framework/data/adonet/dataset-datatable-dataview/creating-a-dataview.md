---
title: Crear un objeto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 539e9763c8aa4affdb6f3bd219a99dbca50cee01
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202348"
---
# <a name="creating-a-dataview"></a>Crear un objeto DataView

Hay dos formas de crear una <xref:System.Data.DataView>. Puede usar el constructor **DataView** o puede crear una referencia a la <xref:System.Data.DataTable.DefaultView%2A> propiedad de <xref:System.Data.DataTable> . El constructor de **DataView** puede estar vacío o puede tomar un **DataTable** como un solo argumento, o un **DataTable** junto con criterios de filtro, criterios de ordenación y un filtro de estado de fila. Para obtener más información sobre los argumentos adicionales disponibles para su uso con **DataView**, vea [ordenar y filtrar datos](sorting-and-filtering-data.md).  
  
 Dado que el índice de un objeto **DataView** se genera cuando se crea la **DataView** y cuando se modifica cualquiera de las propiedades **Sort**, **RowFilter**o **RowStateFilter** , se obtiene el mejor rendimiento al proporcionar cualquier criterio de ordenación inicial o criterio de filtrado como argumentos del constructor al crear la **DataView**. La creación de una **DataView** sin especificar criterios de ordenación o de filtro y, después, el establecimiento de las propiedades **Sort**, **RowFilter**o **RowStateFilter** , hace que el índice se compile al menos dos veces: una vez cuando se crea la **DataView** y otra vez cuando se modifica cualquiera de las propiedades de ordenación o filtro.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [Objetos DataView](dataviews.md)
- [Ordenar y filtrar datos](sorting-and-filtering-data.md)
- [Objetos DataTable](datatables.md)
- [Información general de ADO.NET](../ado-net-overview.md)
