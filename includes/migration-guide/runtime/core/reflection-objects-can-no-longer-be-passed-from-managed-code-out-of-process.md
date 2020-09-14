---
ms.openlocfilehash: f011f6ebe0fa85a59f3e69c93bba9eddc4c1689b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497713"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a><span data-ttu-id="9cf9e-101">Los objetos Reflection ya no se pueden pasar desde el código administrado a los clientes DCOM fuera de proceso</span><span class="sxs-lookup"><span data-stu-id="9cf9e-101">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients</span></span>

#### <a name="details"></a><span data-ttu-id="9cf9e-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="9cf9e-102">Details</span></span>

<span data-ttu-id="9cf9e-103">Los objetos de reflexión ya no se pueden pasar desde el código administrado a los clientes DCOM fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="9cf9e-103">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients.</span></span> <span data-ttu-id="9cf9e-104">Afecta a los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="9cf9e-104">The following types are affected:</span></span>

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <span data-ttu-id="9cf9e-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (y sus tipos derivados, incluidos <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName> y <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span><span class="sxs-lookup"><span data-stu-id="9cf9e-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (and its derived types, including <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName>, and <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span></span>
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>

<span data-ttu-id="9cf9e-106">Las llamadas a <code>IMarshal</code> para el objeto devuelven <code>E_NOINTERFACE</code>.</span><span class="sxs-lookup"><span data-stu-id="9cf9e-106">Calls to <code>IMarshal</code> for the object return <code>E_NOINTERFACE</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9cf9e-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="9cf9e-107">Suggestion</span></span>

<span data-ttu-id="9cf9e-108">Actualice el código de serialización para que funcione con objetos que no sean de reflexión.</span><span class="sxs-lookup"><span data-stu-id="9cf9e-108">Update marshaling code to work with non-reflection objects.</span></span>

| <span data-ttu-id="9cf9e-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="9cf9e-109">Name</span></span>    | <span data-ttu-id="9cf9e-110">Valor</span><span class="sxs-lookup"><span data-stu-id="9cf9e-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9cf9e-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="9cf9e-111">Scope</span></span>   |<span data-ttu-id="9cf9e-112">Secundaria</span><span class="sxs-lookup"><span data-stu-id="9cf9e-112">Minor</span></span>|
|<span data-ttu-id="9cf9e-113">Versión</span><span class="sxs-lookup"><span data-stu-id="9cf9e-113">Version</span></span>|<span data-ttu-id="9cf9e-114">4.6</span><span class="sxs-lookup"><span data-stu-id="9cf9e-114">4.6</span></span>|
|<span data-ttu-id="9cf9e-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="9cf9e-115">Type</span></span>|<span data-ttu-id="9cf9e-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="9cf9e-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="9cf9e-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="9cf9e-117">Affected APIs</span></span>

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <xref:System.Reflection.FieldInfo?displayProperty=fullName>
- <xref:System.Reflection.MemberInfo?displayProperty=fullName>
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.MethodInfo?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>
- <xref:System.Reflection.TypeInfo?displayProperty=fullName>
- <xref:System.Type?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Reflection.Assembly`
- `T:System.Reflection.FieldInfo`
- `T:System.Reflection.MemberInfo`
- `T:System.Reflection.MethodBody`
- `T:System.Reflection.MethodInfo`
- `T:System.Reflection.Module`
- `T:System.Reflection.ParameterInfo`
- `T:System.Reflection.TypeInfo`
- `T:System.Type`

-->
