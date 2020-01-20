---
ms.openlocfilehash: 5612ebce67946e22aaeeba861115ce4f8967e1f5
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344452"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a><span data-ttu-id="f5893-101">Las API que notifican la versión ahora notifican la versión del producto y no la del archivo</span><span class="sxs-lookup"><span data-stu-id="f5893-101">APIs that report version now report product and not file version</span></span>

<span data-ttu-id="f5893-102">Muchas de las API que devuelven versiones en .NET Core ahora devuelven la versión del producto en lugar de la del archivo.</span><span class="sxs-lookup"><span data-stu-id="f5893-102">Many of the APIs that return versions in .NET Core now return the product version rather than the file version.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f5893-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="f5893-103">Change description</span></span>

<span data-ttu-id="f5893-104">En .NET Core 2.2 y en versiones anteriores, métodos como <xref:System.Environment.Version?displayProperty=nameWithType> y <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>, y el cuadro de diálogo de las propiedades del archivo para los ensamblados de .NET Core reflejan la versión del archivo.</span><span class="sxs-lookup"><span data-stu-id="f5893-104">In .NET Core 2.2 and previous versions, methods such as <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>, and the file properties dialog for .NET Core assemblies reflect the file version.</span></span> <span data-ttu-id="f5893-105">A partir de .NET Core 3.0, reflejan la versión del producto.</span><span class="sxs-lookup"><span data-stu-id="f5893-105">Starting with .NET Core 3.0, they reflect the product version.</span></span>

<span data-ttu-id="f5893-106">En la ilustración siguiente se muestra la diferencia en la información sobre la versión del ensamblado *System.Runtime.dll* para .NET Core 2.2 (a la izquierda) y .NET Core 3.0 (a la derecha), tal y como se muestra en los cuadros de diálogo de las propiedades del archivo de **Windows Explorer**.</span><span class="sxs-lookup"><span data-stu-id="f5893-106">The following figure illustrates the difference in version information for the *System.Runtime.dll* assembly for .NET Core 2.2 (on the left) and .NET Core 3.0 (on the right) as displayed by the **Windows Explorer** file properties dialog.</span></span>

![Diferencia en la información de la versión del producto](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a><span data-ttu-id="f5893-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f5893-108">Version introduced</span></span>

<span data-ttu-id="f5893-109">3.0</span><span class="sxs-lookup"><span data-stu-id="f5893-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f5893-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="f5893-110">Recommended action</span></span>

<span data-ttu-id="f5893-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f5893-111">None.</span></span> <span data-ttu-id="f5893-112">Este cambio debería hacer que la comprobación de la versión sea intuitiva en lugar de difícil de entender.</span><span class="sxs-lookup"><span data-stu-id="f5893-112">This change should make version detection intuitive rather than obtuse.</span></span>

#### <a name="category"></a><span data-ttu-id="f5893-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="f5893-113">Category</span></span>

<span data-ttu-id="f5893-114">CoreFX</span><span class="sxs-lookup"><span data-stu-id="f5893-114">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f5893-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f5893-115">Affected APIs</span></span>

- <xref:System.Environment.Version?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>

<!--

### Affected APIs

- `P:System.Environment.Version`
- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
