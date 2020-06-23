---
ms.openlocfilehash: f42da00487735acdcc60f876c75e1dfd17103008
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702457"
---
### <a name="winforms-properties-now-throw-argumentoutofrangeexception"></a><span data-ttu-id="e3618-101">Ahora, las propiedades de WinForms producen ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="e3618-101">WinForms properties now throw ArgumentOutOfRangeException</span></span>

<span data-ttu-id="e3618-102">Algunas propiedades de Windows Forms inician ahora una excepción <xref:System.ArgumentOutOfRangeException> en los argumentos no válidos, donde antes no lo hacían.</span><span class="sxs-lookup"><span data-stu-id="e3618-102">Some Windows Forms properties now throw an <xref:System.ArgumentOutOfRangeException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e3618-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="e3618-103">Change description</span></span>

<span data-ttu-id="e3618-104">Anteriormente, estas propiedades producían varias excepciones, como <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException>o <xref:System.ArgumentException>, cuando se pasaban argumentos fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="e3618-104">Previously, these properties threw various exceptions, such as <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException>, or <xref:System.ArgumentException>, when passed out-of-range arguments.</span></span> <span data-ttu-id="e3618-105">A partir de .NET 5.0, estas propiedades producen ahora <xref:System.ArgumentOutOfRangeException> cuando se pasan argumentos que están fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="e3618-105">Starting in .NET 5.0, these properties now throw an <xref:System.ArgumentOutOfRangeException> when passed arguments that are out of range.</span></span>

<span data-ttu-id="e3618-106">El inicio de una <xref:System.ArgumentOutOfRangeException> se ajusta al comportamiento del tiempo de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="e3618-106">Throwing an <xref:System.ArgumentOutOfRangeException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="e3618-107">También mejora la experiencia de depuración al comunicar claramente qué argumento no es válido.</span><span class="sxs-lookup"><span data-stu-id="e3618-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e3618-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="e3618-108">Version introduced</span></span>

<span data-ttu-id="e3618-109">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="e3618-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e3618-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="e3618-110">Recommended action</span></span>

- <span data-ttu-id="e3618-111">Actualice el código para evitar pasar argumentos no válidos.</span><span class="sxs-lookup"><span data-stu-id="e3618-111">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="e3618-112">Si es necesario, administre un elemento <xref:System.ArgumentOutOfRangeException> al establecer la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e3618-112">If necessary, handle an <xref:System.ArgumentOutOfRangeException> when setting the property.</span></span>

#### <a name="category"></a><span data-ttu-id="e3618-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="e3618-113">Category</span></span>

<span data-ttu-id="e3618-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e3618-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e3618-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e3618-115">Affected APIs</span></span>

<span data-ttu-id="e3618-116">En la tabla siguiente se enumeran las propiedades y los parámetros afectados:</span><span class="sxs-lookup"><span data-stu-id="e3618-116">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="e3618-117">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="e3618-117">Property</span></span> | <span data-ttu-id="e3618-118">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="e3618-118">Parameter name</span></span> | <span data-ttu-id="e3618-119">Versión agregada</span><span class="sxs-lookup"><span data-stu-id="e3618-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)?displayProperty=nameWithType> | `index` | <span data-ttu-id="e3618-120">5.0 (versión preliminar 5)</span><span class="sxs-lookup"><span data-stu-id="e3618-120">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.TreeNode.ImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="e3618-121">5.0 (versión preliminar 6)</span><span class="sxs-lookup"><span data-stu-id="e3618-121">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.TreeNode.SelectedImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="e3618-122">5.0 (versión preliminar 6)</span><span class="sxs-lookup"><span data-stu-id="e3618-122">5.0 Preview 6</span></span> |

<!-- 

#### Affected APIs

- `P:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)`
- `P:System.Windows.Forms.TreeNode.ImageIndex`
- `P:System.Windows.Forms.TreeNode.SelectedImageIndex`

-->
