---
ms.openlocfilehash: d1ddba72ce25c5e01025d916d52f785b5a1a9e71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901701"
---
### <a name="hosting-generic-host-restricts-startup-constructor-injection"></a><span data-ttu-id="c176e-101">Hospedaje: el host genérico restringe la inserción del constructor de Startup</span><span class="sxs-lookup"><span data-stu-id="c176e-101">Hosting: Generic host restricts Startup constructor injection</span></span>

<span data-ttu-id="c176e-102">Los únicos tipos que admite el host genérico para la inserción del constructor de la clase `Startup` son `IHostEnvironment`, `IWebHostEnvironment` e `IConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="c176e-102">The only types the generic host supports for `Startup` class constructor injection are `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration`.</span></span> <span data-ttu-id="c176e-103">Las aplicaciones que usan `WebHost` no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="c176e-103">Apps using `WebHost` are unaffected.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c176e-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="c176e-104">Change description</span></span>

<span data-ttu-id="c176e-105">Antes de ASP.NET Core 3.0, se podía usar la inserción de constructores para tipos arbitrarios en el constructor de la clase `Startup`.</span><span class="sxs-lookup"><span data-stu-id="c176e-105">Prior to ASP.NET Core 3.0, constructor injection could be used for arbitrary types in the `Startup` class's constructor.</span></span> <span data-ttu-id="c176e-106">En ASP.NET Core 3.0, se ha cambiado la plataforma de la pila web a la biblioteca de host genéricos.</span><span class="sxs-lookup"><span data-stu-id="c176e-106">In ASP.NET Core 3.0, the web stack was replatformed onto the generic host library.</span></span> <span data-ttu-id="c176e-107">Puede ver el cambio en el archivo *Program.cs* de las plantillas:</span><span class="sxs-lookup"><span data-stu-id="c176e-107">You can see the change in the *Program.cs* file of the templates:</span></span>

<span data-ttu-id="c176e-108">**ASP.NET Core 2.x:**</span><span class="sxs-lookup"><span data-stu-id="c176e-108">**ASP.NET Core 2.x:**</span></span>

<https://github.com/dotnet/aspnetcore/blob/5cb615fcbe8559e49042e93394008077e30454c0/src/Templating/src/Microsoft.DotNet.Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L20-L22>

<span data-ttu-id="c176e-109">**ASP.NET Core 3.0:**</span><span class="sxs-lookup"><span data-stu-id="c176e-109">**ASP.NET Core 3.0:**</span></span>

<https://github.com/dotnet/aspnetcore/blob/b1ca2c1155da3920f0df5108b9fedbe82efaa11c/src/ProjectTemplates/Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L19-L24>

<span data-ttu-id="c176e-110">`Host` usa un contenedor de inserción de dependencias (DI) para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c176e-110">`Host` uses one dependency injection (DI) container to build the app.</span></span> <span data-ttu-id="c176e-111">`WebHost` usa dos contenedores: uno para el host y otro para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c176e-111">`WebHost` uses two containers: one for the host and one for the app.</span></span> <span data-ttu-id="c176e-112">Como resultado, el constructor de `Startup` ya no admite la inserción de servicios personalizados.</span><span class="sxs-lookup"><span data-stu-id="c176e-112">As a result, the `Startup` constructor no longer supports custom service injection.</span></span> <span data-ttu-id="c176e-113">Solo se pueden insertar `IHostEnvironment`, `IWebHostEnvironment` e `IConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="c176e-113">Only `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration` can be injected.</span></span> <span data-ttu-id="c176e-114">Este cambio evita problemas de DI, como la creación duplicada de un servicio singleton.</span><span class="sxs-lookup"><span data-stu-id="c176e-114">This change prevents DI issues such as the duplicate creation of a singleton service.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c176e-115">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="c176e-115">Version introduced</span></span>

<span data-ttu-id="c176e-116">3.0</span><span class="sxs-lookup"><span data-stu-id="c176e-116">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c176e-117">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="c176e-117">Reason for change</span></span>

<span data-ttu-id="c176e-118">Este cambio es consecuencia del cambio de plataforma de la pila web a la biblioteca de host genéricos.</span><span class="sxs-lookup"><span data-stu-id="c176e-118">This change is a consequence of replatforming the web stack onto the generic host library.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c176e-119">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="c176e-119">Recommended action</span></span>

<span data-ttu-id="c176e-120">Inserte los servicios en la firma del método `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="c176e-120">Inject services into the `Startup.Configure` method signature.</span></span> <span data-ttu-id="c176e-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c176e-121">For example:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IOptions<MyOptions> options)
```

#### <a name="category"></a><span data-ttu-id="c176e-122">Categoría</span><span class="sxs-lookup"><span data-stu-id="c176e-122">Category</span></span>

<span data-ttu-id="c176e-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c176e-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c176e-124">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c176e-124">Affected APIs</span></span>

<span data-ttu-id="c176e-125">None</span><span class="sxs-lookup"><span data-stu-id="c176e-125">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
