---
title: Consultar objetos DataSet con tipo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: 30a6512202615590a4b399b8ce7173b213a8873c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="querying-typed-datasets"></a>Consultar objetos DataSet con tipo
Si el esquema de <xref:System.Data.DataSet> se conoce en tiempo de diseño de la aplicación, se recomienda usar un <xref:System.Data.DataSet> con tipo al utilizar [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Un tipo <xref:System.Data.DataSet> es una clase que deriva de un <xref:System.Data.DataSet>. Como tal, hereda todos los métodos, eventos y propiedades de un <xref:System.Data.DataSet>. Además, un tipo <xref:System.Data.DataSet> proporciona métodos fuertemente tipados, eventos y propiedades. Esto significa que se puede tener acceso a tablas y columnas por su nombre, en lugar de utilizar métodos de una colección. Esto hace que las consultas sean más sencillas y más legibles. Para obtener más información, consulte [conjuntos de datos con tipo](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] también admite las consultas en un tipo <xref:System.Data.DataSet>. Con un tipo <xref:System.Data.DataSet>, no es necesario utilizar la interfaz genérica <xref:System.Data.DataRowExtensions.Field%2A> método o <xref:System.Data.DataRowExtensions.SetField%2A> método para acceder a los datos de columna.  Los nombres de propiedad están disponibles en tiempo de compilación porque la información de tipo se incluye en el <xref:System.Data.DataSet>. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] proporciona acceso a valores de columna como tipo correcto para que los errores de falta de coincidencia de tipos se interceptan cuando se compila el código en lugar de en tiempo de ejecución.  
  
 Antes de poder empezar a consultar un <xref:System.Data.DataSet> con tipo se debe generar la clase usando el Diseñador de DataSet de [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  Para obtener más información, vea [Crear y configurar conjuntos de datos](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).  
  
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
 [Consulta de conjuntos de datos](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [Consultas entre tablas](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 [Consultas de tabla única](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
