---
ms.openlocfilehash: 02c9305a36f47dfaf0b1fa8d19b07cd2d34badae
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032120"
---
### <a name="fieldinfosetvalue-throws-exception-for-static-init-only-fields"></a><span data-ttu-id="e65f1-101">FieldInfo.SetValue produce una excepción en los campos estáticos de solo inicialización</span><span class="sxs-lookup"><span data-stu-id="e65f1-101">FieldInfo.SetValue throws exception for static, init-only fields</span></span>

<span data-ttu-id="e65f1-102">A partir de .NET Core 3.0, se produce una excepción si intenta establecer un valor en un campo <xref:System.Reflection.FieldAttributes.InitOnly> estático al llamar a <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="e65f1-102">Starting in .NET Core 3.0, an exception is thrown when you attempt to set a value on a static, <xref:System.Reflection.FieldAttributes.InitOnly> field by calling <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e65f1-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="e65f1-103">Change description</span></span>

<span data-ttu-id="e65f1-104">En .NET Framework y en versiones de .NET Core anteriores a la 3.0, podía establecer el valor de un campo estático constante una vez inicializado ([readonly en C#](~/docs/csharp/language-reference/keywords/readonly.md)) mediante una llamada a <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="e65f1-104">In .NET Framework and versions of .NET Core prior to 3.0, you could set the value of a static field that's constant after it is initialized ([readonly in C#](~/docs/csharp/language-reference/keywords/readonly.md)) by calling <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="e65f1-105">Con todo, al establecer este tipo de campo de esta manera, se producía un comportamiento imprevisible en función de la plataforma de destino y la configuración de optimización.</span><span class="sxs-lookup"><span data-stu-id="e65f1-105">However, setting such a field in this way resulted in unpredictable behavior based on the target framework and optimization settings.</span></span>

<span data-ttu-id="e65f1-106">En .NET Core 3.0 y versiones posteriores, al llamar a <xref:System.Reflection.FieldInfo.SetValue%2A> en un campo <xref:System.Reflection.FieldAttributes.InitOnly> estático, se produce una excepción <xref:System.FieldAccessException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e65f1-106">In .NET Core 3.0 and later versions, when you call <xref:System.Reflection.FieldInfo.SetValue%2A> on a static, <xref:System.Reflection.FieldAttributes.InitOnly> field, a <xref:System.FieldAccessException?displayProperty=nameWithType> exception is thrown.</span></span>

> [!TIP]
> <span data-ttu-id="e65f1-107">Un campo <xref:System.Reflection.FieldAttributes.InitOnly> es uno que solo se puede establecer en el momento en que se declara o en el constructor de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="e65f1-107">An <xref:System.Reflection.FieldAttributes.InitOnly> field is one that can only be set at the time it's declared or in the constructor for the containing class.</span></span> <span data-ttu-id="e65f1-108">En otras palabras, es constante después de inicializarse.</span><span class="sxs-lookup"><span data-stu-id="e65f1-108">In other words, it's constant after it is initialized.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e65f1-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="e65f1-109">Version introduced</span></span>

<span data-ttu-id="e65f1-110">3.0</span><span class="sxs-lookup"><span data-stu-id="e65f1-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e65f1-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="e65f1-111">Recommended action</span></span>

<span data-ttu-id="e65f1-112">Inicialice los campos <xref:System.Reflection.FieldAttributes.InitOnly> estáticos en un constructor estático.</span><span class="sxs-lookup"><span data-stu-id="e65f1-112">Initialize static, <xref:System.Reflection.FieldAttributes.InitOnly> fields in a static constructor.</span></span> <span data-ttu-id="e65f1-113">Esto se aplica a los tipos dinámicos y no dinámicos.</span><span class="sxs-lookup"><span data-stu-id="e65f1-113">This applies to both dynamic and non-dynamic types.</span></span>

<span data-ttu-id="e65f1-114">Como alternativa, puede quitar el atributo <xref:System.Reflection.FieldAttributes.InitOnly?displayProperty=nameWithType> del campo y después llamar a <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e65f1-114">Alternatively, you can remove the <xref:System.Reflection.FieldAttributes.InitOnly?displayProperty=nameWithType> attribute from the field, and then call <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="e65f1-115">Categoría</span><span class="sxs-lookup"><span data-stu-id="e65f1-115">Category</span></span>

<span data-ttu-id="e65f1-116">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="e65f1-116">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e65f1-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e65f1-117">Affected APIs</span></span>

- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)?displayProperty=nameWithType>
- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)`
- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)`

-->
