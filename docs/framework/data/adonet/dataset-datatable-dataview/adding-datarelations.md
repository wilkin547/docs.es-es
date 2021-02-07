---
description: Más información sobre cómo agregar objetos DataRelation
title: Agregar objetos DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 56438c9b69fab71c4843582b6cfea50fa057eb44
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725225"
---
# <a name="adding-datarelations"></a>Agregar objetos DataRelation

En un <xref:System.Data.DataSet> que contiene varios objetos <xref:System.Data.DataTable>, es posible utilizar objetos <xref:System.Data.DataRelation> para relacionar una tabla con otra, navegar por las tablas y devolver filas secundarias o primarias de una tabla relacionada.  
  
 Los argumentos necesarios para crear una **DataRelation** son un nombre para la **DataRelation** que se va a crear y una matriz de una o varias <xref:System.Data.DataColumn> referencias a las columnas que actúan como columnas primarias y secundarias de la relación. Después de crear una **DataRelation**, puede usarla para desplazarse entre las tablas y recuperar los valores.  
  
 Agregar una **DataRelation** a <xref:System.Data.DataSet> agrega, de forma predeterminada, <xref:System.Data.UniqueConstraint> a la tabla primaria y <xref:System.Data.ForeignKeyConstraint> a la tabla secundaria. Para obtener más información sobre estas restricciones predeterminadas, consulte [restricciones de DataTable](datatable-constraints.md).  
  
 En el ejemplo de código siguiente se crea una **DataRelation** con dos <xref:System.Data.DataTable> objetos en un <xref:System.Data.DataSet> . Cada <xref:System.Data.DataTable> contiene una columna denominada **CustID**, que actúa como un vínculo entre los dos <xref:System.Data.DataTable> objetos. En el ejemplo se agrega una única **DataRelation** a la colección **Relations** de <xref:System.Data.DataSet> . El primer argumento del ejemplo especifica el nombre de la **DataRelation** que se va a crear. El segundo argumento establece la **DataColumn** primaria y el tercer argumento establece la **DataColumn** secundaria.  
  
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
  
 Una **DataRelation** también tiene una propiedad **anidada** que, cuando se establece en **true**, hace que las filas de la tabla secundaria se aniden dentro de la fila asociada de la tabla primaria cuando se escriben como elementos XML mediante <xref:System.Data.DataSet.WriteXml%2A> . Para obtener más información, vea [Using XML in a DataSet](using-xml-in-a-dataset.md) (Usar XML en un conjunto de datos).  
  
## <a name="see-also"></a>Vea también

- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
