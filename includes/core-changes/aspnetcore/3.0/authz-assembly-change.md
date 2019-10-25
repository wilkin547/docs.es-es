---
ms.openlocfilehash: 65bac44c84589fb55d2b04c39088c2825c451a6b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393939"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a><span data-ttu-id="a620b-101">Autorización: la sobrecarga de AddAuthorization se ha cambiado a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="a620b-101">Authorization: AddAuthorization overload moved to different assembly</span></span>

<span data-ttu-id="a620b-102">Se ha cambiado a `AddAuthorizationCore` el nombre de los métodos `AddAuthorization` principales que antes se encontraban en `Microsoft.AspNetCore.Authorization`.</span><span class="sxs-lookup"><span data-stu-id="a620b-102">The core `AddAuthorization` methods that used to reside in `Microsoft.AspNetCore.Authorization` were renamed to `AddAuthorizationCore`.</span></span> <span data-ttu-id="a620b-103">Los métodos `AddAuthorization` antiguos todavía existen, pero ahora se encuentran en el paquete `Microsoft.AspNetCore.Authorization.Policy`.</span><span class="sxs-lookup"><span data-stu-id="a620b-103">The old `AddAuthorization` methods still exist, but are in the `Microsoft.AspNetCore.Authorization.Policy` package instead.</span></span> <span data-ttu-id="a620b-104">Las aplicaciones en las que se usen ambos métodos no se verán afectadas.</span><span class="sxs-lookup"><span data-stu-id="a620b-104">Apps using both methods should see no impact.</span></span> <span data-ttu-id="a620b-105">Las aplicaciones en las que no se usaba el paquete de directivas deben cambiar a `AddAuthorizationCore`.</span><span class="sxs-lookup"><span data-stu-id="a620b-105">Apps that weren't using the policy package must switch to using `AddAuthorizationCore`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a620b-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="a620b-106">Version introduced</span></span>

<span data-ttu-id="a620b-107">3.0</span><span class="sxs-lookup"><span data-stu-id="a620b-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a620b-108">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="a620b-108">Old behavior</span></span>

<span data-ttu-id="a620b-109">Los métodos `AddAuthorization` existían en `Microsoft.AspNetCore.Authorization`.</span><span class="sxs-lookup"><span data-stu-id="a620b-109">`AddAuthorization` methods existed in `Microsoft.AspNetCore.Authorization`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a620b-110">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="a620b-110">New behavior</span></span>

<span data-ttu-id="a620b-111">Los métodos `AddAuthorization` existen en `Microsoft.AspNetCore.Authorization.Policy`.</span><span class="sxs-lookup"><span data-stu-id="a620b-111">`AddAuthorization` methods exist in `Microsoft.AspNetCore.Authorization.Policy`.</span></span> <span data-ttu-id="a620b-112">`AddAuthorizationCore` es el nuevo nombre de los métodos antiguos.</span><span class="sxs-lookup"><span data-stu-id="a620b-112">`AddAuthorizationCore` is the new name for the old methods.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a620b-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="a620b-113">Reason for change</span></span>

<span data-ttu-id="a620b-114">`AddAuthorization` es un nombre de método más indicado para agregar todos los servicios comunes necesarios para la autorización.</span><span class="sxs-lookup"><span data-stu-id="a620b-114">`AddAuthorization` is a better method name for adding all common services needed for authorization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a620b-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="a620b-115">Recommended action</span></span>

<span data-ttu-id="a620b-116">Agregue una referencia a `Microsoft.AspNetCore.Authorization.Policy` o, en su lugar, use `AddAuthorizationCore`.</span><span class="sxs-lookup"><span data-stu-id="a620b-116">Either add a reference to `Microsoft.AspNetCore.Authorization.Policy` or use `AddAuthorizationCore` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="a620b-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="a620b-117">Category</span></span>

<span data-ttu-id="a620b-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a620b-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a620b-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a620b-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
