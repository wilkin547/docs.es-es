---
ms.openlocfilehash: 64d540278544e74c46d46b77c97bccd26d4116dd
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803258"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="b969e-101">Permitir interrupción para revertir desde otra generación de SQL de la versión 4.5 a la generación de SQL más sencilla de la versión 4.0</span><span class="sxs-lookup"><span data-stu-id="b969e-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b969e-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="b969e-102">Details</span></span>|<span data-ttu-id="b969e-103">Las consultas que generan instrucciones JOIN y contienen una llamada a una operación de limitación sin usar primero OrderBy, ahora generan código SQL más sencillo.</span><span class="sxs-lookup"><span data-stu-id="b969e-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="b969e-104">Después de actualizar a .NET Framework 4.5, estas consultas generaban código SQL más complicado que en versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="b969e-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>|
|<span data-ttu-id="b969e-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="b969e-105">Suggestion</span></span>|<span data-ttu-id="b969e-106">Esta característica está deshabilitada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b969e-106">This feature is disabled by default.</span></span> <span data-ttu-id="b969e-107">Si Entity Framework genera instrucciones JOIN adicionales que causan la degradación del rendimiento, puede habilitar esta característica mediante la adición de la entrada siguiente a la sección <code>&lt;appSettings&gt;</code> del archivo de configuración de la aplicación (app.config):</span><span class="sxs-lookup"><span data-stu-id="b969e-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="b969e-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="b969e-108">Scope</span></span>|<span data-ttu-id="b969e-109">Transparente</span><span class="sxs-lookup"><span data-stu-id="b969e-109">Transparent</span></span>|
|<span data-ttu-id="b969e-110">Versión</span><span class="sxs-lookup"><span data-stu-id="b969e-110">Version</span></span>|<span data-ttu-id="b969e-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="b969e-111">4.5.2</span></span>|
|<span data-ttu-id="b969e-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="b969e-112">Type</span></span>|<span data-ttu-id="b969e-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b969e-113">Runtime</span></span>|

