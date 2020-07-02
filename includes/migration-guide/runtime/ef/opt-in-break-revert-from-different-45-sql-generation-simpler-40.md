---
ms.openlocfilehash: 22b5abbe769733e8d5ca3e78dd9e6e13b2363737
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620617"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a>Permitir interrupción para revertir desde otra generación de SQL de la versión 4.5 a la generación de SQL más sencilla de la versión 4.0

#### <a name="details"></a>Detalles

Las consultas que generan instrucciones JOIN y contienen una llamada a una operación de limitación sin usar primero OrderBy, ahora generan código SQL más sencillo. Después de actualizar a .NET Framework 4.5, estas consultas generaban código SQL más complicado que en versiones anteriores.

#### <a name="suggestion"></a>Sugerencia

Esta característica está deshabilitada de manera predeterminada. Si Entity Framework genera instrucciones JOIN adicionales que causan la degradación del rendimiento, puede habilitar esta característica mediante la adición de la entrada siguiente a la sección <code>&lt;appSettings&gt;</code> del archivo de configuración de la aplicación (app.config):<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Transparente|
|Versión|4.5.2|
|Tipo|Tiempo de ejecución|
