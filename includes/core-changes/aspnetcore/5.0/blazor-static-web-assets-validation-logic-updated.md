---
ms.openlocfilehash: c090e99cd0569a843a4c505ad11b8da5740213e8
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440484"
---
### <a name="blazor-updated-validation-logic-for-static-web-assets"></a><span data-ttu-id="622a4-101">Blazor: Lógica de validación actualizada para los recursos web estáticos</span><span class="sxs-lookup"><span data-stu-id="622a4-101">Blazor: Updated validation logic for static web assets</span></span>

<span data-ttu-id="622a4-102">Se ha producido una incidencia en la validación de conflictos para los recursos web estáticos en ASP.NET Core 3.1 y WebAssembly 3.2 de Blazor.</span><span class="sxs-lookup"><span data-stu-id="622a4-102">There was an issue in conflict validation for static web assets in ASP.NET Core 3.1 and Blazor WebAssembly 3.2.</span></span> <span data-ttu-id="622a4-103">La incidencia es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="622a4-103">The issue:</span></span>

* <span data-ttu-id="622a4-104">Se ha impedido la detección de conflictos adecuada entre los recursos de host y los de las bibliotecas de clases de Razor (RCL) y las aplicaciones WebAssembly de Blazor.</span><span class="sxs-lookup"><span data-stu-id="622a4-104">Prevented proper conflict detection between the host assets and assets from Razor Class Libraries (RCLs) and Blazor WebAssembly apps.</span></span>
* <span data-ttu-id="622a4-105">Principalmente afecta a las aplicaciones WebAssembly de Blazor, ya que, de forma predeterminada, los recursos web estáticos de las RCL se proporcionan con el prefijo `_content/$(PackageId)`.</span><span class="sxs-lookup"><span data-stu-id="622a4-105">Mostly affects Blazor WebAssembly apps, since by default, static web assets in RCLs are served under the `_content/$(PackageId)` prefix.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="622a4-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="622a4-106">Version introduced</span></span>

<span data-ttu-id="622a4-107">5.0</span><span class="sxs-lookup"><span data-stu-id="622a4-107">5.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="622a4-108">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="622a4-108">Old behavior</span></span>

<span data-ttu-id="622a4-109">Durante el desarrollo, se podrían reemplazar de forma silenciosa los recursos web estáticos de una RCL por los del proyecto del host en la misma ruta de acceso del host.</span><span class="sxs-lookup"><span data-stu-id="622a4-109">During development, an RCL's static web assets could be silently overridden with host project assets on the same host path.</span></span> <span data-ttu-id="622a4-110">Imagine que una RCL que haya definido un recurso web estático se proporciona en */carpeta/archivo.txt*.</span><span class="sxs-lookup"><span data-stu-id="622a4-110">Consider an RCL that has defined a static web asset to be served at */folder/file.txt*.</span></span> <span data-ttu-id="622a4-111">Si el host ha colocado un archivo en *wwwroot/carpeta/archivo.txt*, el archivo del servidor ha reemplazado en modo silencioso el de la RCL o la aplicación WebAssembly de Blazor.</span><span class="sxs-lookup"><span data-stu-id="622a4-111">If the host placed a file at *wwwroot/folder/file.txt*, the file on the server silently overrode the file on the RCL or Blazor WebAssembly app.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="622a4-112">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="622a4-112">New behavior</span></span>

<span data-ttu-id="622a4-113">ASP.NET Core detecta correctamente el momento en el que se produce esta incidencia.</span><span class="sxs-lookup"><span data-stu-id="622a4-113">ASP.NET Core correctly detects when this issue happens.</span></span> <span data-ttu-id="622a4-114">Notifica el conflicto al usuario para que pueda tomar las medidas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="622a4-114">It informs you, the user, of the conflict so that you can take the appropriate action.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="622a4-115">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="622a4-115">Reason for change</span></span>

<span data-ttu-id="622a4-116">Los recursos web estáticos no se han diseñado para que se puedan reemplazar por archivos en el host *wwwroot* del proyecto.</span><span class="sxs-lookup"><span data-stu-id="622a4-116">Static web assets weren't intended to be overridable by files on the *wwwroot* host of the project.</span></span> <span data-ttu-id="622a4-117">Si se permite el reemplazo de esos archivos, se podrían producir errores difíciles de diagnosticar.</span><span class="sxs-lookup"><span data-stu-id="622a4-117">Allowing for the overriding of those files could lead to errors that are difficult to diagnose.</span></span> <span data-ttu-id="622a4-118">Como resultado, se podrían producir cambios de comportamiento no definidos en las aplicaciones publicadas.</span><span class="sxs-lookup"><span data-stu-id="622a4-118">The result could be undefined behavior changes in published apps.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="622a4-119">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="622a4-119">Recommended action</span></span>

<span data-ttu-id="622a4-120">De forma predeterminada, no hay ningún motivo por el que un archivo de RCL esté en conflicto con un archivo en el host.</span><span class="sxs-lookup"><span data-stu-id="622a4-120">By default, there's no reason for an RCL file to conflict with a file on the host.</span></span> <span data-ttu-id="622a4-121">Los archivos de RCL tienen el prefijo `_content/${PackageId}`.</span><span class="sxs-lookup"><span data-stu-id="622a4-121">RCL files are prefixed with `_content/${PackageId}`.</span></span> <span data-ttu-id="622a4-122">Los archivos WebAssembly de Blazor se colocan en la raíz del espacio de direcciones URL del host, lo que facilita los conflictos.</span><span class="sxs-lookup"><span data-stu-id="622a4-122">Blazor WebAssembly files are placed at the root of the host URL space, which makes conflicts easier.</span></span> <span data-ttu-id="622a4-123">Por ejemplo, las aplicaciones WebAssembly de Blazor contienen un archivo *favicon.ico* que el host también podría incluir en su carpeta *wwwroot*.</span><span class="sxs-lookup"><span data-stu-id="622a4-123">For example, Blazor WebAssembly apps contain a *favicon.ico* file that the host might also include in its *wwwroot* folder.</span></span>

<span data-ttu-id="622a4-124">Si el origen del conflicto es un archivo de RCL, normalmente significa que el código copia recursos de la biblioteca en la carpeta *wwwroot* del proyecto.</span><span class="sxs-lookup"><span data-stu-id="622a4-124">If the conflict's source is an RCL file, it often means code is copying assets from the library into the project's *wwwroot* folder.</span></span> <span data-ttu-id="622a4-125">La escritura de código para copiar archivos anula uno de los objetivos principales de los recursos web estáticos.</span><span class="sxs-lookup"><span data-stu-id="622a4-125">Writing code to copy files defeats a primary goal of static web assets.</span></span> <span data-ttu-id="622a4-126">Este objetivo es fundamental para obtener actualizaciones en el explorador cuando se actualiza el contenido sin tener que desencadenar una nueva compilación.</span><span class="sxs-lookup"><span data-stu-id="622a4-126">This goal is fundamental to get updates on the browser when the contents are updated without having to trigger a new compilation.</span></span>

<span data-ttu-id="622a4-127">Puede optar por conservar este comportamiento y mantener el archivo en el host.</span><span class="sxs-lookup"><span data-stu-id="622a4-127">You may choose to preserve this behavior and maintain the file on the host.</span></span> <span data-ttu-id="622a4-128">Para ello, quite el archivo de la lista de recursos web estáticos con un destino de MSBuild personalizado.</span><span class="sxs-lookup"><span data-stu-id="622a4-128">To do so, remove the file from the list of static web assets with a custom MSBuild target.</span></span>

<span data-ttu-id="622a4-129">Para usar el archivo de la RCL o el de la aplicación WebAssembly de Blazor en lugar del archivo del proyecto de host, quite el archivo del proyecto del host.</span><span class="sxs-lookup"><span data-stu-id="622a4-129">To use the RCL's file or the Blazor WebAssembly app's file instead of the host project's file, remove the file from the host project.</span></span>

#### <a name="category"></a><span data-ttu-id="622a4-130">Categoría</span><span class="sxs-lookup"><span data-stu-id="622a4-130">Category</span></span>

<span data-ttu-id="622a4-131">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="622a4-131">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="622a4-132">API afectadas</span><span class="sxs-lookup"><span data-stu-id="622a4-132">Affected APIs</span></span>

<span data-ttu-id="622a4-133">None</span><span class="sxs-lookup"><span data-stu-id="622a4-133">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
