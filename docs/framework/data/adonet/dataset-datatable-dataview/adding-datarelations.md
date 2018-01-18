---
title: Agregar objetos DataRelation
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
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4650ccc5324489fb5c577cf2542ae95e1904441a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="adding-datarelations"></a>Agregar objetos DataRelation
En un <xref:System.Data.DataSet> que contiene varios objetos <xref:System.Data.DataTable>, es posible utilizar objetos <xref:System.Data.DataRelation> para relacionar una tabla con otra, navegar por las tablas y devolver filas secundarias o primarias de una tabla relacionada.  
  
 Los argumentos necesarios para crear un **DataRelation** son un nombre para el **DataRelation** va a crear y una matriz de uno o varios <xref:System.Data.DataColumn> referencias a las columnas que actúan como primarios y secundarios columnas de la relación. Después de haber creado un **DataRelation**, puede usar para navegar por las tablas y recuperar valores.  
  
 Agregar un **DataRelation** a una <xref:System.Data.DataSet> agrega de forma predeterminada, un <xref:System.Data.UniqueConstraint> a la tabla primaria y una <xref:System.Data.ForeignKeyConstraint> a la tabla secundaria. Para obtener más información acerca de estas restricciones predeterminadas, vea [restricciones de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 En el ejemplo de código siguiente se crea un **DataRelation** con dos <xref:System.Data.DataTable> objetos en un <xref:System.Data.DataSet>. Cada <xref:System.Data.DataTable> contiene una columna denominada **CustID**, que actúa como un vínculo entre los dos <xref:System.Data.DataTable> objetos. En el ejemplo se agrega una sola **DataRelation** a la **relaciones** colección de la <xref:System.Data.DataSet>. El primer argumento del ejemplo especifica el nombre de la **DataRelation** va a crear. El segundo argumento establece el elemento primario **DataColumn** y el tercer argumento establece el elemento secundario **DataColumn**.  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 A **DataRelation** también tiene un **Nested** propiedad que, cuando se establece en **true**, hace que las filas de la tabla secundaria se anidan dentro de la fila asociada de la tabla primaria Cuando se escriben como elementos XML mediante <xref:System.Data.DataSet.WriteXml%2A> . Para obtener más información, vea [Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md) (Usar XML en un conjunto de datos).  
  
## <a name="see-also"></a>Vea también  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
