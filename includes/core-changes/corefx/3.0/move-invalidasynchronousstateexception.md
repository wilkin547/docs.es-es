---
ms.openlocfilehash: 19359422f79f8240676b0057c7391f6b06f961ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147554"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a><span data-ttu-id="f87d9-101">Se ha movido InvalidAsynchronousStateException a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="f87d9-101">InvalidAsynchronousStateException moved to another assembly</span></span>

<span data-ttu-id="f87d9-102">La clase <xref:System.ComponentModel.InvalidAsynchronousStateException> se ha movido.</span><span class="sxs-lookup"><span data-stu-id="f87d9-102">The <xref:System.ComponentModel.InvalidAsynchronousStateException> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f87d9-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="f87d9-103">Change description</span></span>

<span data-ttu-id="f87d9-104">En .NET Core 2.2 y en versiones anteriores, la clase <xref:System.ComponentModel.InvalidAsynchronousStateException> se encuentra en el ensamblado *System.ComponentModel.TypeConverter*.</span><span class="sxs-lookup"><span data-stu-id="f87d9-104">In .NET Core 2.2 and earlier versions, the <xref:System.ComponentModel.InvalidAsynchronousStateException> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="f87d9-105">A partir de .NET Core 3.0, se encuentra en el ensamblado *System.ComponentModel.Primitives*.</span><span class="sxs-lookup"><span data-stu-id="f87d9-105">Starting with .NET Core 3.0, it is found in the *System.ComponentModel.Primitives* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f87d9-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f87d9-106">Version introduced</span></span>

<span data-ttu-id="f87d9-107">3.0</span><span class="sxs-lookup"><span data-stu-id="f87d9-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f87d9-108">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="f87d9-108">Recommended action</span></span>

<span data-ttu-id="f87d9-109">Este cambio solo afecta a las aplicaciones que usan la reflexión para cargar <xref:System.ComponentModel.InvalidAsynchronousStateException> mediante la llamada a un método como <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>, o una sobrecarga de <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> que supone que el tipo está en un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="f87d9-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.InvalidAsynchronousStateException> by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="f87d9-110">En ese caso, el ensamblado al que se hace referencia en la llamada al método debe actualizarse para reflejar la nueva ubicación del ensamblado del tipo.</span><span class="sxs-lookup"><span data-stu-id="f87d9-110">If that is the case, the assembly the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="f87d9-111">Categoría</span><span class="sxs-lookup"><span data-stu-id="f87d9-111">Category</span></span>

<span data-ttu-id="f87d9-112">CoreFX</span><span class="sxs-lookup"><span data-stu-id="f87d9-112">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f87d9-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f87d9-113">Affected APIs</span></span>

<span data-ttu-id="f87d9-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f87d9-114">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
