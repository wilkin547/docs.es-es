---
ms.openlocfilehash: c5a061dffa1deb66e1769d6ec70dfa2155ac6a31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615768"
---
### <a name="calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a><span data-ttu-id="8884c-101">La llamada a CreateDefaultAuthorizationContext con un argumento NULL ha cambiado</span><span class="sxs-lookup"><span data-stu-id="8884c-101">Calling CreateDefaultAuthorizationContext with a null argument has changed</span></span>

#### <a name="details"></a><span data-ttu-id="8884c-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="8884c-102">Details</span></span>

<span data-ttu-id="8884c-103">La implementación del elemento <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=fullName> devuelto por una llamada a <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=fullName> con un argumento authorizationPolicies nulo ha cambiado su implementación en .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="8884c-103">The implementation of the <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=fullName> returned by a call to the <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=fullName> with a null authorizationPolicies argument has changed its implementation in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8884c-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="8884c-104">Suggestion</span></span>

<span data-ttu-id="8884c-105">En raras ocasiones, las aplicaciones WCF que usan la autenticación personalizada pueden sufrir diferencias de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="8884c-105">In rare cases, WCF apps that use custom authentication may see behavioral differences.</span></span> <span data-ttu-id="8884c-106">En estos casos, es posible restaurar el comportamiento anterior de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="8884c-106">In such cases, the previous behavior can be restored in either of two ways:</span></span>

- <span data-ttu-id="8884c-107">Vuelva a compilar la aplicación para que se dirija a una versión anterior a .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="8884c-107">Recompile your app to target an earlier version of the .NET Framework than 4.6.</span></span> <span data-ttu-id="8884c-108">Para los servicios hospedados en IIS, use el elemento `<httpRuntime targetFramework="x.x">` para que se dirija a una versión anterior de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8884c-108">For IIS-hosted services, use the `<httpRuntime targetFramework="x.x">` element to target an earlier version of the .NET Framework.</span></span>
- <span data-ttu-id="8884c-109">Agregue la siguiente línea a la sección `<appSettings>` del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="8884c-109">Add the following line to the `<appSettings>` section of your app.config file:</span></span>

    ```xml
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />
    ```

| <span data-ttu-id="8884c-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="8884c-110">Name</span></span>    | <span data-ttu-id="8884c-111">Valor</span><span class="sxs-lookup"><span data-stu-id="8884c-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8884c-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="8884c-112">Scope</span></span>   | <span data-ttu-id="8884c-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="8884c-113">Minor</span></span>       |
| <span data-ttu-id="8884c-114">Versión</span><span class="sxs-lookup"><span data-stu-id="8884c-114">Version</span></span> | <span data-ttu-id="8884c-115">4.6</span><span class="sxs-lookup"><span data-stu-id="8884c-115">4.6</span></span>         |
| <span data-ttu-id="8884c-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="8884c-116">Type</span></span>    | <span data-ttu-id="8884c-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="8884c-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="8884c-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8884c-118">Affected APIs</span></span>

- <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=nameWithType>
