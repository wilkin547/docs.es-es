---
title: Métodos genéricos Field y SetField (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
ms.openlocfilehash: d7ddee775e91c6be6166a091997afd58113cfe6b
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249108"
---
# <a name="generic-field-and-setfield-methods-linq-to-dataset"></a>Métodos genéricos Field y SetField (LINQ to DataSet)
LINQ to DataSetLINQ to <xref:System.Data.DataRow> DataSet proporciona métodos de extensión a la clase para tener acceso a los valores de columna: el <xref:System.Data.DataRowExtensions.Field%2A> método y el <xref:System.Data.DataRowExtensions.SetField%2A> método. Estos métodos facilitan el acceso a los valores de columna a los desarrolladores, sobre todo en lo relativo a valores NULL. El <xref:System.Data.DataSet> <xref:System.DBNull.Value?displayProperty=nameWithType> uso para representar valores null, <xref:System.Nullable> <xref:System.Nullable%601> mientras que LINQ usa los tipos y. El uso del descriptor <xref:System.Data.DataRow> de acceso de columna preexistente en requiere que convierta el objeto devuelto al tipo adecuado. Si un campo <xref:System.Data.DataRow> determinado en un puede ser null, debe comprobar <xref:System.DBNull.Value?displayProperty=nameWithType> explícitamente si hay un valor <xref:System.InvalidCastException>nulo porque devolverlo e horizontalmente convertirlo a otro tipo produce un archivo . En el ejemplo siguiente, si el <xref:System.Data.DataRow.IsNull%2A?displayProperty=nameWithType> método no se usó para comprobar si hay <xref:System.DBNull.Value?displayProperty=nameWithType> un valor nulo, <xref:System.String>se produciría una excepción si el indizador devolvió e intentó convertirlo en un archivo .  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 El método <xref:System.Data.DataRowExtensions.Field%2A> proporciona acceso a los valores de columna de <xref:System.Data.DataRow> y <xref:System.Data.DataRowExtensions.SetField%2A> establece los valores de columna en <xref:System.Data.DataRow>. Tanto <xref:System.Data.DataRowExtensions.Field%2A> el <xref:System.Data.DataRowExtensions.SetField%2A> método como el método controlan los tipos de valor que aceptan valores NULL, por lo que no es necesario comprobar explícitamente los valores NU como en el ejemplo anterior. Además, ambos son métodos genéricos, lo que significa que no es necesario convertir el tipo de valor devuelto.  
  
 El siguiente ejemplo utiliza el método <xref:System.Data.DataRowExtensions.Field%2A>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 Observe que el tipo de datos especificado en el parámetro `T` genérico de los métodos <xref:System.Data.DataRowExtensions.Field%2A> y <xref:System.Data.DataRowExtensions.SetField%2A> deben coincidir con el tipo del valor subyacente. De lo contrario, se producirá una excepción <xref:System.InvalidCastException>. El nombre de columna especificado debe también coincidir con el nombre de una columna en <xref:System.Data.DataSet>; en caso contrario, se producirá una <xref:System.ArgumentException>. En ambos casos, la excepción se produce en tiempo de ejecución durante la enumeración de datos cuando se ejecuta la consulta.  
  
 El método <xref:System.Data.DataRowExtensions.SetField%2A> en sí no realiza ninguna conversión de tipos. Sin embargo, esto no significa que no se realizará una conversión de tipos. El <xref:System.Data.DataRowExtensions.SetField%2A> método expone el comportamiento <xref:System.Data.DataRow> ADO.NET de la clase. El objeto podría realizar <xref:System.Data.DataRow> una conversión de tipos y <xref:System.Data.DataRow> el valor convertido se guardaría en el objeto.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.DataRowExtensions>
