---
title: Datos binarios y datos de valores grandes de SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: 4d941ad6b7865112b45fd8c20ad89e9236e17b9d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791673"
---
# <a name="sql-server-binary-and-large-value-data"></a>Datos binarios y datos de valores grandes de SQL Server
SQL Server proporciona el especificador `max`, que amplía la capacidad de almacenamiento de los tipos de datos `varchar`, `nvarchar` y `varbinary`. `varchar(max)`, `nvarchar(max)` y`varbinary(max)` se denominan colectivamente *tipos de datos de valores grandes*. Puede utilizar los tipos de datos de valores grandes para almacenar hasta 2^31-1 bytes de datos.  
  
 SQL Server 2008 incorpora el atributo FILESTREAM, que no es un tipo de datos, sino un atributo que se puede definir en una columna, y permite almacenar datos de valores grandes en el sistema de archivos en lugar de almacenarlos en la base de datos.  
  
## <a name="in-this-section"></a>En esta sección  
 [Modificación de datos de valores grandes (max) en ADO.NET](modifying-large-value-max-data.md)  
 Describe cómo trabajar con tipos de datos de valores grandes.  
  
 [Datos FILESTREAM](filestream-data.md)  
 Describe cómo trabajar con datos de valores grandes almacenados en SQL Server 2008 con el atributo FILESTREAM.  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos de SQL Server y ADO.NET](sql-server-data-types.md)
- [Operaciones de datos de SQL Server en ADO.NET](sql-server-data-operations.md)
- [Recuperar y modificar datos en ADO.NET](../retrieving-and-modifying-data.md)
- [Información general sobre ADO.NET](../ado-net-overview.md)
