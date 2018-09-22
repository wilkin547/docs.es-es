---
title: Comparar valores GUID y uniqueidentifier
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: aababd75-2335-43e3-ace8-4b7ae84191a8
ms.openlocfilehash: 7d982b73332a2629ccd32c409e0de6fe1ce6eb98
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2018
ms.locfileid: "46696380"
---
# <a name="comparing-guid-and-uniqueidentifier-values"></a>Comparar valores GUID y uniqueidentifier
El tipo de datos de identificador único global (GUID) de SQL Server viene representado por el tipo de datos `uniqueidentifier`, que almacena un valor binario de 16 bytes. Un GUID es un número binario que sirve principalmente como identificador, el cual que debe ser único en una red formada por varios equipos en muchos sitios. Los GUID se pueden generar con la llamada a la función NEWID de Transact-SQL, y se tiene la garantía de que son únicos en todo el mundo. Para obtener más información, consulte [uniqueidentifier (Transact-SQL)](/sql/t-sql/data-types/uniqueidentifier-transact-sql).  
  
## <a name="working-with-sqlguid-values"></a>Trabajo con valores SqlGuid  
 Como los valores GUID son largos y poco claros, no resultan significativos para los usuarios. Si utiliza GUID generados de forma aleatoria en valores de claves e inserta muchas filas, obtendrá E/S aleatoria en los índices, lo que puede afectar al rendimiento negativamente. Los GUID son también relativamente grandes si se comparan con otros tipos de datos. En general, se recomienda el uso de GUID solo en situaciones muy limitadas en las que no resulta adecuado ningún otro tipo de datos.  
  
### <a name="comparing-guid-values"></a>Comparación de valores GUID  
 Los operadores de comparación se pueden utilizar con valores `uniqueidentifier`. Sin embargo, al comparar los patrones de bits de los dos valores no se implementa el orden. Las únicas operaciones que se permiten en un `uniqueidentifier` valor son comparaciones (=, <>, \<, >, \<=, > =) y comprobaciones para NULL (IS NULL e IS NOT NULL). No se permite ninguna otra operación aritmética.  
  
 Tanto <xref:System.Guid> como <xref:System.Data.SqlTypes.SqlGuid> tienen un método `CompareTo` para comparar diferentes valores GUID. Sin embargo, `System.Guid.CompareTo` y `SqlTypes.SqlGuid.CompareTo` se implementan de forma distinta. <xref:System.Data.SqlTypes.SqlGuid> implementa `CompareTo` mediante el comportamiento de SQL Server, en el que los últimos seis bytes de un valor son los más significativos. <xref:System.Guid> evalúa los 16 bytes. En el siguiente ejemplo se muestra esta diferencia conductual. La primera sección del código muestra valores <xref:System.Guid> sin ordenar; la segunda sección muestra los valores <xref:System.Guid> ordenados y la tercera sección muestra los valores <xref:System.Data.SqlTypes.SqlGuid> ordenados. El resultado se muestra debajo del listado de código.  
  
 [!code-csharp[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/VB/source.vb#1)]  
  
 Este ejemplo produce los siguientes resultados.  
  
```  
Unsorted Guids:  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
  
Sorted Guids:  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
  
Sorted SqlGuids:  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
```  
  
## <a name="see-also"></a>Vea también  

[Tipos de datos de SQL Server y ADO.NET](sql-server-data-types.md)  
[Información general sobre ADO.NET](../ado-net-overview.md)  
