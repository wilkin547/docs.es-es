---
ms.openlocfilehash: c8f44ae1a500ed240dbff7d9a2c1479af368b7f1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394066"
---
### <a name="identity-default-bootstrap-version-of-ui-changed"></a><span data-ttu-id="b0d1d-101">Identity: se ha cambiado la versión de Bootstrap predeterminada de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="b0d1d-101">Identity: Default Bootstrap version of UI changed</span></span>

<span data-ttu-id="b0d1d-102">A partir de ASP.NET Core 3.0, la interfaz de usuario de Identity tiene como valor predeterminado el uso de la versión 4 de Bootstrap.</span><span class="sxs-lookup"><span data-stu-id="b0d1d-102">Starting in ASP.NET Core 3.0, Identity UI defaults to using version 4 of Bootstrap.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b0d1d-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="b0d1d-103">Version introduced</span></span>

<span data-ttu-id="b0d1d-104">3.0</span><span class="sxs-lookup"><span data-stu-id="b0d1d-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b0d1d-105">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="b0d1d-105">Old behavior</span></span>

<span data-ttu-id="b0d1d-106">La llamada al método `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` era la misma que en `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);`.</span><span class="sxs-lookup"><span data-stu-id="b0d1d-106">The `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` method call was the same as `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);`</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b0d1d-107">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="b0d1d-107">New behavior</span></span>

<span data-ttu-id="b0d1d-108">La llamada al método `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` es la misma que en `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap4);`.</span><span class="sxs-lookup"><span data-stu-id="b0d1d-108">The `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` method call is the same as `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap4);`</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b0d1d-109">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="b0d1d-109">Reason for change</span></span>

<span data-ttu-id="b0d1d-110">Bootstrap 4 se lanzó durante el periodo de tiempo de ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b0d1d-110">Bootstrap 4 was released during ASP.NET Core 3.0 timeframe.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b0d1d-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="b0d1d-111">Recommended action</span></span>

<span data-ttu-id="b0d1d-112">En el caso de que use la interfaz de usuario predeterminada de Identity y la haya agregado en `Startup.ConfigureServices`, este cambio le afectará, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b0d1d-112">You're impacted by this change if you use the default Identity UI and have added it in `Startup.ConfigureServices` as shown in the following example:</span></span>

```csharp
services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();
```

<span data-ttu-id="b0d1d-113">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b0d1d-113">Take one of the following actions:</span></span>

- <span data-ttu-id="b0d1d-114">Migre su aplicación para usar Bootstrap 4 usando la [guía de migración](https://getbootstrap.com/docs/4.0/migration).</span><span class="sxs-lookup"><span data-stu-id="b0d1d-114">Migrate your app to use Bootstrap 4 using their [migration guide](https://getbootstrap.com/docs/4.0/migration).</span></span>
- <span data-ttu-id="b0d1d-115">Actualice `Startup.ConfigureServices` para forzar el uso de Bootstrap 3.</span><span class="sxs-lookup"><span data-stu-id="b0d1d-115">Update `Startup.ConfigureServices` to enforce usage of Bootstrap 3.</span></span> <span data-ttu-id="b0d1d-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b0d1d-116">For example:</span></span>

    ```csharp
    services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);
    ```

#### <a name="category"></a><span data-ttu-id="b0d1d-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="b0d1d-117">Category</span></span>

<span data-ttu-id="b0d1d-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b0d1d-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b0d1d-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b0d1d-119">Affected APIs</span></span>

<span data-ttu-id="b0d1d-120">None</span><span class="sxs-lookup"><span data-stu-id="b0d1d-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
