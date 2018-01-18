---
title: Definir claves principales
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
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: abd1dc4b515121343b2ca9674b263c327d153fad
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="defining-primary-keys"></a>Definir claves principales
Generalmente, una tabla de base de datos tiene una columna o grupo de columnas que identifican de manera exclusiva cada fila de la tabla. Esta columna o grupo de columnas de identificación se denomina clave principal.  
  
 Cuando se identifica una sola <xref:System.Data.DataColumn> como el <xref:System.Data.DataTable.PrimaryKey%2A> para un <xref:System.Data.DataTable>, establece automáticamente la tabla el <xref:System.Data.DataColumn.AllowDBNull%2A> propiedad de la columna a **false** y la <xref:System.Data.DataColumn.Unique%2A> propiedad  **True**. Para varias columnas las claves principales, solo el **AllowDBNull** propiedad se establece automáticamente en **false**.  
  
 El **PrimaryKey** propiedad de un <xref:System.Data.DataTable> recibe como valor una matriz de uno o varios **DataColumn** objetos, como se muestra en los ejemplos siguientes. En el primer ejemplo se define una sola columna como clave principal.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustID")}  
  
' Or  
  
Dim columns(1) As DataColumn  
columns(0) = workTable.Columns("CustID")  
workTable.PrimaryKey = columns  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustID"]};  
  
// Or  
  
DataColumn[] columns = new DataColumn[1];  
columns[0] = workTable.Columns["CustID"];  
workTable.PrimaryKey = columns;  
```  
  
 En el siguiente ejemplo se definen dos columnas como clave principal.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustLName"), _  
                                         workTable.Columns("CustFName")}  
  
' Or  
  
Dim keyColumn(2) As DataColumn  
keyColumn(0) = workTable.Columns("CustLName")  
keyColumn(1) = workTable.Columns("CustFName")  
workTable.PrimaryKey = keyColumn  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustLName"],   
                                         workTable.Columns["CustFName"]};  
  
// Or  
  
DataColumn[] keyColumn = new DataColumn[2];  
keyColumn[0] = workTable.Columns["CustLName"];  
keyColumn[1] = workTable.Columns["CustFName"];  
workTable.PrimaryKey = keyColumn;  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Data.DataTable>  
 [Definición del esquema de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [Objetos DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
