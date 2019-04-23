---
ms.openlocfilehash: e5d81d791e1a2f1a2dbdafc787dec1227423883d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774275"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a>Permitir interrupción para revertir desde otra generación de SQL de la versión 4.5 a la generación de SQL más sencilla de la versión 4.0

|   |   |
|---|---|
|Detalles|Las consultas que generan instrucciones JOIN y contienen una llamada a una operación de limitación sin usar primero OrderBy, ahora generan código SQL más sencillo. Después de actualizar a .NET Framework 4.5, estas consultas generaban código SQL más complicado que en versiones anteriores.|
|Sugerencia|Esta característica está deshabilitada de manera predeterminada. Si Entity Framework genera instrucciones JOIN adicionales que causan la degradación del rendimiento, puede habilitar esta característica mediante la adición de la entrada siguiente a la sección <code>&lt;appSettings&gt;</code> del archivo de configuración de la aplicación (app.config):<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>|
|Ámbito|Transparente|
|Versión|4.5.2|
|Tipo|Tiempo de ejecución|
