---
title: 'Mitigación: período de bloqueo del grupo'
ms.date: 03/30/2017
ms.assetid: 92d2de20-79be-4df1-b182-144143a8866a
ms.openlocfilehash: 98396d4254975d1806a8477cbcd2380cb52ceaf3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457846"
---
# <a name="mitigation-pool-blocking-period"></a>Mitigación: período de bloqueo del grupo
El período de bloqueo del grupo de conexiones se quito de las conexiones a bases de datos SQL de Azure.  
  
## <a name="additional-description"></a>Descripción adicional  
 En .NET Framework 4.6.1 y versiones anteriores, cuando una aplicación encuentra un error de conexión transitorio al conectarse a una base de datos, no es posible reintentar rápidamente la conexión, porque el grupo de conexiones almacena el error en la caché y vuelve a generarlo entre 5 segundos y 1 minuto. Para obtener más información, consulte [Agrupaciones de conexiones de SQL Server (ADO.NET)](../data/adonet/sql-server-connection-pooling.md). Este comportamiento causa problemas en las conexiones a bases de datos SQL de Azure, las que habitualmente presentan errores transitorios de los que se recuperan dentro de unos pocos segundos. La característica de bloqueo del grupo de conexiones significa que la aplicación no se puede conectar a la base de datos durante un período prolongado, incluso si la base de datos está disponible. Este comportamiento es problemático especialmente para las aplicaciones web que se conectan a las bases de datos SQL de Azure y que necesitan presentarse dentro de unos segundos.  
  
 A partir de .NET Framework 4.6.2, para las solicitudes de apertura de conexión a bases de datos SQL de Azure conocidas (*.database.windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de), los errores de apertura de conexión no se almacenan en la caché. Para todos los otros intentos de conexión, se sigue aplicando el período de bloqueo del grupo de conexiones.  
  
## <a name="impact"></a>Impacto  
 Este cambio permite que el intento de abrir una conexión a las bases de datos SQL de Azure se reintente de inmediato, lo que mejora el rendimiento de las aplicaciones habilitadas para la nube.  
  
## <a name="mitigation"></a>Mitigación  
 En el caso de las aplicaciones a las que este cambio afecta negativamente, puede configurar el período de bloqueo del grupo de conexiones si establece la nueva propiedad <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A?displayProperty=nameWithType>.  El valor de la propiedad es un miembro de la enumeración <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType> que puede tener cualquiera de los tres valores:  
  
- <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType>
  
- <xref:System.Data.SqlClient.PoolBlockingPeriod.Auto?displayProperty=nameWithType>
  
- <xref:System.Data.SqlClient.PoolBlockingPeriod.NeverBlock?displayProperty=nameWithType>
  
 El comportamiento anterior se puede restaurar al establecer la propiedad <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> en <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- [Compatibilidad de aplicaciones](application-compatibility.md)
