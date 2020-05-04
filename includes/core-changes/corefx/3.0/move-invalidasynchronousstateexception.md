---
ms.openlocfilehash: d1562cb76f37b6cc2aeb6fe2f7c17c393e169e84
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158491"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a><span data-ttu-id="c4281-101">Se ha movido InvalidAsynchronousStateException a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="c4281-101">InvalidAsynchronousStateException moved to another assembly</span></span>

<span data-ttu-id="c4281-102">La clase <xref:System.ComponentModel.InvalidAsynchronousStateException> se ha movido.</span><span class="sxs-lookup"><span data-stu-id="c4281-102">The <xref:System.ComponentModel.InvalidAsynchronousStateException> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c4281-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="c4281-103">Change description</span></span>

<span data-ttu-id="c4281-104">En .NET Core 2.2 y en versiones anteriores, la clase <xref:System.ComponentModel.InvalidAsynchronousStateException> se encuentra en el ensamblado *System.ComponentModel.TypeConverter*.</span><span class="sxs-lookup"><span data-stu-id="c4281-104">In .NET Core 2.2 and earlier versions, the <xref:System.ComponentModel.InvalidAsynchronousStateException> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="c4281-105">A partir de .NET Core 3.0, se encuentra en el ensamblado *System.ComponentModel.Primitives*.</span><span class="sxs-lookup"><span data-stu-id="c4281-105">Starting with .NET Core 3.0, it is found in the *System.ComponentModel.Primitives* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c4281-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="c4281-106">Version introduced</span></span>

<span data-ttu-id="c4281-107">3.0</span><span class="sxs-lookup"><span data-stu-id="c4281-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c4281-108">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="c4281-108">Recommended action</span></span>

<span data-ttu-id="c4281-109">Este cambio solo afecta a las aplicaciones que usan la reflexión para cargar <xref:System.ComponentModel.InvalidAsynchronousStateException> mediante la llamada a un método como <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>, o una sobrecarga de <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> que supone que el tipo está en un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="c4281-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.InvalidAsynchronousStateException> by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="c4281-110">En ese caso, actualice el ensamblado al que se hace referencia en la llamada de método para reflejar la nueva ubicación del ensamblado del tipo.</span><span class="sxs-lookup"><span data-stu-id="c4281-110">If that is the case, update the assembly referenced in the method call to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="c4281-111">Categoría</span><span class="sxs-lookup"><span data-stu-id="c4281-111">Category</span></span>

<span data-ttu-id="c4281-112">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="c4281-112">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c4281-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c4281-113">Affected APIs</span></span>

<span data-ttu-id="c4281-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c4281-114">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
