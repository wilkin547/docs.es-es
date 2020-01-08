---
title: Ordenar con DataView (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 885b3b7b-51c1-42b3-bb29-b925f4f69a6f
ms.openlocfilehash: 2998de7dee34f9b5410bfe53988e0b7cfa797784
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634760"
---
# <a name="sorting-with-dataview-linq-to-dataset"></a>Ordenar con DataView (LINQ to DataSet)
La capacidad de ordenar datos basándose en criterios específicos y, a continuación, presentarlos a un cliente mediante un control de interfaz de usuario es un aspecto importante del enlace de datos. <xref:System.Data.DataView> proporciona varias maneras de ordenar datos y devolver filas de datos ordenados según criterios de ordenación específicos. Además de las funcionalidades de ordenación basada en cadena, <xref:System.Data.DataView> también permite usar expresiones LINQ (Language Integrated Query) para los criterios de ordenación. Las expresiones LINQ permiten operaciones de ordenación mucho más complejas y eficaces que la ordenación basada en cadena. En este tema se describen ambos enfoques de ordenación utilizando <xref:System.Data.DataView>.  
  
## <a name="creating-dataview-from-a-query-with-sorting-information"></a>Crear DataView desde una consulta con información de ordenación  
 Se puede crear un objeto <xref:System.Data.DataView> a partir de una consulta de LINQ to DataSet. Si esa consulta contiene una cláusula <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.ThenBy%2A>o <xref:System.Linq.Enumerable.ThenByDescending%2A>, las expresiones de estas cláusulas se utilizan como base para ordenar los datos de la <xref:System.Data.DataView>. Por ejemplo, si la consulta contiene las cláusulas `Order By…`y `Then By…`, el <xref:System.Data.DataView> resultante ordenará los datos por ambas columnas especificadas.  
  
 La ordenación basada en expresión es más eficaz y compleja que la simple ordenación basada en cadena. Observe que la ordenación basada en cadena y expresión se excluyen mutuamente. Cuando el <xref:System.Data.DataView.Sort%2A> basado en cadena se establece después de haber creado <xref:System.Data.DataView> desde una consulta, el filtro basado en expresión inferido a partir de la consulta se borra y no se puede volver a restablecer.  
  
 El índice de <xref:System.Data.DataView> se compila cuando se crea <xref:System.Data.DataView> y cuando se modifica cualquier información de filtro u ordenación. Para obtener el mejor rendimiento, proporcione criterios de ordenación en la consulta LINQ to DataSet en la que se crea el <xref:System.Data.DataView> y sin modificar la información de ordenación, más adelante. Para obtener más información, vea [rendimiento de DataView](dataview-performance.md).  
  
> [!NOTE]
> En la mayor parte de los casos, las expresiones utilizadas en la ordenación no deben tener efectos secundarios y deben ser deterministas. Además, las expresiones no deben tener ninguna lógica que dependa de un número de conjunto de ejecuciones, porque las operaciones de ordenación se pueden ejecutar un número ilimitado de veces.  
  
### <a name="example"></a>Ejemplo  
 El siguiente ejemplo consulta en la tabla SalesOrderHeader y ordena las filas devueltas por fecha de pedido; crea un <xref:System.Data.DataView> desde una consulta y enlaza <xref:System.Data.DataView> a un <xref:System.Windows.Forms.BindingSource>:  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby)]  
  
### <a name="example"></a>Ejemplo  
 El siguiente ejemplo consulta en la tabla SalesOrderHeader y ordena la fila devuelta por el importe total a pagar; crea un <xref:System.Data.DataView> desde una consulta y enlaza <xref:System.Data.DataView> a un <xref:System.Windows.Forms.BindingSource>:  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby2)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby2)]  
  
### <a name="example"></a>Ejemplo  
 El siguiente ejemplo consulta en la tabla SalesOrderDetail y ordena las filas devueltas por cantidad de pedido y, a continuación, por id. del pedido de ventas; crea un <xref:System.Data.DataView> desde una consulta y enlaza <xref:System.Data.DataView> a un <xref:System.Windows.Forms.BindingSource>:  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderbythenby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderbythenby)]  
  
## <a name="using-the-string-based-sort-property"></a>Utilizar la propiedad Sort basada en cadena  
 La funcionalidad de ordenación basada en cadena de <xref:System.Data.DataView> sigue funcionando con LINQ to DataSet. Después de crear una <xref:System.Data.DataView> a partir de una consulta de LINQ to DataSet, puede utilizar la propiedad <xref:System.Data.DataView.Sort%2A> para establecer la ordenación en el <xref:System.Data.DataView>.  
  
 Las funcionalidades de ordenación basada en cadena y expresión se excluyen mutuamente. Al establecer la propiedad <xref:System.Data.DataView.Sort%2A> se borrará la ordenación basada en expresión heredada de la consulta a partir de la que se ha creado <xref:System.Data.DataView>.  
  
 Para obtener más información sobre el filtrado de <xref:System.Data.DataView.Sort%2A> basado en cadenas, vea [ordenar y filtrar datos](./dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
### <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea <xref:System.Data.DataView> a partir de la tabla Contact y ordena las filas por apellido en orden descendente y luego por nombres en orden ascendente:  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
### <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se consultan los apellidos que empiezan por la letra "S" en la tabla Contact.  Se crea una clase <xref:System.Data.DataView> a partir de dicha consulta y se enlaza a un objeto <xref:System.Windows.Forms.BindingSource>.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## <a name="clearing-the-sort"></a>Borrar la ordenación  
 Se puede borrar la información de ordenación de <xref:System.Data.DataView> después de haberla establecido mediante la propiedad <xref:System.Data.DataView.Sort%2A>. Hay dos formas de borrar información de ordenación en <xref:System.Data.DataView>:  
  
- Establezca la propiedad <xref:System.Data.DataView.Sort%2A> en `null`.  
  
- Establecer la propiedad <xref:System.Data.DataView.Sort%2A> en una cadena vacía.  
  
### <a name="example"></a>Ejemplo  
 El siguiente ejemplo crea un <xref:System.Data.DataView> desde una consulta y borra la ordenación mediante el establecimiento de la propiedad <xref:System.Data.DataView.Sort%2A> en una cadena vacía:  
  
 [!code-csharp[DP DataView Samples#LDVClearSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort)]
 [!code-vb[DP DataView Samples#LDVClearSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort)]  
  
### <a name="example"></a>Ejemplo  
 El siguiente ejemplo crea un <xref:System.Data.DataView> desde la tabla Contact y establece la propiedad <xref:System.Data.DataView.Sort%2A> para ordenar por apellidos en orden descendente. A continuación, la información de ordenación se borra estableciendo la propiedad <xref:System.Data.DataView.Sort%2A> en `null`:  
  
 [!code-csharp[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort2)]
 [!code-vb[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort2)]  
  
## <a name="see-also"></a>Vea también

- [Enlace de datos y LINQ to DataSet](data-binding-and-linq-to-dataset.md)
- [Filtrado con DataView](filtering-with-dataview-linq-to-dataset.md)
- [Ordenación de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546145(v=vs.120))
