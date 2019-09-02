---
title: Agregar objetos DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: fde1e2ace09e31234d199876ae7f063e01e7a7e4
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203971"
---
# <a name="adding-datarelations"></a>Agregar objetos DataRelation
En un <xref:System.Data.DataSet> que contiene varios objetos <xref:System.Data.DataTable>, es posible utilizar objetos <xref:System.Data.DataRelation> para relacionar una tabla con otra, navegar por las tablas y devolver filas secundarias o primarias de una tabla relacionada.  
  
 Los argumentos necesarios para crear una **DataRelation** son un nombre para la **DataRelation** que se va a crear y una matriz de una o varias <xref:System.Data.DataColumn> referencias a las columnas que actúan como columnas primarias y secundarias de la relación. Después de crear una **DataRelation**, puede usarla para desplazarse entre las tablas y recuperar los valores.  
  
 Agregar una **DataRelation** a <xref:System.Data.DataSet> agrega, <xref:System.Data.UniqueConstraint> de forma predeterminada, a la tabla primaria y <xref:System.Data.ForeignKeyConstraint> a la tabla secundaria. Para obtener más información sobre estas restricciones predeterminadas, consulte [restricciones de DataTable](datatable-constraints.md).  
  
 En el ejemplo de código siguiente se crea una DataRelation <xref:System.Data.DataTable> con dos objetos <xref:System.Data.DataSet>en un. Cada <xref:System.Data.DataTable> contiene una columna denominada **CustID**, que actúa como un vínculo entre los dos <xref:System.Data.DataTable> objetos. En el ejemplo se agrega una única **DataRelation** a la <xref:System.Data.DataSet>colección Relations de. El primer argumento del ejemplo especifica el nombre de la **DataRelation** que se va a crear. El segundo argumento establece la **DataColumn** primaria y el tercer argumento establece la **DataColumn**secundaria.  
  
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
  
 Una **DataRelation** también tiene una propiedad **anidada** que, cuando se establece en **true**, hace que las filas de la tabla secundaria se aniden dentro de la fila asociada de la tabla primaria cuando se escriben como elementos <xref:System.Data.DataSet.WriteXml%2A> XML mediante. Para obtener más información, vea [Using XML in a DataSet](using-xml-in-a-dataset.md) (Usar XML en un conjunto de datos).  
  
## <a name="see-also"></a>Vea también

- [Objetos DataSet, DataTable y DataView](index.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
