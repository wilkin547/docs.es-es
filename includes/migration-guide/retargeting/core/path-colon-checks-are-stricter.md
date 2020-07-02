---
ms.openlocfilehash: 3e4a5936bbac4e77efc5f7e68b55ddf49bae5d43
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614716"
---
### <a name="path-colon-checks-are-stricter"></a><span data-ttu-id="99a95-101">Las comprobaciones de dos puntos de ruta de acceso son más estrictas</span><span class="sxs-lookup"><span data-stu-id="99a95-101">Path colon checks are stricter</span></span>

#### <a name="details"></a><span data-ttu-id="99a95-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="99a95-102">Details</span></span>

<span data-ttu-id="99a95-103">En .NET Framework 4.6.2, se realizaron varios cambios para admitir las rutas de acceso que anteriormente no eran compatibles (tanto en longitud como en formato).</span><span class="sxs-lookup"><span data-stu-id="99a95-103">In .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in length and format).</span></span> <span data-ttu-id="99a95-104">Se aumentó la corrección de las comprobaciones de sintaxis adecuada del separador de unidad (dos puntos), que tenía el efecto secundario de bloquear algunas rutas de acceso de URI en algunas API de ruta concretas en las que antes se toleraban.</span><span class="sxs-lookup"><span data-stu-id="99a95-104">Checks for proper drive separator (colon) syntax were made more correct, which had the side effect of blocking some URI paths in a few select Path APIs where they used to be tolerated.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="99a95-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="99a95-105">Suggestion</span></span>

<span data-ttu-id="99a95-106">Si se pasa un URI a las API afectadas, modifique la cadena para que primero sea una ruta de acceso válida.</span><span class="sxs-lookup"><span data-stu-id="99a95-106">If passing a URI to affected APIs, modify the string to be a legal path first.</span></span><ul><li><span data-ttu-id="99a95-107">Quite manualmente el esquema de las direcciones URL (por ejemplo, quite `file://`).</span><span class="sxs-lookup"><span data-stu-id="99a95-107">Remove the scheme from URLs manually (e.g. remove `file://` from URLs)</span></span>

- <span data-ttu-id="99a95-108">Pase el URI a la clase <xref:System.Uri> y use <xref:System.Uri.LocalPath>.</span><span class="sxs-lookup"><span data-stu-id="99a95-108">Pass the URI to the <xref:System.Uri> class and use <xref:System.Uri.LocalPath></span></span>

<span data-ttu-id="99a95-109">Como alternativa, puede rechazar la nueva normalización de la ruta de acceso si establece el conmutador `Switch.System.IO.UseLegacyPathHandling` de AppContext en true.</span><span class="sxs-lookup"><span data-stu-id="99a95-109">Alternatively, you can opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling` AppContext switch to true.</span></span>

| <span data-ttu-id="99a95-110">Nombre</span><span class="sxs-lookup"><span data-stu-id="99a95-110">Name</span></span>    | <span data-ttu-id="99a95-111">Valor</span><span class="sxs-lookup"><span data-stu-id="99a95-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="99a95-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="99a95-112">Scope</span></span>   | <span data-ttu-id="99a95-113">Borde</span><span class="sxs-lookup"><span data-stu-id="99a95-113">Edge</span></span>        |
| <span data-ttu-id="99a95-114">Versión</span><span class="sxs-lookup"><span data-stu-id="99a95-114">Version</span></span> | <span data-ttu-id="99a95-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="99a95-115">4.6.2</span></span>       |
| <span data-ttu-id="99a95-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="99a95-116">Type</span></span>    | <span data-ttu-id="99a95-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="99a95-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="99a95-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="99a95-118">Affected APIs</span></span>

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>
