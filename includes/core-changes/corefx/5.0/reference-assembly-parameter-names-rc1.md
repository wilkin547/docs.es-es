---
ms.openlocfilehash: 760c9ce2427bc1f5e9276e66ecb6d2cf2ed83c16
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738830"
---
### <a name="parameter-names-changed-in-rc1"></a><span data-ttu-id="b4b62-101">Nombres de parámetros modificados en RC1</span><span class="sxs-lookup"><span data-stu-id="b4b62-101">Parameter names changed in RC1</span></span>

<span data-ttu-id="b4b62-102">Se han cambiado algunos nombres de parámetros de ensamblado de referencia para coincidir con los nombres de parámetro de los ensamblados de implementación.</span><span class="sxs-lookup"><span data-stu-id="b4b62-102">Some reference assembly parameter names have changed to match parameter names in the implementation assemblies.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b4b62-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="b4b62-103">Change description</span></span>

<span data-ttu-id="b4b62-104">En versiones anteriores de .NET 5.0 Preview y RC, algunos nombres de parámetros de [ensamblado de referencia](../../../../docs/standard/assembly/reference-assemblies.md) son diferentes de sus parámetros correspondientes en el ensamblado de implementación.</span><span class="sxs-lookup"><span data-stu-id="b4b62-104">In previous .NET 5.0 preview and RC versions, some [reference assembly](../../../../docs/standard/assembly/reference-assemblies.md) parameter names are different to their corresponding parameters in the implementation assembly.</span></span> <span data-ttu-id="b4b62-105">Esto puede producir problemas al usar argumentos con nombre y reflexión.</span><span class="sxs-lookup"><span data-stu-id="b4b62-105">This can cause problems while using named arguments and reflection.</span></span>

<span data-ttu-id="b4b62-106">En .NET 5.0 RC2, estos nombres de parámetros no coincidentes se han actualizado en los ensamblados de referencia para que coincidan exactamente con los nombres de parámetro correspondientes en los ensamblados de implementación.</span><span class="sxs-lookup"><span data-stu-id="b4b62-106">In .NET 5.0 RC2, these mismatched parameter names were updated in the reference assemblies to exactly match the corresponding parameter names in the implementation assemblies.</span></span>

<span data-ttu-id="b4b62-107">En esta tabla se muestran las API y los nombres de los parámetros que han cambiado.</span><span class="sxs-lookup"><span data-stu-id="b4b62-107">The following table shows the APIs and parameter names that changed.</span></span>

| <span data-ttu-id="b4b62-108">API</span><span class="sxs-lookup"><span data-stu-id="b4b62-108">API</span></span> | <span data-ttu-id="b4b62-109">Nombre del parámetro antiguo</span><span class="sxs-lookup"><span data-stu-id="b4b62-109">Old parameter name</span></span> | <span data-ttu-id="b4b62-110">Nombre del parámetro nuevo</span><span class="sxs-lookup"><span data-stu-id="b4b62-110">New parameter name</span></span> |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

#### <a name="reason-for-change"></a><span data-ttu-id="b4b62-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="b4b62-111">Reason for change</span></span>

<span data-ttu-id="b4b62-112">Los nombres de los parámetros se han cambiado por coherencia y para evitar errores al usar argumentos con nombre y reflexión.</span><span class="sxs-lookup"><span data-stu-id="b4b62-112">The parameter names were changed for consistency and to avoid failures when using named arguments and reflection.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b4b62-113">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="b4b62-113">Version introduced</span></span>

<span data-ttu-id="b4b62-114">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="b4b62-114">5.0 RC2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b4b62-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="b4b62-115">Recommended action</span></span>

<span data-ttu-id="b4b62-116">Si se produce un error del compilador debido a un cambio de nombre de un parámetro, actualice el nombre del parámetro en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="b4b62-116">If you encounter a compiler error due to a parameter name change, update the parameter name accordingly.</span></span>

#### <a name="category"></a><span data-ttu-id="b4b62-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="b4b62-117">Category</span></span>

<span data-ttu-id="b4b62-118">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="b4b62-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b4b62-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b4b62-119">Affected APIs</span></span>

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->
