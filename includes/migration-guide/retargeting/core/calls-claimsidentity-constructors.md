---
ms.openlocfilehash: b88f7d4a17f885b687d99ab9410a56039e176080
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614641"
---
### <a name="calls-to-claimsidentity-constructors"></a><span data-ttu-id="80113-101">Llamadas a los constructores de ClaimsIdentity</span><span class="sxs-lookup"><span data-stu-id="80113-101">Calls to ClaimsIdentity constructors</span></span>

#### <a name="details"></a><span data-ttu-id="80113-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="80113-102">Details</span></span>

<span data-ttu-id="80113-103">A partir de .NET Framework 4.6.2, hay un cambio en el modo en que los constructores <xref:System.Security.Claims.ClaimsIdentity> con un parámetro <xref:System.Security.Principal.IIdentity?displayProperty=fullName> establecen la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="80113-103">Starting with the .NET Framework 4.6.2, there is a change in how <xref:System.Security.Claims.ClaimsIdentity> constructors with an <xref:System.Security.Principal.IIdentity?displayProperty=fullName> parameter set the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property.</span></span> <span data-ttu-id="80113-104">Si el argumento <xref:System.Security.Principal.IIdentity?displayProperty=fullName> es un objeto <xref:System.Security.Claims.ClaimsIdentity> y la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> de ese objeto <xref:System.Security.Claims.ClaimsIdentity> no es `null`, la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> se conecta mediante el método <xref:System.Security.Claims.ClaimsIdentity.Clone>.</span><span class="sxs-lookup"><span data-stu-id="80113-104">If the <xref:System.Security.Principal.IIdentity?displayProperty=fullName> argument is a <xref:System.Security.Claims.ClaimsIdentity> object, and the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of that <xref:System.Security.Claims.ClaimsIdentity> object is not `null`, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property is attached by using the <xref:System.Security.Claims.ClaimsIdentity.Clone> method.</span></span> <span data-ttu-id="80113-105">En .NET Framework 4.6.1 y versiones anteriores, la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> se adjuntaba como una referencia existente. Debido a este cambio, a partir de .NET Framework 4.6.2, la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> del nuevo objeto <xref:System.Security.Claims.ClaimsIdentity> no es igual que la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> del argumento <xref:System.Security.Principal.IIdentity?displayProperty=fullName> del constructor.</span><span class="sxs-lookup"><span data-stu-id="80113-105">In the Framework 4.6.1 and earlier versions, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property is attached as an existing reference.Because of this change, starting with the .NET Framework 4.6.2, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of the new <xref:System.Security.Claims.ClaimsIdentity> object is not equal to the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of the constructor's <xref:System.Security.Principal.IIdentity?displayProperty=fullName> argument.</span></span> <span data-ttu-id="80113-106">En .NET Framework 4.6.1 y versiones anteriores, es igual.</span><span class="sxs-lookup"><span data-stu-id="80113-106">In the .NET Framework 4.6.1 and earlier versions, it is equal.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="80113-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="80113-107">Suggestion</span></span>

<span data-ttu-id="80113-108">Si no desea este comportamiento, puede restaurar el comportamiento anterior si establece el modificador `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` en el archivo de configuración de la aplicación en `true`.</span><span class="sxs-lookup"><span data-stu-id="80113-108">If this behavior is undesirable, you can restore the previous behavior by setting the `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` switch in your application configuration file to `true`.</span></span> <span data-ttu-id="80113-109">Para ello, es necesario agregar lo siguiente a la sección `<runtime>` del archivo web.config:</span><span class="sxs-lookup"><span data-stu-id="80113-109">This requires that you add the following to the `<runtime>` section of your web.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="80113-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="80113-110">Name</span></span>    | <span data-ttu-id="80113-111">Valor</span><span class="sxs-lookup"><span data-stu-id="80113-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="80113-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="80113-112">Scope</span></span>   | <span data-ttu-id="80113-113">Borde</span><span class="sxs-lookup"><span data-stu-id="80113-113">Edge</span></span>        |
| <span data-ttu-id="80113-114">Versión</span><span class="sxs-lookup"><span data-stu-id="80113-114">Version</span></span> | <span data-ttu-id="80113-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="80113-115">4.6.2</span></span>       |
| <span data-ttu-id="80113-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="80113-116">Type</span></span>    | <span data-ttu-id="80113-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="80113-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="80113-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="80113-118">Affected APIs</span></span>

- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity)>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim})>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim},System.String,System.String,System.String)>
