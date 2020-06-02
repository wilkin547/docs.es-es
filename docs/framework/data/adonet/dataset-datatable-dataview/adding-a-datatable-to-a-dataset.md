---
title: Agregar un objeto DataTable a un objeto DataSet
description: Consulte este código de ejemplo para obtener información sobre cómo crear objetos DataTable y cómo agregarlos a un conjunto de DataSet existente en ADO.NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
ms.openlocfilehash: 42bd36b394de560884a2ec607f4cbc65d1171e4e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286965"
---
# <a name="adding-a-datatable-to-a-dataset"></a>Agregar un objeto DataTable a un objeto DataSet
ADO.NET permite crear objetos <xref:System.Data.DataTable> y agregarlos a un <xref:System.Data.DataSet> existente. Es posible establecer información de restricciones para una <xref:System.Data.DataTable> mediante las propiedades  <xref:System.Data.DataTable.PrimaryKey%2A> y <xref:System.Data.DataColumn.Unique%2A>.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se construye un <xref:System.Data.DataSet>, se agrega un objeto <xref:System.Data.DataTable> nuevo al <xref:System.Data.DataSet> y, a continuación, se agregan tres objetos <xref:System.Data.DataColumn> a la tabla. Por ultimo, el código establece una columna como columna de clave principal.  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a>Distinción entre mayúsculas y minúsculas  
 Pueden existir dos o más tablas o relaciones con el mismo nombre, pero que difieran en mayúsculas y minúsculas, en un <xref:System.Data.DataSet>. En estos casos, las referencias a tablas y relaciones por nombre distinguen mayúsculas y minúsculas. Por ejemplo, si el <xref:System.Data.DataSet> **conjunto de DataSet** contiene las tablas **Table1** y **Table1**, haría referencia a **tabla1** por nombre como **DataSet. Tables ["Table1"]** y **Table1** as **DataSet. Tables ["Table1"]**. Al intentar hacer referencia a cualquiera de las tablas como **DataSet. Tables ["TABLE1"]** se generaría una excepción.  
  
 El comportamiento de distinción entre mayúsculas y minúsculas no se aplica si sólo hay una tabla o relación con un nombre concreto. Por ejemplo, si <xref:System.Data.DataSet> solo tiene **Table1**, puede hacer referencia a él mediante **DataSet. Tables ["Table1"]**.  
  
> [!NOTE]
> La propiedad <xref:System.Data.DataSet.CaseSensitive%2A> del <xref:System.Data.DataSet> no afecta a este comportamiento. La propiedad <xref:System.Data.DataSet.CaseSensitive%2A> se aplica a los datos del <xref:System.Data.DataSet> y afecta a la ordenación, la búsqueda, el filtrado, la aplicación de restricciones, etc.  
  
## <a name="namespace-support"></a>Compatibilidad con los espacios de nombres  
 En las versiones de ADO.NET anteriores a la versión 2.0, dos tablas no podían tener el mismo nombre, aunque se encontrasen en espacios de nombres diferentes. Esta limitación se quitó en ADO.NET 2.0. Un <xref:System.Data.DataSet> puede contener dos tablas con el mismo valor de propiedad <xref:System.Data.DataTable.TableName%2A>, pero con valores de propiedad <xref:System.Data.DataTable.Namespace%2A> diferentes.  
  
## <a name="see-also"></a>Consulte también

- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
