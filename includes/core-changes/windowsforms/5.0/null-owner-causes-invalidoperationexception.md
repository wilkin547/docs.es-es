---
ms.openlocfilehash: b6cb7c4b479551ff4563998f310ff518d935f48a
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656356"
---
### <a name="datagridview-related-apis-now-throw-invalidoperationexception"></a><span data-ttu-id="129ea-101">Excepción InvalidOperationException por parte de las API relacionadas con DataGridView</span><span class="sxs-lookup"><span data-stu-id="129ea-101">DataGridView-related APIs now throw InvalidOperationException</span></span>

<span data-ttu-id="129ea-102">Algunas API relacionadas con <xref:System.Windows.Forms.DataGridView> ahora producen una excepción <xref:System.InvalidOperationException> si el valor <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner?displayProperty=nameWithType> del objeto es `null`.</span><span class="sxs-lookup"><span data-stu-id="129ea-102">Some APIs related to <xref:System.Windows.Forms.DataGridView> now throw an <xref:System.InvalidOperationException> if the object's <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner?displayProperty=nameWithType> value is `null`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="129ea-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="129ea-103">Change description</span></span>

<span data-ttu-id="129ea-104">En las versiones anteriores de .NET, las API afectadas inician una excepción <xref:System.NullReferenceException> cuando se invocan y el valor de <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> es `null`.</span><span class="sxs-lookup"><span data-stu-id="129ea-104">In previous .NET versions, the affected APIs throw a <xref:System.NullReferenceException> when they are invoked and the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> value is `null`.</span></span> <span data-ttu-id="129ea-105">A partir de .NET 5.0, estas API inician una excepción <xref:System.InvalidOperationException> en lugar de una excepción <xref:System.NullReferenceException> si el valor de <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> es `null` cuando se invocan.</span><span class="sxs-lookup"><span data-stu-id="129ea-105">Starting in .NET 5.0, these APIs throw an <xref:System.InvalidOperationException> instead of a <xref:System.NullReferenceException> if the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> value is `null` when they are invoked.</span></span>

<span data-ttu-id="129ea-106">El inicio de una <xref:System.InvalidOperationException> se ajusta al comportamiento del tiempo de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="129ea-106">Throwing an <xref:System.InvalidOperationException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="129ea-107">También mejora la experiencia de depuración al comunicar claramente qué propiedad no es válida.</span><span class="sxs-lookup"><span data-stu-id="129ea-107">It also improves the debugging experience by clearly communicating the invalid property.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="129ea-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="129ea-108">Version introduced</span></span>

<span data-ttu-id="129ea-109">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="129ea-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="129ea-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="129ea-110">Recommended action</span></span>

<span data-ttu-id="129ea-111">Revise el código y, si es necesario, actualícelo para evitar la construcción de los tipos afectados con la propiedad <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> como `null`.</span><span class="sxs-lookup"><span data-stu-id="129ea-111">Review your code and, if necessary, update it to prevent constructing the affected types with the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> property as `null`.</span></span>

#### <a name="category"></a><span data-ttu-id="129ea-112">Categoría</span><span class="sxs-lookup"><span data-stu-id="129ea-112">Category</span></span>

<span data-ttu-id="129ea-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="129ea-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="129ea-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="129ea-114">Affected APIs</span></span>

<span data-ttu-id="129ea-115">En la tabla siguiente se enumeran las propiedades y los parámetros afectados:</span><span class="sxs-lookup"><span data-stu-id="129ea-115">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="129ea-116">Propiedad o método afectado</span><span class="sxs-lookup"><span data-stu-id="129ea-116">Affected method or property</span></span> | <span data-ttu-id="129ea-117">Propiedad validada</span><span class="sxs-lookup"><span data-stu-id="129ea-117">Validated property</span></span> | <span data-ttu-id="129ea-118">Versión agregada</span><span class="sxs-lookup"><span data-stu-id="129ea-118">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.DataGridViewButtonCell.DataGridViewButtonCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="129ea-119">5.0</span><span class="sxs-lookup"><span data-stu-id="129ea-119">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="129ea-120">5.0</span><span class="sxs-lookup"><span data-stu-id="129ea-120">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.State?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="129ea-121">5.0</span><span class="sxs-lookup"><span data-stu-id="129ea-121">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="129ea-122">5.0</span><span class="sxs-lookup"><span data-stu-id="129ea-122">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Bounds?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="129ea-123">5.0</span><span class="sxs-lookup"><span data-stu-id="129ea-123">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="129ea-124">5.0</span><span class="sxs-lookup"><span data-stu-id="129ea-124">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Name?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="129ea-125">5.0</span><span class="sxs-lookup"><span data-stu-id="129ea-125">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Parent?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="129ea-126">5.0</span><span class="sxs-lookup"><span data-stu-id="129ea-126">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="129ea-127">5.0</span><span class="sxs-lookup"><span data-stu-id="129ea-127">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Navigate(System.Windows.Forms.AccessibleNavigation)?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="129ea-128">5.0</span><span class="sxs-lookup"><span data-stu-id="129ea-128">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewImageCell.DataGridViewImageCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="129ea-129">5.0</span><span class="sxs-lookup"><span data-stu-id="129ea-129">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="129ea-130">5.0</span><span class="sxs-lookup"><span data-stu-id="129ea-130">5.0</span></span> |

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.DataGridViewButtonCell.DataGridViewButtonCellAccessibleObject.DoDefaultAction`
- `P:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DefaultAction`
- `P:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.State`
- `M:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DoDefaultAction`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Bounds`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DefaultAction`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Name`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Parent`
- `M:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DoDefaultAction`
- `M:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Navigate(System.Windows.Forms.AccessibleNavigation)`
- `M:System.Windows.Forms.DataGridViewImageCell.DataGridViewImageCellAccessibleObject.DoDefaultAction`
- `M:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject.DoDefaultAction`

-->
