---
title: Métodos genéricos Field y SetField (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
ms.openlocfilehash: 9a2913de6534612455c14858f6baffea8ef78976
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "67347476"
---
# <a name="generic-field-and-setfield-methods-linq-to-dataset"></a>Métodos genéricos Field y SetField (LINQ to DataSet)
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] proporciona métodos de extensión a la clase <xref:System.Data.DataRow> para obtener acceso a los valores de columna: el método <xref:System.Data.DataRowExtensions.Field%2A> y el método <xref:System.Data.DataRowExtensions.SetField%2A>. Estos métodos facilitan el acceso a los valores de columna a los desarrolladores, sobre todo en lo relativo a valores NULL. El <xref:System.Data.DataSet> usa <xref:System.DBNull.Value?displayProperty=nameWithType> para representar valores null, mientras que [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] usa el <xref:System.Nullable> y <xref:System.Nullable%601> tipos. Mediante el descriptor de acceso de columna preexistente en <xref:System.Data.DataRow> , deberá convertir el objeto devuelto al tipo adecuado. Si un campo determinado en un <xref:System.Data.DataRow> puede ser null, debe comprobar explícitamente un valor null porque devuelve <xref:System.DBNull.Value?displayProperty=nameWithType> y su conversión implícita a otro tipo produce una <xref:System.InvalidCastException>. En el ejemplo siguiente, si la <xref:System.Data.DataRow.IsNull%2A?displayProperty=nameWithType> no usó el método para comprobar si un valor null, se iniciaría una excepción si el indizador devolviera <xref:System.DBNull.Value?displayProperty=nameWithType> e intentó convertir un <xref:System.String>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 El método <xref:System.Data.DataRowExtensions.Field%2A> proporciona acceso a los valores de columna de <xref:System.Data.DataRow> y <xref:System.Data.DataRowExtensions.SetField%2A> establece los valores de columna en <xref:System.Data.DataRow>. Tanto el método <xref:System.Data.DataRowExtensions.Field%2A> como el método <xref:System.Data.DataRowExtensions.SetField%2A> controlan tipos que admiten valores NULL, por lo que no es necesario comprobar explícitamente si hay valores NULL, como en el ejemplo anterior. Además, ambos son métodos genéricos, lo que significa que no es necesario convertir el tipo de valor devuelto.  
  
 El siguiente ejemplo utiliza el método <xref:System.Data.DataRowExtensions.Field%2A>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 Observe que el tipo de datos especificado en el parámetro `T` genérico de los métodos <xref:System.Data.DataRowExtensions.Field%2A> y <xref:System.Data.DataRowExtensions.SetField%2A> deben coincidir con el tipo del valor subyacente. De lo contrario, se producirá una excepción <xref:System.InvalidCastException>. El nombre de columna especificado debe también coincidir con el nombre de una columna en <xref:System.Data.DataSet>; en caso contrario, se producirá una <xref:System.ArgumentException>. En ambos casos, la excepción se produce en tiempo de ejecución durante la enumeración de datos cuando se ejecuta la consulta.  
  
 El método <xref:System.Data.DataRowExtensions.SetField%2A> en sí no realiza ninguna conversión de tipos. Sin embargo, esto no significa que no se realizará una conversión de tipos. El <xref:System.Data.DataRowExtensions.SetField%2A> método expone el comportamiento ADO.NET de la <xref:System.Data.DataRow> clase. Se pudo realizar una conversión de tipos por los <xref:System.Data.DataRow> objeto y el valor convertido, a continuación, se guardarían en la <xref:System.Data.DataRow> objeto.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.DataRowExtensions>
