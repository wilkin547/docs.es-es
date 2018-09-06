---
title: Navegar por objetos DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: 1819d468d12c03ce0c4faac11f4b20b8fe0f9c33
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43731279"
---
# <a name="navigating-datarelations"></a>Navegar por objetos DataRelation
Una de las principales funciones de una <xref:System.Data.DataRelation> es permitir la navegación de una <xref:System.Data.DataTable> a otra dentro de un <xref:System.Data.DataSet>. Esto le permite recuperar todos relacionado <xref:System.Data.DataRow> objetos en una **DataTable** cuando se especifica una sola **DataRow** desde un relacionados **DataTable**. Por ejemplo, después de establecer un **DataRelation** entre una tabla de clientes y una tabla de pedidos, puede recuperar todas las filas de pedido para un cliente determinado de filas mediante **GetChildRows**.  
  
 En el ejemplo de código siguiente se crea un **DataRelation** entre el **clientes** tabla y el **pedidos** tabla de un **DataSet** y devuelve todos los pedidos de cada cliente.  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 El ejemplo siguiente se basa en el anterior; se relacionan cuatro tablas y se navega por dichas relaciones. Como se muestra en el ejemplo anterior, **CustomerID** se relaciona con la **clientes** la tabla a la **pedidos** tabla. Para cada cliente en el **clientes** de tabla, todas las filas secundarias en el **pedidos** se determinan la tabla, con el fin de devolver el número de pedidos que tiene un cliente concreto y sus **OrderID** valores.  
  
 El ejemplo ampliado también devuelve los valores de la **OrderDetails** y **productos** tablas. El **pedidos** tabla se relaciona con la **OrderDetails** tabla mediante **OrderID** para determinar, para cada pedido de cliente, qué productos y cantidades se pidieron. Dado que el **OrderDetails** tabla sólo contiene el **ProductID** de un producto pedido, **OrderDetails** está relacionado con **productos** uso de **ProductID** con el fin de devolver el **ProductName**. En esta relación, el **productos** es la tabla primaria y la **Order Details** tabla es el elemento secundario. Como resultado, al recorrer en iteración el **OrderDetails** tabla, **GetParentRow** se llama para recuperar el relacionados **ProductName** valor.  
  
 Tenga en cuenta que, cuando el **DataRelation** se crea para el **clientes** y **pedidos** tablas, se especifica ningún valor para el **createConstraints**marca (el valor predeterminado es **true**). Se supone que todas las filas de la **pedidos** tabla tiene un **CustomerID** valor que existe en el elemento primario **clientes** tabla. Si un **CustomerID** existe en el **pedidos** tabla que no existe en el **clientes** tabla, un <xref:System.Data.ForeignKeyConstraint> hace que se produzca una excepción.  
  
 Cuando la columna secundaria pueda contener valores que no contiene la columna primaria, establezca la **createConstraints** marca **false** al agregar el **DataRelation**. En el ejemplo, el **createConstraints** marca se establece en **false** para el **DataRelation** entre el **pedidos** tabla y el  **OrderDetails** tabla. Esto permite que la aplicación devolver todos los registros de la **OrderDetails** tabla y solo un subconjunto de registros desde el **pedidos** tabla sin generar una excepción en tiempo de ejecución. El ejemplo ampliado genera el resultado con el siguiente formato.  
  
```  
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
  
 El ejemplo de código siguiente es un ejemplo ampliado donde los valores de la **OrderDetails** y **productos** se devuelven las tablas, con solo un subconjunto de los registros de la **pedidos**tabla que se va a devolver.  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
