---
title: Métodos genéricos Field y SetField (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
ms.openlocfilehash: 310eb3ccecc3159234ed362ed044be7ad704dde4
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634838"
---
# <a name="generic-field-and-setfield-methods-linq-to-dataset"></a>Métodos genéricos Field y SetField (LINQ to DataSet)
LINQ to DataSet proporciona métodos de extensión a la clase <xref:System.Data.DataRow> para tener acceso a los valores de columna: el método <xref:System.Data.DataRowExtensions.Field%2A> y el método <xref:System.Data.DataRowExtensions.SetField%2A>. Estos métodos facilitan el acceso a los valores de columna a los desarrolladores, sobre todo en lo relativo a valores NULL. El <xref:System.Data.DataSet> usa <xref:System.DBNull.Value?displayProperty=nameWithType> para representar valores NULL, mientras que LINQ usa los tipos <xref:System.Nullable> y <xref:System.Nullable%601>. Usar el descriptor de acceso de columna preexistente en <xref:System.Data.DataRow> requiere que se convierta el objeto devuelto al tipo adecuado. Si un campo determinado de una <xref:System.Data.DataRow> puede ser null, debe comprobar explícitamente si hay un valor null, ya que devolver <xref:System.DBNull.Value?displayProperty=nameWithType> y convertirlo implícitamente a otro tipo produce una <xref:System.InvalidCastException>. En el ejemplo siguiente, si el método <xref:System.Data.DataRow.IsNull%2A?displayProperty=nameWithType> no se usó para comprobar si hay un valor null, se produciría una excepción si el indexador devolviera <xref:System.DBNull.Value?displayProperty=nameWithType> e intentó convertirlo en un <xref:System.String>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 El método <xref:System.Data.DataRowExtensions.Field%2A> proporciona acceso a los valores de columna de <xref:System.Data.DataRow> y <xref:System.Data.DataRowExtensions.SetField%2A> establece los valores de columna en <xref:System.Data.DataRow>. Tanto el método <xref:System.Data.DataRowExtensions.Field%2A> como el método <xref:System.Data.DataRowExtensions.SetField%2A> controlan tipos que admiten valores NULL, por lo que no es necesario comprobar explícitamente si hay valores NULL, como en el ejemplo anterior. Además, ambos son métodos genéricos, lo que significa que no es necesario convertir el tipo de valor devuelto.  
  
 El siguiente ejemplo utiliza el método <xref:System.Data.DataRowExtensions.Field%2A>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 Observe que el tipo de datos especificado en el parámetro `T` genérico de los métodos <xref:System.Data.DataRowExtensions.Field%2A> y <xref:System.Data.DataRowExtensions.SetField%2A> deben coincidir con el tipo del valor subyacente. De lo contrario, se producirá una excepción <xref:System.InvalidCastException>. El nombre de columna especificado debe también coincidir con el nombre de una columna en <xref:System.Data.DataSet>; en caso contrario, se producirá una <xref:System.ArgumentException>. En ambos casos, la excepción se produce en tiempo de ejecución durante la enumeración de datos cuando se ejecuta la consulta.  
  
 El método <xref:System.Data.DataRowExtensions.SetField%2A> en sí no realiza ninguna conversión de tipos. Sin embargo, esto no significa que no se realizará una conversión de tipos. El método <xref:System.Data.DataRowExtensions.SetField%2A> expone el comportamiento ADO.NET de la clase <xref:System.Data.DataRow>. El objeto <xref:System.Data.DataRow> puede realizar una conversión de tipos y el valor convertido se guardaría en el objeto <xref:System.Data.DataRow>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.DataRowExtensions>
