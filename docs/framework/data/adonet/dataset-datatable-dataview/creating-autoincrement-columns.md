---
title: Crear columnas de incremento automático
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 99c52b93cee858511d50aba2f30f2b9f96d91ccd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090945"
---
# <a name="creating-autoincrement-columns"></a>Crear columnas de incremento automático
Para garantizar que los valores de una columna son únicos, éstos se pueden establecer de manera que se incrementen automáticamente cuando se agregan filas a la tabla. Para crear un incremento automático <xref:System.Data.DataColumn>, establezca el <xref:System.Data.DataColumn.AutoIncrement%2A> propiedad de la columna a **true**. El <xref:System.Data.DataColumn> , a continuación, se inicia con el valor definido en el <xref:System.Data.DataColumn.AutoIncrementSeed%2A> propiedad y con cada fila agregada, el valor de la **AutoIncrement** columna aumenta con el valor definido en el <xref:System.Data.DataColumn.AutoIncrementStep%2A> propiedad de la columna.  
  
 Para **AutoIncrement** columnas, se recomienda que el <xref:System.Data.DataColumn.ReadOnly%2A> propiedad de la **DataColumn** establecerse **true**.  
  
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
- [Definición del esquema de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [Objetos DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
