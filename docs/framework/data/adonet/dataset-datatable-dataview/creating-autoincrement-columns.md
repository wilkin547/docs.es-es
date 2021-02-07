---
description: Más información acerca de cómo crear columnas de incremento automático
title: Crear columnas de incremento automático
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 7568b1013b7af5aef7a6fc1f28dc163a082743a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739643"
---
# <a name="creating-autoincrement-columns"></a>Crear columnas de incremento automático

Para garantizar que los valores de una columna son únicos, éstos se pueden establecer de manera que se incrementen automáticamente cuando se agregan filas a la tabla. Para crear un incremento automático <xref:System.Data.DataColumn> , establezca la <xref:System.Data.DataColumn.AutoIncrement%2A> propiedad de la columna en **true**. <xref:System.Data.DataColumn>A continuación, comienza con el valor definido en la <xref:System.Data.DataColumn.AutoIncrementSeed%2A> propiedad y, con cada fila agregada, el valor de la columna **incremento automático** aumenta según el valor definido en la <xref:System.Data.DataColumn.AutoIncrementStep%2A> propiedad de la columna.  
  
 En el caso de las columnas de **incremento automático** , se recomienda <xref:System.Data.DataColumn.ReadOnly%2A> establecer la propiedad de **DataColumn** en **true**.  
  
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
- [Información general de ADO.NET](../ado-net-overview.md)
