---
description: 'Más información acerca de: consultar conjuntos de DataSet con tipo'
title: Consultar objetos DataSet con tipo
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: 5bcf8bb587a0ed0eaca1bbe9b3a7d7143757780e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723704"
---
# <a name="query-typed-datasets"></a>Consultar conjuntos de DataSet con tipo

Si el esquema de <xref:System.Data.DataSet> se conoce en tiempo de diseño de la aplicación, se recomienda usar un tipo cuando se use <xref:System.Data.DataSet> LINQ to DataSet. Un con tipo <xref:System.Data.DataSet> es una clase que se deriva de <xref:System.Data.DataSet> . Como tal, hereda todos los métodos, eventos y propiedades de un <xref:System.Data.DataSet>. Además, un con tipo <xref:System.Data.DataSet> proporciona métodos, eventos y propiedades fuertemente tipados. Esto significa que se puede tener acceso a tablas y columnas por su nombre, en lugar de utilizar métodos de una colección. Esto hace que las consultas sean más sencillas y más legibles. Para obtener más información, vea conjuntos de datos [con tipo](./dataset-datatable-dataview/typed-datasets.md).

LINQ to DataSet también admite la consulta en un tipo <xref:System.Data.DataSet> . Con un tipo <xref:System.Data.DataSet> , no es necesario utilizar el método o método genérico <xref:System.Data.DataRowExtensions.Field%2A> <xref:System.Data.DataRowExtensions.SetField%2A> para tener acceso a los datos de la columna. Los nombres de propiedad están disponibles en tiempo de compilación porque la información de tipo se incluye en <xref:System.Data.DataSet> . LINQ to DataSet proporciona acceso a los valores de columna como tipo correcto, de modo que los errores de coincidencia de tipos se detectan cuando se compila el código en lugar de en tiempo de ejecución.

Antes de poder empezar a consultar un tipo <xref:System.Data.DataSet> , debe generar la clase mediante el **Diseñador de DataSet** en Visual Studio. Para obtener más información, vea [crear y configurar conjuntos](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio)de datos.

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

- [Consulta de conjuntos de datos](querying-datasets-linq-to-dataset.md)
- [Consultas entre tablas](cross-table-queries-linq-to-dataset.md)
- [Consultas de tabla única](single-table-queries-linq-to-dataset.md)
