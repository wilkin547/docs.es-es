---
description: Más información sobre cómo navegar por los objetos DataRelation
title: Navegar por objetos DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: 72d5bbb282b3b43434e528390769e1203519e8e2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651813"
---
# <a name="navigating-datarelations"></a>Navegar por objetos DataRelation

Una de las principales funciones de una <xref:System.Data.DataRelation> es permitir la navegación de una <xref:System.Data.DataTable> a otra dentro de un <xref:System.Data.DataSet>. Esto permite recuperar todos los <xref:System.Data.DataRow> objetos relacionados en un **objeto DataTable** cuando se proporciona una única **DataRow** desde un **DataTable** relacionado. Por ejemplo, después de establecer una **DataRelation** entre una tabla de clientes y una tabla de pedidos, puede recuperar todas las filas de pedidos de una fila de cliente determinada mediante **GetChildRows**.  
  
 En el ejemplo de código siguiente se crea una **DataRelation** entre la tabla **Customers** y la tabla **Orders** de un **DataSet** y se devuelven todos los pedidos de cada cliente.  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 El ejemplo siguiente se basa en el anterior; se relacionan cuatro tablas y se navega por dichas relaciones. Como en el ejemplo anterior, **CustomerID** relaciona la tabla **Customers** con la tabla **Orders** . Para cada cliente de la tabla **Customers** , se determinan todas las filas secundarias de la tabla **Orders** , con el fin de devolver el número de pedidos que tiene un cliente determinado y sus valores **OrderID** .  
  
 El ejemplo expandido también devuelve los valores de las tablas **OrderDetails** y **Products** . La tabla **Orders** está relacionada con la tabla **OrderDetails** mediante **OrderID** para determinar, para cada pedido de cliente, qué productos y cantidades se han pedido. Dado que la tabla **OrderDetails** solo contiene el **ProductID** de un producto pedido, **OrderDetails** se relaciona con los **productos** que usan **ProductID** para devolver el **NombreProducto**. En esta relación, la tabla **Products** es el elemento primario y la tabla **Order Details** es el elemento secundario. Como resultado, al recorrer en iteración la tabla **OrderDetails** , se llama a **GetParentRow** para recuperar el valor **ProductName** relacionado.  
  
 Tenga en cuenta que cuando se crea la **DataRelation** para las tablas **Customers** y **Orders** , no se especifica ningún valor para la marca **createConstraints** (el valor predeterminado es **true**). Se supone que todas las filas de la tabla **Orders** tienen un valor **CustomerID** que existe en la tabla primaria **Customers** . Si existe un **CustomerID** en la tabla **Orders** que no existe en la tabla **Customers** , <xref:System.Data.ForeignKeyConstraint> se produce una excepción.  
  
 Cuando la columna secundaria pueda contener valores que no contenga la columna primaria, establezca el marcador **createConstraints** en **false** al agregar la **DataRelation**. En el ejemplo, el marcador **createConstraints** se establece en **false** para la **DataRelation** entre la tabla **Orders** y la tabla **OrderDetails** . Esto permite que la aplicación devuelva todos los registros de la tabla **OrderDetails** y solo un subconjunto de registros de la tabla **Orders** sin generar una excepción en tiempo de ejecución. El ejemplo ampliado genera el resultado con el siguiente formato.  
  
```output  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 El siguiente ejemplo de código es un ejemplo ampliado en el que se devuelven los valores de las tablas **OrderDetails** y **Products** , con solo un subconjunto de los registros de la tabla **Orders** que se devuelve.  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
