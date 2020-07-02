---
ms.openlocfilehash: af10716fe5f4c07091e8605cdf620e4a499fb1e8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620546"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a><span data-ttu-id="f53a4-101">No se debe usar IPad en el archivo de funciones personalizado porque ahora es una funcionalidad del explorador</span><span class="sxs-lookup"><span data-stu-id="f53a4-101">IPad should not be used in custom capabilities file because it is now a browser capability</span></span>

#### <a name="details"></a><span data-ttu-id="f53a4-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="f53a4-102">Details</span></span>

<span data-ttu-id="f53a4-103">A partir de .NET Framework 4.5, iPad es un identificador en el archivo de funciones de explorador de ASP.NET predeterminado, por lo que no se debe usar en un archivo de funciones personalizado.</span><span class="sxs-lookup"><span data-stu-id="f53a4-103">Beginning in .NET Framework 4.5, iPad is an identifier in the default ASP.NET browser capabilities file, so it should not be used in a custom capabilities file</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f53a4-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="f53a4-104">Suggestion</span></span>

<span data-ttu-id="f53a4-105">Si se requieren funciones específicas de iPad, es necesario modificar el comportamiento de iPad estableciéndolas en el refID &quot;IPad&quot; de puerta de enlace predefinido en lugar de mediante la generación de un nuevo id. &quot;IPad&quot; mediante la búsqueda de coincidencias de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="f53a4-105">If iPad-specific capabilities are required, it is necessary to modify iPad behavior by setting capabilities on the pre-defined gateway refID &quot;IPad&quot; instead of by generating a new &quot;IPad&quot; ID by user agent matching.</span></span>

| <span data-ttu-id="f53a4-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="f53a4-106">Name</span></span>    | <span data-ttu-id="f53a4-107">Valor</span><span class="sxs-lookup"><span data-stu-id="f53a4-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f53a4-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="f53a4-108">Scope</span></span>   |<span data-ttu-id="f53a4-109">Borde</span><span class="sxs-lookup"><span data-stu-id="f53a4-109">Edge</span></span>|
|<span data-ttu-id="f53a4-110">Versión</span><span class="sxs-lookup"><span data-stu-id="f53a4-110">Version</span></span>|<span data-ttu-id="f53a4-111">4.5</span><span class="sxs-lookup"><span data-stu-id="f53a4-111">4.5</span></span>|
|<span data-ttu-id="f53a4-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="f53a4-112">Type</span></span>|<span data-ttu-id="f53a4-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f53a4-113">Runtime</span></span>|
