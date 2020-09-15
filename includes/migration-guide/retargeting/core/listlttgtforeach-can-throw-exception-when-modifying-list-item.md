---
ms.openlocfilehash: 3300a74b81fc9eeba670ee0ceb2c2615fd3925bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617285"
---
### <a name="listlttgtforeach-can-throw-exception-when-modifying-list-item"></a><span data-ttu-id="08c28-101">List&lt;T&gt;.ForEach puede iniciar una excepción al modificar un elemento de lista</span><span class="sxs-lookup"><span data-stu-id="08c28-101">List&lt;T&gt;.ForEach can throw exception when modifying list item</span></span>

#### <a name="details"></a><span data-ttu-id="08c28-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="08c28-102">Details</span></span>

<span data-ttu-id="08c28-103">A partir de .NET Framework 4.5, un enumerador <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> iniciará una excepción <xref:System.InvalidOperationException?displayProperty=fullName> si se modifica un elemento de la colección que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="08c28-103">Beginning in .NET Framework 4.5, a <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> enumerator will throw an <xref:System.InvalidOperationException?displayProperty=fullName> exception if an element in the calling collection is modified.</span></span> <span data-ttu-id="08c28-104">En versiones anteriores no se iniciaban excepciones en estos casos, aunque sí podían producirse condiciones de carrera.</span><span class="sxs-lookup"><span data-stu-id="08c28-104">Previously, this would not throw an exception but could lead to race conditions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="08c28-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="08c28-105">Suggestion</span></span>

<span data-ttu-id="08c28-106">Lo ideal es corregir el código para no modificar listas durante la enumeración de sus elementos, ya que esta nunca es una operación segura.</span><span class="sxs-lookup"><span data-stu-id="08c28-106">Ideally, code should be fixed to not modify lists while enumerating their elements because that is never a safe operation.</span></span> <span data-ttu-id="08c28-107">Pero para revertir al comportamiento anterior, es posible seleccionar .NET Framework 4.0 como destino de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="08c28-107">To revert to the previous behavior, though, an app may target .NET Framework 4.0.</span></span>

| <span data-ttu-id="08c28-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="08c28-108">Name</span></span>    | <span data-ttu-id="08c28-109">Valor</span><span class="sxs-lookup"><span data-stu-id="08c28-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="08c28-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="08c28-110">Scope</span></span>   | <span data-ttu-id="08c28-111">Borde</span><span class="sxs-lookup"><span data-stu-id="08c28-111">Edge</span></span>        |
| <span data-ttu-id="08c28-112">Versión</span><span class="sxs-lookup"><span data-stu-id="08c28-112">Version</span></span> | <span data-ttu-id="08c28-113">4.5</span><span class="sxs-lookup"><span data-stu-id="08c28-113">4.5</span></span>         |
| <span data-ttu-id="08c28-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="08c28-114">Type</span></span>    | <span data-ttu-id="08c28-115">Redestinación</span><span class="sxs-lookup"><span data-stu-id="08c28-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="08c28-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="08c28-116">Affected APIs</span></span>

- <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType>
