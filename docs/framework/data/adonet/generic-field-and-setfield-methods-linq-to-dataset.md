---
title: Métodos genéricos Field y SetField (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
ms.openlocfilehash: 9deda11592389dd799477bdc027d59a0be0036da
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200659"
---
# <a name="generic-field-and-setfield-methods-linq-to-dataset"></a>Métodos genéricos Field y SetField (LINQ to DataSet)

LINQ to DataSet proporciona métodos de extensión a la <xref:System.Data.DataRow> clase para tener acceso a los valores de columna: el <xref:System.Data.DataRowExtensions.Field%2A> método y el <xref:System.Data.DataRowExtensions.SetField%2A> método. Estos métodos facilitan el acceso a los valores de columna a los desarrolladores, sobre todo en lo relativo a valores NULL. <xref:System.Data.DataSet>Usa <xref:System.DBNull.Value?displayProperty=nameWithType> para representar valores NULL, mientras que LINQ utiliza los <xref:System.Nullable> <xref:System.Nullable%601> tipos y. Usar el descriptor de acceso de columna preexistente en <xref:System.Data.DataRow> requiere que se convierta el objeto devuelto al tipo adecuado. Si un campo determinado en <xref:System.Data.DataRow> puede ser null, debe comprobar explícitamente si hay un valor null, ya que si se devuelve <xref:System.DBNull.Value?displayProperty=nameWithType> y se convierte implícitamente a otro tipo, se produce una excepción <xref:System.InvalidCastException> . En el ejemplo siguiente, si el <xref:System.Data.DataRow.IsNull%2A?displayProperty=nameWithType> método no se usó para comprobar si hay un valor null, se produciría una excepción si el indizador devolviera <xref:System.DBNull.Value?displayProperty=nameWithType> e intentara convertirlo en un <xref:System.String> .  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 El método <xref:System.Data.DataRowExtensions.Field%2A> proporciona acceso a los valores de columna de <xref:System.Data.DataRow> y <xref:System.Data.DataRowExtensions.SetField%2A> establece los valores de columna en <xref:System.Data.DataRow>. Tanto el <xref:System.Data.DataRowExtensions.Field%2A> método como el <xref:System.Data.DataRowExtensions.SetField%2A> método controlan los tipos de valor que aceptan valores NULL, por lo que no es necesario comprobar explícitamente si hay valores NULL como en el ejemplo anterior. Además, ambos son métodos genéricos, lo que significa que no es necesario convertir el tipo de valor devuelto.  
  
 El siguiente ejemplo utiliza el método <xref:System.Data.DataRowExtensions.Field%2A>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 Observe que el tipo de datos especificado en el parámetro `T` genérico de los métodos <xref:System.Data.DataRowExtensions.Field%2A> y <xref:System.Data.DataRowExtensions.SetField%2A> deben coincidir con el tipo del valor subyacente. De lo contrario, se producirá una excepción <xref:System.InvalidCastException>. El nombre de columna especificado debe también coincidir con el nombre de una columna en <xref:System.Data.DataSet>; en caso contrario, se producirá una <xref:System.ArgumentException>. En ambos casos, la excepción se produce en tiempo de ejecución durante la enumeración de datos cuando se ejecuta la consulta.  
  
 El método <xref:System.Data.DataRowExtensions.SetField%2A> en sí no realiza ninguna conversión de tipos. Sin embargo, esto no significa que no se realizará una conversión de tipos. El <xref:System.Data.DataRowExtensions.SetField%2A> método expone el comportamiento ADO.net de la <xref:System.Data.DataRow> clase. El objeto puede realizar una conversión de tipos <xref:System.Data.DataRow> y el valor convertido se guardaría en el <xref:System.Data.DataRow> objeto.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Data.DataRowExtensions>
