---
description: Más información acerca de cómo crear un objeto DataView (LINQ to DataSet)
title: Crear un objeto DataView (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76057508-e12d-4779-a707-06a4c2568acf
ms.openlocfilehash: 4261e4bf55616a56652cb111d3660210dc3f96f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663825"
---
# <a name="creating-a-dataview-object-linq-to-dataset"></a>Crear un objeto DataView (LINQ to DataSet)

Hay dos maneras de crear un <xref:System.Data.DataView> en el contexto de LINQ to DataSet. Puede crear a <xref:System.Data.DataView> partir de una consulta de LINQ to DataSet sobre un <xref:System.Data.DataTable> , o puede crearlo a partir de un tipo o sin tipo <xref:System.Data.DataTable> . En ambos casos, se crea mediante <xref:System.Data.DataView> uno de los métodos de <xref:System.Data.DataTableExtensions.AsDataView%2A> extensión; <xref:System.Data.DataView> no se puede construir directamente en el contexto de LINQ to DataSet.  
  
 Cuando se ha creado <xref:System.Data.DataView>, puede enlazarlo con un control de la interfaz de usuario en una aplicación de Windows Forms o en una aplicación ASP.NET, o cambiar la configuración de filtro y ordenación.  
  
 <xref:System.Data.DataView> construye un índice, que mejora considerablemente el rendimiento de las operaciones que pueden utilizarlo, como filtro y ordenación. El índice de <xref:System.Data.DataView> se compila cuando se crea <xref:System.Data.DataView> y cuando se modifica cualquier información de filtro u ordenación. La creación de <xref:System.Data.DataView> y el posterior establecimiento de información de filtro y ordenación hace que el índice se compile al menos dos veces: una cuando se crea <xref:System.Data.DataView> y la otra cuando se modifica cualquiera de las propiedades de ordenación y filtrado.  
  
 Para obtener más información sobre el filtrado y la ordenación con <xref:System.Data.DataView> , vea [filtrar con DataView](filtering-with-dataview-linq-to-dataset.md) y [ordenar con DataView](sorting-with-dataview-linq-to-dataset.md).  
  
## <a name="creating-dataview-from-a-linq-to-dataset-query"></a>Crear DataView desde una consulta LINQ to DataSet  

 <xref:System.Data.DataView>Se puede crear un objeto a partir de los resultados de una consulta de LINQ to DataSet, donde los resultados son una proyección de <xref:System.Data.DataRow> objetos. El objeto <xref:System.Data.DataView> que se acaba de crear hereda la información de filtrado y ordenación de la consulta a partir de la cual se creó.  
  
> [!NOTE]
> En la mayor parte de los casos, las expresiones utilizadas en el filtrado y la ordenación no deben tener efectos secundarios y deben ser deterministas. Además, las expresiones no deben tener ninguna lógica que dependa de un número de conjunto de ejecuciones, ya que las operaciones de filtrado y ordenación se pueden ejecutar un número ilimitado de veces.  
  
 No se admite la creación de <xref:System.Data.DataView> a partir de una consulta que devuelve tipos anónimos o consultas que realizan operaciones de combinación.  
  
 Sólo se admiten los siguientes operadores de consulta en una consulta utilizada para crear <xref:System.Data.DataView>:  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Cast%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.OrderBy%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.OrderByDescending%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.ThenBy%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.ThenByDescending%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Where%2A>  
  
 Tenga en cuenta que cuando <xref:System.Data.DataView> se crea un a partir de una consulta de LINQ to DataSet, el <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A> método debe ser el último método llamado en la consulta. Esto se muestra en el ejemplo siguiente, que crea un <xref:System.Data.DataView> de pedidos en línea ordenados por el total a pagar:  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquery1)]
 [!code-vb[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquery1)]  
  
 También puede utilizar las propiedades y basadas en <xref:System.Data.DataView.RowFilter%2A> cadenas <xref:System.Data.DataView.Sort%2A> para filtrar y ordenar una <xref:System.Data.DataView> después de que se haya creado a partir de una consulta. Observe que con esto se borrará la información de ordenación y filtro heredada de la consulta. En el ejemplo siguiente se crea un a <xref:System.Data.DataView> partir de una LINQ to DataSet consulta que filtra por los apellidos que empiezan por ' a '. La propiedad basada en cadena <xref:System.Data.DataView.Sort%2A> se establece para ordenar por apellidos en orden ascendente y después por nombres en orden descendente:  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## <a name="creating-a-dataview-from-a-datatable"></a>Crear DataView a partir de DataTable  

 Además de crearse a partir de una consulta de LINQ to DataSet, un <xref:System.Data.DataView> objeto se puede crear a partir de un mediante <xref:System.Data.DataTable> el <xref:System.Data.DataTableExtensions.AsDataView%2A> método.  
  
 En el ejemplo siguiente, se crea <xref:System.Data.DataView> a partir de la tabla SalesOrderDetail y se establece ese objeto como origen de datos de un objeto <xref:System.Windows.Forms.BindingSource>: Este objeto actúa como proxy para un control <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromtable)]
 [!code-vb[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromtable)]  
  
 El filtro y la ordenación pueden establecerse en <xref:System.Data.DataView> después de que se haya creado a partir de <xref:System.Data.DataTable>. El ejemplo siguiente crea <xref:System.Data.DataView> a partir de la tabla Contact y establece la propiedad <xref:System.Data.DataView.Sort%2A> para ordenar por apellidos en orden ascendente y luego por nombres en orden descendente:  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
 No obstante, se produce una pérdida de rendimiento cuando se establece la propiedad <xref:System.Data.DataView.RowFilter%2A> o <xref:System.Data.DataView.Sort%2A> después de haberse creado <xref:System.Data.DataView> a partir de una consulta, debido a que <xref:System.Data.DataView> construye un índice para admitir operaciones de filtro y ordenación. El establecimiento de la propiedad <xref:System.Data.DataView.RowFilter%2A> o <xref:System.Data.DataView.Sort%2A> hace que se recompile el índice de los datos, lo que agrega sobrecarga a la aplicación y reduce el rendimiento. Siempre que sea posible, se recomienda especificar la información sobre filtro y ordenación cuando se cree por primera vez <xref:System.Data.DataView> y evitar modificaciones posteriores.  
  
## <a name="see-also"></a>Vea también

- [Enlace de datos y LINQ to DataSet](data-binding-and-linq-to-dataset.md)
- [Filtrado con DataView](filtering-with-dataview-linq-to-dataset.md)
- [Ordenación con DataView](sorting-with-dataview-linq-to-dataset.md)
