---
title: Crear columnas de incremento automático
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 5e4a36829107480a44980c7210b39c21231c67f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786457"
---
# <a name="creating-autoincrement-columns"></a>Crear columnas de incremento automático
Para garantizar que los valores de una columna son únicos, éstos se pueden establecer de manera que se incrementen automáticamente cuando se agregan filas a la tabla. Para crear un incremento <xref:System.Data.DataColumn>automático, establezca la <xref:System.Data.DataColumn.AutoIncrement%2A> propiedad de la columna en **true**. A continuación, comienza con el valor definido en <xref:System.Data.DataColumn.AutoIncrementSeed%2A> la propiedad y, con cada fila agregada, el valor de la columna **incremento automático** aumenta según el valor <xref:System.Data.DataColumn.AutoIncrementStep%2A> definido en la propiedad de la columna. <xref:System.Data.DataColumn>  
  
 En el caso de las columnas de **incremento automático** , se recomienda establecer la <xref:System.Data.DataColumn.ReadOnly%2A> propiedad de **DataColumn** en **true**.  
  
 En el ejemplo siguiente se muestra cómo se crea una columna que comienza con un valor de 200 y va aumentando de tres en tres.  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.DataColumn>
- [Definición del esquema de DataTable](datatable-schema-definition.md)
- [Objetos DataTable](datatables.md)
- [Información general sobre ADO.NET](../ado-net-overview.md)
