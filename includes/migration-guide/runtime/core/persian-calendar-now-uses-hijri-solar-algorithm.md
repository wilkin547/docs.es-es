---
ms.openlocfilehash: e4d9efe7d2a06a1e501b070c23184dcd913dba71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621410"
---
### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a><span data-ttu-id="9abd3-101">En el calendario persa ahora se usa el algoritmo Hijri solar</span><span class="sxs-lookup"><span data-stu-id="9abd3-101">Persian calendar now uses the Hijri solar algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="9abd3-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="9abd3-102">Details</span></span>

<span data-ttu-id="9abd3-103">A partir de .NET Framework 4.6, en la clase <xref:System.Globalization.PersianCalendar?displayProperty=fullName> se usa el algoritmo Hijri solar.</span><span class="sxs-lookup"><span data-stu-id="9abd3-103">Starting with the .NET Framework 4.6, the <xref:System.Globalization.PersianCalendar?displayProperty=fullName> class uses the Hijri solar algorithm.</span></span> <span data-ttu-id="9abd3-104">La conversión de fechas entre <xref:System.Globalization.PersianCalendar?displayProperty=fullName> y otros calendarios puede producir un resultado ligeramente diferente a partir de .NET Framework 4.6 para las fechas anteriores a 1800 o posteriores a 2023 (del calendario gregoriano). Además, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> ahora es <code>March 22, 0622</code> en lugar de <code>March 21, 0622</code>.</span><span class="sxs-lookup"><span data-stu-id="9abd3-104">Converting dates between the <xref:System.Globalization.PersianCalendar?displayProperty=fullName> and other calendars may produce a slightly different result beginning with the .NET Framework 4.6 for dates earlier than 1800 or later than 2023 (Gregorian).Also, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> is now <code>March 22, 0622</code> instead of <code>March 21, 0622</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9abd3-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="9abd3-105">Suggestion</span></span>

<span data-ttu-id="9abd3-106">Tenga en cuenta que algunas fechas tempranas o tardías pueden ser ligeramente diferentes cuando se usa PersianCalendar en .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="9abd3-106">Be aware that some early or late dates may be slightly different when using the PersianCalendar in .NET Framework 4.6.</span></span> <span data-ttu-id="9abd3-107">Además, al serializar fechas entre procesos que puedan ejecutarse en diferentes versiones de .NET Framework, no las guarde como cadenas de fecha de PersianCalendar (ya que estos valores pueden ser diferentes).</span><span class="sxs-lookup"><span data-stu-id="9abd3-107">Also, when serializing dates between processes which may run on different .NET Framework versions, do not store them as PersianCalendar date strings (since those values may be different).</span></span>

| <span data-ttu-id="9abd3-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="9abd3-108">Name</span></span>    | <span data-ttu-id="9abd3-109">Valor</span><span class="sxs-lookup"><span data-stu-id="9abd3-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9abd3-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="9abd3-110">Scope</span></span>   |<span data-ttu-id="9abd3-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="9abd3-111">Minor</span></span>|
|<span data-ttu-id="9abd3-112">Versión</span><span class="sxs-lookup"><span data-stu-id="9abd3-112">Version</span></span>|<span data-ttu-id="9abd3-113">4.6</span><span class="sxs-lookup"><span data-stu-id="9abd3-113">4.6</span></span>|
|<span data-ttu-id="9abd3-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="9abd3-114">Type</span></span>|<span data-ttu-id="9abd3-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="9abd3-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9abd3-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="9abd3-116">Affected APIs</span></span>

-<xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|
