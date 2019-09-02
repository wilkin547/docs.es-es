---
title: Definir claves principales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: dbfd8a8b207c0da9403ac1f8ab36557c4abe383b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204912"
---
# <a name="defining-primary-keys"></a>Definir claves principales
Generalmente, una tabla de base de datos tiene una columna o grupo de columnas que identifican de manera exclusiva cada fila de la tabla. Esta columna o grupo de columnas de identificación se denomina clave principal.  
  
 Al identificar un único <xref:System.Data.DataColumn> <xref:System.Data.DataTable> <xref:System.Data.DataColumn.Unique%2A> <xref:System.Data.DataColumn.AllowDBNull%2A>como para, la tabla establece automáticamente la propiedad de la columna en false y la propiedad en true. <xref:System.Data.DataTable.PrimaryKey%2A> En el caso de las claves principales de varias columnas, solo la propiedad **AllowDBNull** se establece automáticamente en **false**.  
  
 La propiedad **PrimaryKey** de una <xref:System.Data.DataTable> recibe como valor una matriz de uno o más objetos **DataColumn** , como se muestra en los ejemplos siguientes. En el primer ejemplo se define una sola columna como clave principal.  
  
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

- <xref:System.Data.DataTable>
- [Definición del esquema de DataTable](datatable-schema-definition.md)
- [Objetos DataTable](datatables.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
