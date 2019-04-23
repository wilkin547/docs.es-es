---
ms.openlocfilehash: 4e81087431091dfa4d5432d5ea5e2b665be2b130
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774406"
---
### <a name="listtforeach-can-throw-exception-when-modifying-list-item"></a><span data-ttu-id="a8b99-101">List\<T>.ForEach puede iniciar una excepción al modificar un elemento de lista</span><span class="sxs-lookup"><span data-stu-id="a8b99-101">List\<T>.ForEach can throw exception when modifying list item</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a8b99-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="a8b99-102">Details</span></span>|<span data-ttu-id="a8b99-103">A partir de .NET Framework 4.5, un enumerador <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> iniciará una excepción <xref:System.InvalidOperationException?displayProperty=name> si se modifica un elemento de la colección que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="a8b99-103">Beginning in .NET Framework 4.5, a <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> enumerator will throw an <xref:System.InvalidOperationException?displayProperty=name> exception if an element in the calling collection is modified.</span></span> <span data-ttu-id="a8b99-104">En versiones anteriores no se iniciaban excepciones en estos casos, aunque sí podían producirse condiciones de carrera.</span><span class="sxs-lookup"><span data-stu-id="a8b99-104">Previously, this would not throw an exception but could lead to race conditions.</span></span>|
|<span data-ttu-id="a8b99-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="a8b99-105">Suggestion</span></span>|<span data-ttu-id="a8b99-106">Lo ideal es corregir el código para no modificar listas durante la enumeración de sus elementos, ya que esta nunca es una operación segura.</span><span class="sxs-lookup"><span data-stu-id="a8b99-106">Ideally, code should be fixed to not modify lists while enumerating their elements because that is never a safe operation.</span></span> <span data-ttu-id="a8b99-107">Pero para revertir al comportamiento anterior, es posible seleccionar .NET Framework 4.0 como destino de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="a8b99-107">To revert to the previous behavior, though, an app may target .NET Framework 4.0.</span></span>|
|<span data-ttu-id="a8b99-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="a8b99-108">Scope</span></span>|<span data-ttu-id="a8b99-109">Borde</span><span class="sxs-lookup"><span data-stu-id="a8b99-109">Edge</span></span>|
|<span data-ttu-id="a8b99-110">Versión</span><span class="sxs-lookup"><span data-stu-id="a8b99-110">Version</span></span>|<span data-ttu-id="a8b99-111">4.5</span><span class="sxs-lookup"><span data-stu-id="a8b99-111">4.5</span></span>|
|<span data-ttu-id="a8b99-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="a8b99-112">Type</span></span>|<span data-ttu-id="a8b99-113">Redestinación</span><span class="sxs-lookup"><span data-stu-id="a8b99-113">Retargeting</span></span>|
|<span data-ttu-id="a8b99-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a8b99-114">Affected APIs</span></span>|<ul><li><xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType></li></ul>|
