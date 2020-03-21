---
title: Crear un objeto DataTable a partir de una consulta (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b97afeb-03f8-41e2-8eb3-58aff65f7d18
ms.openlocfilehash: 46e977088cd6eca7842565ae6b258f70ca5920a9
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111821"
---
# <a name="creating-a-datatable-from-a-query-linq-to-dataset"></a>Crear un objeto DataTable a partir de una consulta (LINQ to DataSet)
El enlace de datos es una utilización muy frecuente del objeto <xref:System.Data.DataTable>. El método <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> toma los resultados de una consulta y copia los datos en un objeto <xref:System.Data.DataTable> que puede utilizarse después para el enlace de datos. Cuando las operaciones de datos se han realizado, el <xref:System.Data.DataTable> nuevo se vuelve a combinar en el <xref:System.Data.DataTable> de origen.  
  
 El método <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> utiliza el siguiente proceso para crear un <xref:System.Data.DataTable> a partir de una consulta:  
  
1. El método <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> clona un <xref:System.Data.DataTable> a partir de la tabla origen (un objeto <xref:System.Data.DataTable> que implementa la interfaz <xref:System.Linq.IQueryable%601>). El <xref:System.Collections.IEnumerable> origen se ha originado generalmente a partir de una LINQ to DataSet expresión o consulta de método.  
  
2. El esquema del <xref:System.Data.DataTable> clonado se compila a partir de las columnas del primer objeto <xref:System.Data.DataRow> enumerado en la tabla origen; el nombre de la tabla clonada es el nombre de la tabla origen con la palabra "query" anexada.  
  
3. En cada fila de la tabla origen, el contenido de la fila se copia en un objeto<xref:System.Data.DataRow> nuevo, el cual, a continuación, se inserta en la tabla clonada. Las propiedades <xref:System.Data.DataRow.RowState%2A> y <xref:System.Data.DataRow.RowError%2A> se mantienen en toda la operación de copia. Si los objetos <xref:System.ArgumentException> de origen pertenecen a tablas diferentes, se produce una<xref:System.Data.DataRow>.  
  
4. Cuando todos los objetos <xref:System.Data.DataTable> de la tabla de entrada que se puede consultar se han copiado, se devuelve el <xref:System.Data.DataRow> clonado. Si la secuencia origen no contiene objetos <xref:System.Data.DataRow>, el método devuelve un <xref:System.Data.DataTable> vacío.  
  
Llamar <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> al método hace que se ejecute la consulta enlazada a la tabla de origen.  
  
 Cuando el método <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> encuentra una referencia NULL o un tipo de valor que admite valores NULL en una fila de la tabla origen, reemplaza el valor con <xref:System.DBNull.Value>. De este modo, los valores NULL se controlan correctamente en el <xref:System.Data.DataTable> devuelto.  
  
 Nota: el método <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> acepta como entrada una consulta que pueda devolver filas de varios objetos <xref:System.Data.DataTable> o <xref:System.Data.DataSet>. El método <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> copiará los datos pero no las propiedades desde los objetos <xref:System.Data.DataTable> o <xref:System.Data.DataSet> de origen en el elemento <xref:System.Data.DataTable> que se va a devolver. Necesitará establecer explícitamente las propiedades de los elementos <xref:System.Data.DataTable> devueltos, como <xref:System.Data.DataTable.Locale%2A> y <xref:System.Data.DataTable.TableName%2A>.  
  
 En el ejemplo siguiente se consultan en la tabla SalesOrderHeader los pedidos posteriores al 8 de agosto de 2001 y se utiliza el método <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> para crear un <xref:System.Data.DataTable> a partir de esa consulta. A continuación, se enlaza <xref:System.Data.DataTable> a un <xref:System.Windows.Forms.BindingSource>, que actúa como proxy para un objeto <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#CopyToDataTable1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#copytodatatable1)]
 [!code-vb[DP LINQ to DataSet Examples#CopyToDataTable1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#copytodatatable1)]  
  
## <a name="creating-a-custom-copytodatatablet-method"></a>Creación de un método\<de> CopyToDataTable T personalizado  
 Los métodos <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> existentes solo funcionan en un origen <xref:System.Collections.Generic.IEnumerable%601> en el que el parámetro genérico `T` es de tipo <xref:System.Data.DataRow>. Aunque esto es útil, no permite la creación de tablas a partir de una secuencia de tipos escalares, a partir de consultas que devuelven tipos anónimos, o a partir de consultas que realizan combinaciones de tablas. Para obtener un ejemplo de `CopyToDataTable` cómo implementar dos métodos personalizados que cargan una tabla de una secuencia de tipos escalares o anónimos, vea [Cómo: implementar\<CopyToDataTable T> donde el tipo genérico T no es un DataRow](implement-copytodatatable-where-type-not-a-datarow.md)s.  
  
 Los ejemplos de esta sección utilizan los tipos personalizados siguientes:  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#ItemClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#itemclass)]
 [!code-vb[DP Custom CopyToDataTable Examples#ItemClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#itemclass)]  
  
### <a name="example"></a>Ejemplo  
 En este ejemplo se realiza una combinación en las tablas `SalesOrderHeader` y `SalesOrderDetail` para obtener pedidos en línea del mes de agosto y se crea una tabla a partir de la consulta.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#join)]
 [!code-vb[DP Custom CopyToDataTable Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#join)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se consulta una colección de elementos cuyo precio es superior a $ 9,99 y se crea una tabla a partir de los resultados de la consulta.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsIntoTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsintotable)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsIntoTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsintotable)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se consulta una colección de elementos cuyo precio es superior a $ 9,99 y se proyectan los resultados. La secuencia de tipos anónimos devuelta se carga en una tabla existente.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsIntoExistingTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsintoexistingtable)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsIntoExistingTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsintoexistingtable)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se consulta una colección de elementos cuyo precio es superior a $ 9,99 y se proyectan los resultados. La secuencia de tipos anónimos devuelta se carga en una tabla existente. El esquema de la tabla se amplía automáticamente porque los tipos `Book` y `Movies` se derivan del tipo `Item`.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsExpandSchema](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsexpandschema)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsExpandSchema](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsexpandschema)]  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se consulta una colección de elementos cuyo precio es superior a $ 9,99 y se devuelve una secuencia de <xref:System.Double>, que se carga en una tabla nueva.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadScalarSequence](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loadscalarsequence)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadScalarSequence](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loadscalarsequence)]  
  
## <a name="see-also"></a>Consulte también

- [Guía de programación](programming-guide-linq-to-dataset.md)
- [Métodos genéricos Field y SetField](generic-field-and-setfield-methods-linq-to-dataset.md)
- [Ejemplos de LINQ to DataSet](linq-to-dataset-examples.md)
