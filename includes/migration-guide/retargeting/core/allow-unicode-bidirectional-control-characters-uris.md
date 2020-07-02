---
ms.openlocfilehash: 53d74db1a77e62cc64250658281fd3e4706fe494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614632"
---
### <a name="allow-unicode-bidirectional-control-characters-in-uris"></a><span data-ttu-id="1c4f3-101">Permitir caracteres de control bidireccional de Unicode en los URI</span><span class="sxs-lookup"><span data-stu-id="1c4f3-101">Allow Unicode Bidirectional Control Characters in URIs</span></span>

#### <a name="details"></a><span data-ttu-id="1c4f3-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="1c4f3-102">Details</span></span>

<span data-ttu-id="1c4f3-103">Unicode especifica varios caracteres de control especiales que se usan para especificar la orientación del texto.</span><span class="sxs-lookup"><span data-stu-id="1c4f3-103">Unicode specifies several special control characters used to specify the orientation of text.</span></span> <span data-ttu-id="1c4f3-104">En versiones anteriores de .NET Framework, estos caracteres se quitaban incorrectamente de todos los URI, incluso si ya estaban presentes en su forma codificada por porcentaje.</span><span class="sxs-lookup"><span data-stu-id="1c4f3-104">In previous versions of the .NET Framework, these characters were incorrectly stripped from all URIs even if they were present in their percent-encoded form.</span></span> <span data-ttu-id="1c4f3-105">Para seguir [RFC 3987](https://tools.ietf.org/html/rfc3987) mejor, ahora se permiten estos caracteres en los URI.</span><span class="sxs-lookup"><span data-stu-id="1c4f3-105">In order to better follow [RFC 3987](https://tools.ietf.org/html/rfc3987), we now allow these characters in URIs.</span></span> <span data-ttu-id="1c4f3-106">Cuando se encuentran sin codificar en un URI, se codifican por porcentaje.</span><span class="sxs-lookup"><span data-stu-id="1c4f3-106">When found unencoded in a URI, they are percent-encoded.</span></span> <span data-ttu-id="1c4f3-107">Cuando se encuentran codificados por porcentaje, se dejan como están.</span><span class="sxs-lookup"><span data-stu-id="1c4f3-107">When found percent-encoded they are left as-is.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1c4f3-108">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="1c4f3-108">Suggestion</span></span>

<span data-ttu-id="1c4f3-109">Para las aplicaciones destinadas a versiones de .NET Framework a partir de la 4.7.2, la compatibilidad con los caracteres bidireccionales de Unicode está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1c4f3-109">For applications that target versions of .NET Framework starting with 4.7.2, support for Unicode bidirectional characters is enabled by default.</span></span> <span data-ttu-id="1c4f3-110">Si no quiere este cambio, puede deshabilitarlo mediante la adición del modificador [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección `<runtime>` del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="1c4f3-110">If this change is undesirable, you can disable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=true" />
</runtime>
```

<span data-ttu-id="1c4f3-111">Para las aplicaciones destinadas a versiones anteriores de .NET Framework pero que se ejecutan en versiones a partir de .NET Framework 4.7.2, la compatibilidad con los caracteres bidireccionales de Unicode está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1c4f3-111">For applications that target earlier versions of the .NET Framework but are running under versions starting with .NET Framework 4.7.2, support for Unicode bidirectional characters is disabled by default.</span></span> <span data-ttu-id="1c4f3-112">Puede habilitarla mediante la adición del modificador [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección `<runtime>` del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="1c4f3-112">You can enable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file::</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=false" />
</runtime>
```

| <span data-ttu-id="1c4f3-113">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="1c4f3-113">Name</span></span>    | <span data-ttu-id="1c4f3-114">Valor</span><span class="sxs-lookup"><span data-stu-id="1c4f3-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1c4f3-115">Ámbito</span><span class="sxs-lookup"><span data-stu-id="1c4f3-115">Scope</span></span>   | <span data-ttu-id="1c4f3-116">Secundaria</span><span class="sxs-lookup"><span data-stu-id="1c4f3-116">Minor</span></span>       |
| <span data-ttu-id="1c4f3-117">Versión</span><span class="sxs-lookup"><span data-stu-id="1c4f3-117">Version</span></span> | <span data-ttu-id="1c4f3-118">4.7.2</span><span class="sxs-lookup"><span data-stu-id="1c4f3-118">4.7.2</span></span>       |
| <span data-ttu-id="1c4f3-119">Tipo</span><span class="sxs-lookup"><span data-stu-id="1c4f3-119">Type</span></span>    | <span data-ttu-id="1c4f3-120">Redestinación</span><span class="sxs-lookup"><span data-stu-id="1c4f3-120">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="1c4f3-121">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1c4f3-121">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
