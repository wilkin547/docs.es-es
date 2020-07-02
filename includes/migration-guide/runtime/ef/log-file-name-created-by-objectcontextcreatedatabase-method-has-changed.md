---
ms.openlocfilehash: 768a948849064cedb38110f5ed271717442325c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620620"
---
### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>El nombre de archivo de registro creado por el método ObjectContext.CreateDatabase ha cambiado para coincidir con las especificaciones de SQL Server

#### <a name="details"></a>Detalles

Cuando se llama al método <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName> directamente o mediante Code First con el proveedor SqlClient y un valor AttachDBFilename en la cadena de conexión, se crea un archivo de registro denominado nombreDeArchivo_log.ldf en lugar de nombreDeArchivo.ldf (donde nombreDeArchivo es el nombre del archivo especificado mediante el valor AttachDBFilename). Este cambio mejora la depuración al proporcionar un archivo de registro cuyo nombre se ajusta a las especificaciones de SQL Server.

#### <a name="suggestion"></a>Sugerencia

Si el nombre de archivo de registro es importante para una aplicación, la aplicación debería actualizarse para que espere el formato de nombre de archivo estándar _log.ldf.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li></ul>|
