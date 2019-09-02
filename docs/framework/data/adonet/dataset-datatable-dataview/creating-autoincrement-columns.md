---
title: Crear columnas de incremento automático
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 2548ad9382b406978dac0a3d366207626278f501
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205138"
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
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
