---
title: Crear un objeto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 9d21b17068ff3ce5b0bd3990144383d7f9ded2f9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151343"
---
# <a name="creating-a-dataview"></a>Crear un objeto DataView
Hay dos formas de crear una <xref:System.Data.DataView>. Puede usar el **dataView** constructor, o puede <xref:System.Data.DataTable.DefaultView%2A> crear una <xref:System.Data.DataTable>referencia a la propiedad de la . El **DataView** constructor puede estar vacío, o puede tomar un **DataTable** como un único argumento, o un **DataTable** junto con criterios de filtro, criterios de ordenación y un filtro de estado de fila. Para obtener más información acerca de los argumentos adicionales disponibles para su uso con **DataView**, vea [Ordenar y filtrar datos](sorting-and-filtering-data.md).  
  
 Dado que el índice de un **DataView** se compila tanto cuando se crea **DataView** como cuando se modifica cualquiera de las propiedades **Sort**, **RowFilter**o **RowStateFilter,** se logra el mejor rendimiento proporcionando cualquier criterio de ordenación inicial o criterio de filtrado como argumentos de constructor al crear **DataView**. Crear un **DataView** sin especificar criterios de ordenación o filtro y, a continuación, establecer el **Sort**, **RowFilter**, o **RowStateFilter** propiedades más adelante hace que el índice se cree al menos dos veces: una vez cuando se crea el **DataView** y otra vez cuando se modifica cualquiera de las propiedades de ordenación o filtro.  
  
 Tenga en cuenta que si crea un **DataView** mediante el constructor que no toma ningún argumento, no podrá usar el **DataView** hasta que haya establecido el **Table** propiedad.  
  
 En el ejemplo de código siguiente se muestra cómo crear un **DataView** mediante el **DataView** constructor. Un **RowFilter**, **Sort** columna y **DataViewRowState** se proporcionan junto con el **DataTable**.  
  
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
  
 En el ejemplo de código siguiente se muestra cómo obtener una referencia a la **predeterminada DataView** de un **DataTable** mediante el **DefaultView** propiedad de la tabla.  
  
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
- [Ordenación y filtrado de datos](sorting-and-filtering-data.md)
- [Objetos DataTable](datatables.md)
- [Información general de ADO.NET](../ado-net-overview.md)
