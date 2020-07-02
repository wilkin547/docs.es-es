---
ms.openlocfilehash: 22b5abbe769733e8d5ca3e78dd9e6e13b2363737
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620617"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="494b9-101">Permitir interrupción para revertir desde otra generación de SQL de la versión 4.5 a la generación de SQL más sencilla de la versión 4.0</span><span class="sxs-lookup"><span data-stu-id="494b9-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

#### <a name="details"></a><span data-ttu-id="494b9-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="494b9-102">Details</span></span>

<span data-ttu-id="494b9-103">Las consultas que generan instrucciones JOIN y contienen una llamada a una operación de limitación sin usar primero OrderBy, ahora generan código SQL más sencillo.</span><span class="sxs-lookup"><span data-stu-id="494b9-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="494b9-104">Después de actualizar a .NET Framework 4.5, estas consultas generaban código SQL más complicado que en versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="494b9-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="494b9-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="494b9-105">Suggestion</span></span>

<span data-ttu-id="494b9-106">Esta característica está deshabilitada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="494b9-106">This feature is disabled by default.</span></span> <span data-ttu-id="494b9-107">Si Entity Framework genera instrucciones JOIN adicionales que causan la degradación del rendimiento, puede habilitar esta característica mediante la adición de la entrada siguiente a la sección <code>&lt;appSettings&gt;</code> del archivo de configuración de la aplicación (app.config):</span><span class="sxs-lookup"><span data-stu-id="494b9-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="494b9-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="494b9-108">Name</span></span>    | <span data-ttu-id="494b9-109">Valor</span><span class="sxs-lookup"><span data-stu-id="494b9-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="494b9-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="494b9-110">Scope</span></span>   |<span data-ttu-id="494b9-111">Transparente</span><span class="sxs-lookup"><span data-stu-id="494b9-111">Transparent</span></span>|
|<span data-ttu-id="494b9-112">Versión</span><span class="sxs-lookup"><span data-stu-id="494b9-112">Version</span></span>|<span data-ttu-id="494b9-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="494b9-113">4.5.2</span></span>|
|<span data-ttu-id="494b9-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="494b9-114">Type</span></span>|<span data-ttu-id="494b9-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="494b9-115">Runtime</span></span>|
