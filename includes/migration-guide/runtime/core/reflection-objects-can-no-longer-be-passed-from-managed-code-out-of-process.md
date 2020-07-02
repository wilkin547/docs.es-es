---
ms.openlocfilehash: a54b17b2002bd0f85b8b47c5e37e040470d6c494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621434"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a><span data-ttu-id="9b4d1-101">Los objetos Reflection ya no se pueden pasar desde el código administrado a los clientes DCOM fuera de proceso</span><span class="sxs-lookup"><span data-stu-id="9b4d1-101">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients</span></span>

#### <a name="details"></a><span data-ttu-id="9b4d1-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="9b4d1-102">Details</span></span>

<span data-ttu-id="9b4d1-103">Los objetos de reflexión ya no se pueden pasar desde el código administrado a los clientes DCOM fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-103">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients.</span></span> <span data-ttu-id="9b4d1-104">Afecta a los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="9b4d1-104">The following types are affected:</span></span><ul><li><xref:System.Reflection.Assembly?displayProperty=fullName></li><li><span data-ttu-id="9b4d1-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (y sus tipos derivados, incluidos <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName> y <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span><span class="sxs-lookup"><span data-stu-id="9b4d1-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (and its derived types, including <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName>, and <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span></span></li><li><xref:System.Reflection.MethodBody?displayProperty=fullName></li><li><xref:System.Reflection.Module?displayProperty=fullName></li><li><span data-ttu-id="9b4d1-106"><xref:System.Reflection.ParameterInfo?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-106"><xref:System.Reflection.ParameterInfo?displayProperty=fullName>.</span></span></li></ul><span data-ttu-id="9b4d1-107">Las llamadas a <code>IMarshal</code> para el objeto devuelven <code>E_NOINTERFACE</code>.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-107">Calls to <code>IMarshal</code> for the object return <code>E_NOINTERFACE</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9b4d1-108">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="9b4d1-108">Suggestion</span></span>

<span data-ttu-id="9b4d1-109">Actualice el código de serialización para que funcione con objetos distintos a Reflection.</span><span class="sxs-lookup"><span data-stu-id="9b4d1-109">Update marshaling code to work with non-reflection objects</span></span>

| <span data-ttu-id="9b4d1-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="9b4d1-110">Name</span></span>    | <span data-ttu-id="9b4d1-111">Valor</span><span class="sxs-lookup"><span data-stu-id="9b4d1-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9b4d1-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="9b4d1-112">Scope</span></span>   |<span data-ttu-id="9b4d1-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="9b4d1-113">Minor</span></span>|
|<span data-ttu-id="9b4d1-114">Versión</span><span class="sxs-lookup"><span data-stu-id="9b4d1-114">Version</span></span>|<span data-ttu-id="9b4d1-115">4.6</span><span class="sxs-lookup"><span data-stu-id="9b4d1-115">4.6</span></span>|
|<span data-ttu-id="9b4d1-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="9b4d1-116">Type</span></span>|<span data-ttu-id="9b4d1-117">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="9b4d1-117">Runtime</span></span>|
