---
title: Filtrar con DataView (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5632d74a-ff53-4ea7-9fe7-4a148eeb1c68
ms.openlocfilehash: 9b4c8e9730dde7d19df9e6a11052ae4591465ea7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177467"
---
# <a name="filtering-with-dataview-linq-to-dataset"></a>Filtrar con DataView (LINQ to DataSet)

La capacidad de filtrar datos utilizando criterios específicos y después presentarlos a un cliente mediante un control de IU es un aspecto importante del enlace de datos. <xref:System.Data.DataView> proporciona varias maneras de filtrar datos y devolver subconjuntos de filas de datos que reúnan determinados criterios. Además de las funcionalidades de filtrado basadas en cadenas, <xref:System.Data.DataView> también proporciona la capacidad de usar expresiones LINQ para los criterios de filtrado. Las expresiones LINQ permiten operaciones de filtrado mucho más complejas y eficaces que el filtrado basado en cadenas.  
  
 Existen dos maneras de filtrar datos utilizando <xref:System.Data.DataView>:  
  
- Cree un a <xref:System.Data.DataView> partir de una consulta de LINQ to DataSet con una cláusula WHERE.  
  
- Utilizar las capacidades de filtro basado en cadena de <xref:System.Data.DataView> existentes.  
  
## <a name="creating-dataview-from-a-query-with-filtering-information"></a>Crear DataView desde una consulta con información de filtro  

 <xref:System.Data.DataView>Se puede crear un objeto a partir de una consulta de LINQ to DataSet. Si dicha consulta tiene una cláusula `Where`, <xref:System.Data.DataView> se crea con información de filtro desde la consulta. La expresión de la cláusula `Where` se utiliza para determinar qué filas de datos se incluirán en <xref:System.Data.DataView>, y constituye la base para el filtro.  
  
 Los filtros basados en expresión son más eficaces y complejos que los sencillos filtros basados en cadena. Los filtros basados en cadena y los basados en expresión se excluyen mutuamente. Cuando el <xref:System.Data.DataView.RowFilter%2A> basado en cadena se establece después de haber creado <xref:System.Data.DataView> desde una consulta, se borra el filtro basado en expresión inferido a partir de la consulta.  
  
> [!NOTE]
> En la mayor parte de los casos, las expresiones utilizadas en el filtro no deben tener efectos secundarios y deben ser deterministas. Además, las expresiones no deben tener ninguna lógica que dependa de un número de conjunto de ejecuciones, porque las operaciones de filtrado se pueden ejecutar un número ilimitado de veces.  
  
### <a name="example"></a>Ejemplo  

 El siguiente ejemplo consulta en la tabla SalesOrderDetail los pedidos con una cantidad superior a 2 e inferior a 6; crea un <xref:System.Data.DataView> desde una consulta y enlaza <xref:System.Data.DataView> a un <xref:System.Windows.Forms.BindingSource>:  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhere](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywhere)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhere](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywhere)]  
  
### <a name="example"></a>Ejemplo  

 El siguiente ejemplo crea un <xref:System.Data.DataView> desde una consulta de pedidos efectuados con posterioridad al 6 de junio de 2001:  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhere3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywhere3)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhere3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywhere3)]  
  
### <a name="example"></a>Ejemplo  

 El filtro se puede combinar también con la ordenación. El siguiente ejemplo crea un <xref:System.Data.DataView> desde una consulta de contactos cuyos apellidos empiezan por la letra "S", y los ordena primero por el apellido y después por el nombre:  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhereOrderByThenBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywhereorderbythenby)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhereOrderByThenBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywhereorderbythenby)]  
  
### <a name="example"></a>Ejemplo  

 El siguiente ejemplo utiliza el algoritmo SoundEx para encontrar contactos cuyo apellido es similar a "Zhu". El algoritmo SoundEx se implementa en el método SoundEx.  
  
 [!code-csharp[DP DataView Samples#LDVSoundExFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvsoundexfilter)]
 [!code-vb[DP DataView Samples#LDVSoundExFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvsoundexfilter)]  
  
 SoundEx es un algoritmo fonético utilizado para indizar nombres según el sonido, tal como se pronuncian en inglés, que fue desarrollado originalmente por la Oficina del Censo de Estados Unidos. El método SoundEx devuelve un código de cuatro caracteres para un nombre que consiste en una letra inglesa seguida de tres números. La letra es la primera letra del nombre y los números codifican el resto de las consonantes del mismo. Los nombres que suenan parecidos comparten el mismo código SoundEx. A continuación se muestra la implementación del SoundEx utilizado en el método SoundEx del ejemplo anterior:  
  
 [!code-csharp[DP DataView Samples#SoundEx](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#soundex)]
 [!code-vb[DP DataView Samples#SoundEx](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#soundex)]  
  
## <a name="using-the-rowfilter-property"></a>Utilizar la propiedad RowFilter  

 La funcionalidad de filtrado basada en cadena existente de <xref:System.Data.DataView> sigue funcionando en el contexto de LINQ to DataSet. Para obtener más información sobre el filtrado basado en cadena <xref:System.Data.DataView.RowFilter%2A> , vea [ordenar y filtrar datos](./dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
 El siguiente ejemplo crea un <xref:System.Data.DataView> desde la tabla Contact y, a continuación, establece la propiedad <xref:System.Data.DataView.RowFilter%2A> para que devuelva filas cuando el apellido del contacto sea "Zhu":  
  
 [!code-csharp[DP DataView Samples#LDVRowFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvrowfilter)]
 [!code-vb[DP DataView Samples#LDVRowFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvrowfilter)]  
  
 Una vez que se ha <xref:System.Data.DataView> creado a partir de una <xref:System.Data.DataTable> consulta de o LINQ to DataSet, puede utilizar la <xref:System.Data.DataView.RowFilter%2A> propiedad para especificar subconjuntos de filas basándose en sus valores de columna. Los filtros basados en cadena y los basados en expresión se excluyen mutuamente. Al establecer la <xref:System.Data.DataView.RowFilter%2A> propiedad se borrará la expresión de filtro que se deduce de la LINQ to DataSet consulta y no se puede restablecer la expresión de filtro.  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhereSetRowFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywheresetrowfilter)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhereSetRowFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywheresetrowfilter)]  
  
 Si desea devolver los resultados de una consulta determinada en los datos, en lugar de proporcionar una vista dinámica de un subconjunto de los datos, para conseguir el máximo rendimiento puede utilizar los métodos <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A> de la <xref:System.Data.DataView>, en lugar de establecer la propiedad <xref:System.Data.DataView.RowFilter%2A>. La propiedad <xref:System.Data.DataView.RowFilter%2A> es más idónea en una aplicación enlazada a datos donde un control enlazado muestra resultados filtrados. El establecimiento de la propiedad <xref:System.Data.DataView.RowFilter%2A> hace que se recompile el índice de los datos, lo que agrega sobrecarga a la aplicación y reduce el rendimiento. Los métodos <xref:System.Data.DataView.Find%2A> y <xref:System.Data.DataView.FindRows%2A> utilizan el índice actual, sin necesidad de recompilarlo. Si va a llamar a <xref:System.Data.DataView.Find%2A> o a <xref:System.Data.DataView.FindRows%2A> una única vez, entonces debería utilizar el <xref:System.Data.DataView> existente. Si va a llamar a <xref:System.Data.DataView.Find%2A> o a <xref:System.Data.DataView.FindRows%2A> varias veces, debería crear un nuevo <xref:System.Data.DataView> para recompilar el índice en la columna en la que desea buscar y, a continuación, llamar a los métodos <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A>. Para obtener más información sobre <xref:System.Data.DataView.Find%2A> los <xref:System.Data.DataView.FindRows%2A> métodos y, vea [Buscar filas](./dataset-datatable-dataview/finding-rows.md) y [rendimiento de DataView](dataview-performance.md).  
  
## <a name="clearing-the-filter"></a>Borrar el filtro  

 Después de haber configurado el filtro de <xref:System.Data.DataView>, éste se puede borrar mediante la propiedad <xref:System.Data.DataView.RowFilter%2A>. El filtro de <xref:System.Data.DataView> se pude borrar de dos maneras:  
  
- Establezca la propiedad <xref:System.Data.DataView.RowFilter%2A> en `null`.  
  
- Establecer la propiedad <xref:System.Data.DataView.RowFilter%2A> en una cadena vacía.  
  
### <a name="example"></a>Ejemplo  

 El siguiente ejemplo crea un <xref:System.Data.DataView> desde una consulta y, a continuación, borra el filtro estableciendo la propiedad <xref:System.Data.DataView.RowFilter%2A> en `null`:  
  
 [!code-csharp[DP DataView Samples#LDVClearRowFilter2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearrowfilter2)]
 [!code-vb[DP DataView Samples#LDVClearRowFilter2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearrowfilter2)]  
  
### <a name="example"></a>Ejemplo  

 El siguiente ejemplo crea un <xref:System.Data.DataView> desde una tabla, establece la propiedad <xref:System.Data.DataView.RowFilter%2A> y, a continuación, borra el filtro estableciendo la propiedad <xref:System.Data.DataView.RowFilter%2A> en una cadena vacía:  
  
 [!code-csharp[DP DataView Samples#LDVClearRowFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearrowfilter)]
 [!code-vb[DP DataView Samples#LDVClearRowFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearrowfilter)]  
  
## <a name="see-also"></a>Consulte también

- [Enlace de datos y LINQ to DataSet](data-binding-and-linq-to-dataset.md)
- [Ordenación con DataView](sorting-with-dataview-linq-to-dataset.md)
