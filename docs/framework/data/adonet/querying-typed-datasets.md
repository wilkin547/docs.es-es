---
title: Consultar objetos DataSet con tipo
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: d956fd5f07c108146d20623bcf811266380c132c
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44270649"
---
# <a name="query-typed-datasets"></a>Consultar objetos DataSet con tipo

Si el esquema de la <xref:System.Data.DataSet> se conoce en tiempo de diseño de la aplicación, se recomienda que use un tipo <xref:System.Data.DataSet> al usar LINQ to DataSet. Un tipo <xref:System.Data.DataSet> es una clase que deriva de un <xref:System.Data.DataSet>. Como tal, hereda todos los métodos, eventos y propiedades de un <xref:System.Data.DataSet>. Además, un tipo <xref:System.Data.DataSet> proporciona propiedades, eventos y métodos fuertemente tipados. Esto significa que se puede tener acceso a tablas y columnas por su nombre, en lugar de utilizar métodos de una colección. Esto hace que las consultas sean más sencillas y más legibles. Para obtener más información, consulte [DataSets con tipo](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).

LINQ to DataSet también admite consultas a través de un tipo <xref:System.Data.DataSet>. Con un tipo <xref:System.Data.DataSet>, no es necesario usar el tipo genérico <xref:System.Data.DataRowExtensions.Field%2A> método o <xref:System.Data.DataRowExtensions.SetField%2A> método para acceder a los datos de columna. Los nombres de propiedad están disponibles en tiempo de compilación porque la información de tipo se incluye en el <xref:System.Data.DataSet>. LINQ to DataSet proporciona acceso a los valores de columna del tipo correcto, por lo que se detectan errores de coincidencia de tipo cuando se compila el código en lugar de en tiempo de ejecución.

Antes de poder empezar a consultar con tipo <xref:System.Data.DataSet>, debe generar la clase mediante el **Diseñador de DataSet** en Visual Studio. Para obtener más información, consulte [crear y configurar conjuntos de datos](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se muestra una consulta sobre un <xref:System.Data.DataSet> con tipo:

```csharp
var query = from o in orders
            where o.OnlineOrderFlag == true
            select new { o.SalesOrderID,
                         o.OrderDate,
                         o.SalesOrderNumber };

foreach(var order in query)
{
    Console.WriteLine("{0}\t{1:d}\t{2}",
      order.SalesOrderID,
      order.OrderDate,
      order.SalesOrderNumber);
}
```

```vb
Dim orders = ds.Tables("SalesOrderHeader")

Dim query = _
       From o In orders _
       Where o.OnlineOrderFlag = True _
       Select New {SalesOrderID := o.SalesOrderID, _
                   OrderDate := o.OrderDate, _
                   SalesOrderNumber := o.SalesOrderNumber}

For Each Dim onlineOrder In query
 Console.WriteLine("{0}\t{1:d}\t{2}", _
 onlineOrder.SalesOrderID, _
 onlineOrder.OrderDate, _
 onlineOrder.SalesOrderNumber)
Next
```

## <a name="see-also"></a>Vea también

- [Consulta de conjuntos de datos](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [Consultas entre tablas](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)
- [Consultas de tabla única](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
