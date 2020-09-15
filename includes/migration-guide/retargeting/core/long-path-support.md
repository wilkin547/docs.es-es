---
ms.openlocfilehash: 67e3ff5000ebd38064ed8a57e4fe561afa31f8d8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614713"
---
### <a name="long-path-support"></a><span data-ttu-id="6083a-101">Compatibilidad con rutas de acceso con formato largo</span><span class="sxs-lookup"><span data-stu-id="6083a-101">Long path support</span></span>

#### <a name="details"></a><span data-ttu-id="6083a-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6083a-102">Details</span></span>

<span data-ttu-id="6083a-103">A partir de las aplicaciones destinadas a .NET Framework 4.6.2, se admiten las rutas de acceso largas (de hasta 32 000 caracteres) y se ha quitado la limitación de 260 caracteres (o `MAX_PATH`) para las longitudes de ruta de acceso. Para las aplicaciones que se vuelven a compilar para .NET Framework 4.6.2, las rutas de acceso de código que antes iniciaban una excepción <xref:System.IO.PathTooLongException?displayProperty=fullName> porque una ruta de acceso superaba los 260 caracteres ahora iniciarán una excepción <xref:System.IO.PathTooLongException?displayProperty=fullName> solo en las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6083a-103">Starting with apps that target the .NET Framework 4.6.2, long paths (of up to 32K characters) are supported, and the 260-character (or `MAX_PATH`) limitation on path lengths has been removed.For apps that are recompiled to target the .NET Framework 4.6.2, code paths that previously threw a <xref:System.IO.PathTooLongException?displayProperty=fullName> because a path exceeded 260 characters will now throw a <xref:System.IO.PathTooLongException?displayProperty=fullName> only under the following conditions:</span></span>

- <span data-ttu-id="6083a-104">La longitud de la ruta de acceso es mayor que <xref:System.Int16.MaxValue> (32 767) caracteres.</span><span class="sxs-lookup"><span data-stu-id="6083a-104">The length of the path is greater than <xref:System.Int16.MaxValue> (32,767) characters.</span></span>
- <span data-ttu-id="6083a-105">El sistema operativo devuelve `COR_E_PATHTOOLONG` o su equivalente.</span><span class="sxs-lookup"><span data-stu-id="6083a-105">The operating system returns `COR_E_PATHTOOLONG` or its equivalent.</span></span>
<span data-ttu-id="6083a-106">Para las aplicaciones que tienen como destino .NET Framework 4.6.1 y versiones anteriores, el entorno de ejecución inicia automáticamente una excepción <xref:System.IO.PathTooLongException?displayProperty=fullName> cada vez que una ruta de acceso supera los 260 caracteres.</span><span class="sxs-lookup"><span data-stu-id="6083a-106">For apps that target the .NET Framework 4.6.1 and earlier versions, the runtime automatically throws a <xref:System.IO.PathTooLongException?displayProperty=fullName> whenever a path exceeds 260 characters.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6083a-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6083a-107">Suggestion</span></span>

<span data-ttu-id="6083a-108">Para las aplicaciones que tienen como destino .NET Framework 4.6.2, se puede rechazar la compatibilidad con rutas de acceso largas si no es adecuada si se agrega lo siguiente a la sección `<runtime>` del archivo `app.config`:</span><span class="sxs-lookup"><span data-stu-id="6083a-108">For apps that target the .NET Framework 4.6.2, you can opt out of long path support if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />
</runtime>
```

<span data-ttu-id="6083a-109">Para las aplicaciones que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en .NET Framework 4.6.2 o versiones posteriores, se puede incluir la compatibilidad con rutas de acceso largas si se agrega lo siguiente a la sección `<runtime>` del archivo `app.config`:</span><span class="sxs-lookup"><span data-stu-id="6083a-109">For apps that target earlier versions of the .NET Framework but run on the .NET Framework 4.6.2 or later, you can opt in to long path support by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />
</runtime>
```

| <span data-ttu-id="6083a-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6083a-110">Name</span></span>    | <span data-ttu-id="6083a-111">Valor</span><span class="sxs-lookup"><span data-stu-id="6083a-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6083a-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6083a-112">Scope</span></span>   | <span data-ttu-id="6083a-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="6083a-113">Minor</span></span>       |
| <span data-ttu-id="6083a-114">Versión</span><span class="sxs-lookup"><span data-stu-id="6083a-114">Version</span></span> | <span data-ttu-id="6083a-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="6083a-115">4.6.2</span></span>       |
| <span data-ttu-id="6083a-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="6083a-116">Type</span></span>    | <span data-ttu-id="6083a-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="6083a-117">Retargeting</span></span> |
