---
title: Comparar valores GUID y uniqueidentifier
description: Aprenda a crear y comparar valores GUID en el proveedor de datos de .NET Framework para SQL Server, que se representan mediante el tipo de datos uniqueidentifier.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: aababd75-2335-43e3-ace8-4b7ae84191a8
ms.openlocfilehash: 245b7246712822043d302c43a765c29ac2090e00
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286512"
---
# <a name="comparing-guid-and-uniqueidentifier-values"></a>Comparar valores GUID y uniqueidentifier
El tipo de datos de identificador único global (GUID) de SQL Server se representa mediante el tipo de datos `uniqueidentifier`, que almacena un valor binario de 16 bytes. Un GUID es un número binario que sirve principalmente como identificador que debe ser único en una red formada por varios equipos en muchos sitios. Los GUID se pueden generar mediante una llamada a la función NEWID de Transact-SQL y se garantiza que sea único en todo el mundo. Para obtener más información, vea [uniqueidentifier (Transact-SQL)](/sql/t-sql/data-types/uniqueidentifier-transact-sql).  
  
## <a name="working-with-sqlguid-values"></a>Trabajo con valores SqlGuid  
 Dado que los valores de GUID son largos y poco claros, no son significativos para los usuarios. Si se usan GUID generados de forma aleatoria para los valores de clave e inserta una gran cantidad de filas, obtendrá E/S aleatoria en los índices, lo que puede afectar negativamente al rendimiento. Los GUID también son relativamente grandes en comparación con otros tipos de datos. En general, se recomienda usar GUID solo para escenarios muy estrechos en los que no sea adecuado ningún otro tipo de datos.  
  
### <a name="comparing-guid-values"></a>Comparación de valores GUID  
 Con los valores `uniqueidentifier` se pueden usar operadores de comparación. No obstante, no se implementa la ordenación mediante la comparación de los patrones de bits de los dos valores. Las únicas operaciones que se permiten con respecto a un `uniqueidentifier` valor son las comparaciones (=,  <>, \<, > , \<=, > =) y la comprobación de NULL (IS NULL y is not null). No se permite ningún otro operador aritmético.  
  
 Tanto <xref:System.Guid> como <xref:System.Data.SqlTypes.SqlGuid> tienen un método `CompareTo` para comparar distintos valores GUID. Sin embargo, `System.Guid.CompareTo` y `SqlTypes.SqlGuid.CompareTo` se implementan de forma diferente. <xref:System.Data.SqlTypes.SqlGuid> implementa `CompareTo` con el comportamiento de SQL Server, los seis últimos bytes de un valor son más significativos. <xref:System.Guid> evalúa los 16 bytes. En el ejemplo siguiente se muestra esta diferencia de comportamiento. La primera sección del código muestra los valores de <xref:System.Guid> sin ordenar y la segunda sección de código muestra los valores de <xref:System.Guid> ordenados. En la tercera sección se muestran los valores de <xref:System.Data.SqlTypes.SqlGuid> ordenados. El resultado se muestra debajo de la lista de códigos.  
  
 [!code-csharp[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/VB/source.vb#1)]  
  
 Este ejemplo genera los siguientes resultados.  
  
```output  
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
  
## <a name="see-also"></a>Consulte también

- [Tipos de datos de SQL Server y ADO.NET](sql-server-data-types.md)
- [Información general de ADO.NET](../ado-net-overview.md)
