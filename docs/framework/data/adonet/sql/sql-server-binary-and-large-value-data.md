---
title: Datos binarios y datos de valores grandes de SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: a9296e83b0f4e4352423470433670bb2cbe5a248
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183044"
---
# <a name="sql-server-binary-and-large-value-data"></a>Datos binarios y datos de valores grandes de SQL Server

SQL Server proporciona el especificador `max`, que amplía la capacidad de almacenamiento de los tipos datos `varchar`, `nvarchar` y `varbinary`. `varchar(max)`, `nvarchar(max)` y `varbinary(max)` se denominan colectivamente *tipos de datos de valores grandes*. Puede usar los tipos de datos de valores grandes para almacenar hasta 2^31-1 bytes de datos.  
  
 SQL Server 2008 presenta el atributo FILESTREAM, que no es un tipo de datos, sino un atributo que se puede definir en una columna, lo que permite almacenar datos de valores grandes en el sistema de archivos, en lugar de en la base de datos.  
  
## <a name="in-this-section"></a>En esta sección  

 [Modificación de datos de valores grandes (Max) en ADO.NET](modifying-large-value-max-data.md)  
 Describe cómo trabajar con tipos de datos de valores grandes.  
  
 [Datos FILESTREAM](filestream-data.md)  
 Describe cómo trabajar con datos de valores grandes almacenados en SQL Server 2008 con el atributo FILESTREAM.  
  
## <a name="see-also"></a>Consulte también

- [Tipos de datos de SQL Server y ADO.NET](sql-server-data-types.md)
- [SQL Server operaciones de datos en ADO.NET](sql-server-data-operations.md)
- [Recuperar y modificar datos en ADO.NET](../retrieving-and-modifying-data.md)
- [Información general de ADO.NET](../ado-net-overview.md)
