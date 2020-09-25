---
title: Agrupar conexiones
description: Obtenga información sobre la agrupación de conexiones, una técnica de optimización que ADO.NET usa para minimizar el costo de abrir conexiones a orígenes de datos.
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: f16b3ba733cce4a1efe72e3f4eee48a431a96fb7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198722"
---
# <a name="connection-pooling"></a>Agrupar conexiones

La conexión a un origen de datos puede ser un proceso largo. Para minimizar el costo de la apertura de conexiones, ADO.NET usa una técnica de optimización denominada *agrupación*de conexiones, lo que minimiza el costo de abrir y cerrar conexiones repetidas veces. Los proveedores de datos .NET Framework tratan de forma diferente la agrupación de conexiones.  
  
## <a name="in-this-section"></a>En esta sección  

 [Agrupación de conexiones de SQL Server (ADO.NET)](sql-server-connection-pooling.md)  
 Proporciona información general sobre la agrupación de conexiones y describe cómo funciona la agrupación de conexiones en SQL Server.  
  
 [Agrupación de conexiones de OLE DB, ODBC y Oracle](ole-db-odbc-and-oracle-connection-pooling.md)  
 Describe la agrupación de conexiones en los proveedores de datos .NET Framework para OLE DB, ODBC y Oracle.  
  
## <a name="see-also"></a>Consulte también

- [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)
- [Información general de ADO.NET](ado-net-overview.md)
