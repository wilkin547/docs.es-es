---
description: 'Más información acerca de cómo: crear zonas horarias sin reglas de ajuste'
title: Procedimiento para crear zonas horarias sin reglas de ajuste
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], adjustment rule
- time zones [.NET], creating
- adjustment rule [.NET]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
ms.openlocfilehash: c2d1f2d2ea21c53c6a3b41603be4f31ec5442a30
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99702735"
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a><span data-ttu-id="5c465-103">Procedimiento para crear zonas horarias sin reglas de ajuste</span><span class="sxs-lookup"><span data-stu-id="5c465-103">How to: Create time zones without adjustment rules</span></span>

<span data-ttu-id="5c465-104">La información precisa de zona horaria requerida por una aplicación puede no estar presente en un sistema determinado por varias razones:</span><span class="sxs-lookup"><span data-stu-id="5c465-104">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

- <span data-ttu-id="5c465-105">La zona horaria nunca se ha definido en el registro del sistema local.</span><span class="sxs-lookup"><span data-stu-id="5c465-105">The time zone has never been defined in the local system's registry.</span></span>

- <span data-ttu-id="5c465-106">Los datos sobre la zona horaria se han modificado o eliminado del registro.</span><span class="sxs-lookup"><span data-stu-id="5c465-106">Data about the time zone has been modified or removed from the registry.</span></span>

- <span data-ttu-id="5c465-107">La zona horaria existe pero no tiene información precisa sobre los ajustes de zona horaria para un determinado período histórico.</span><span class="sxs-lookup"><span data-stu-id="5c465-107">The time zone exists but does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="5c465-108">En estos casos, puede llamar al <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método para definir la zona horaria requerida por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5c465-108">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="5c465-109">Puede usar las sobrecargas de este método para crear una zona horaria con o sin reglas de ajuste.</span><span class="sxs-lookup"><span data-stu-id="5c465-109">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="5c465-110">Si la zona horaria admite el horario de verano, puede definir ajustes con reglas de ajuste fijas o flotantes.</span><span class="sxs-lookup"><span data-stu-id="5c465-110">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="5c465-111">(Para obtener definiciones de estos términos, consulte la sección "terminología de zona horaria" en [información general sobre zonas horarias](time-zone-overview.md)).</span><span class="sxs-lookup"><span data-stu-id="5c465-111">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c465-112">Las zonas horarias personalizadas creadas llamando al <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método no se agregan al registro.</span><span class="sxs-lookup"><span data-stu-id="5c465-112">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="5c465-113">En su lugar, solo se puede tener acceso a ellos a través de la referencia de objeto devuelta por la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> llamada al método.</span><span class="sxs-lookup"><span data-stu-id="5c465-113">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="5c465-114">En este tema se muestra cómo crear una zona horaria sin reglas de ajuste.</span><span class="sxs-lookup"><span data-stu-id="5c465-114">This topic shows how to create a time zone without adjustment rules.</span></span> <span data-ttu-id="5c465-115">Para crear una zona horaria que admita reglas de ajuste del horario de verano, consulte [Cómo: crear zonas horarias con reglas de ajuste](create-time-zones-with-adjustment-rules.md).</span><span class="sxs-lookup"><span data-stu-id="5c465-115">To create a time zone that supports daylight saving time adjustment rules, see [How to: Create time zones with adjustment rules](create-time-zones-with-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-without-adjustment-rules"></a><span data-ttu-id="5c465-116">Para crear una zona horaria sin reglas de ajuste</span><span class="sxs-lookup"><span data-stu-id="5c465-116">To create a time zone without adjustment rules</span></span>

1. <span data-ttu-id="5c465-117">Defina el nombre para mostrar de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="5c465-117">Define the time zone's display name.</span></span>

   <span data-ttu-id="5c465-118">El nombre para mostrar sigue un formato bastante estándar en el que el desplazamiento de la zona horaria de la hora universal coordinada (UTC) se incluye entre paréntesis y va seguido de una cadena que identifica la zona horaria, una o varias de las ciudades de la zona horaria o uno o varios de los países o regiones de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="5c465-118">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

2. <span data-ttu-id="5c465-119">Defina el nombre de la hora estándar de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="5c465-119">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="5c465-120">Normalmente, esta cadena también se usa como identificador de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="5c465-120">Typically, this string is also used as the time zone's identifier.</span></span>

3. <span data-ttu-id="5c465-121">Si desea usar un identificador diferente del nombre estándar de la zona horaria, defina el identificador de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="5c465-121">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

4. <span data-ttu-id="5c465-122">Cree una instancia <xref:System.TimeSpan> de un objeto que defina el desplazamiento de la zona horaria con respecto a la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="5c465-122">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="5c465-123">Las zonas horarias con horas que son posteriores a la hora UTC tienen un desplazamiento positivo.</span><span class="sxs-lookup"><span data-stu-id="5c465-123">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="5c465-124">Las zonas horarias con horas anteriores a la hora UTC tienen un desplazamiento negativo.</span><span class="sxs-lookup"><span data-stu-id="5c465-124">Time zones with times that are earlier than UTC have a negative offset.</span></span>

5. <span data-ttu-id="5c465-125">Llame al <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> método para crear una instancia de la nueva zona horaria.</span><span class="sxs-lookup"><span data-stu-id="5c465-125">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="5c465-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c465-126">Example</span></span>

<span data-ttu-id="5c465-127">En el ejemplo siguiente se define una zona horaria personalizada para Mawson, Antártida, que no tiene reglas de ajuste.</span><span class="sxs-lookup"><span data-stu-id="5c465-127">The following example defines a custom time zone for Mawson, Antarctica, which has no adjustment rules.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

<span data-ttu-id="5c465-128">La cadena asignada a la <xref:System.TimeZoneInfo.DisplayName%2A> propiedad sigue un formato estándar en el que el desplazamiento de la zona horaria con respecto a la hora UTC va seguido de una descripción detallada de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="5c465-128">The string assigned to the <xref:System.TimeZoneInfo.DisplayName%2A> property follows a standard format in which the time zone's offset from UTC is followed by a friendly description of the time zone.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="5c465-129">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="5c465-129">Compiling the code</span></span>

<span data-ttu-id="5c465-130">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="5c465-130">This example requires:</span></span>

- <span data-ttu-id="5c465-131">Que se importen los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="5c465-131">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="5c465-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c465-132">See also</span></span>

- [<span data-ttu-id="5c465-133">Fechas, horas y zonas horarias</span><span class="sxs-lookup"><span data-stu-id="5c465-133">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="5c465-134">Información general sobre zonas horarias</span><span class="sxs-lookup"><span data-stu-id="5c465-134">Time zone overview</span></span>](time-zone-overview.md)
- [<span data-ttu-id="5c465-135">Cómo: crear zonas horarias con reglas de ajuste</span><span class="sxs-lookup"><span data-stu-id="5c465-135">How to: Create time zones with adjustment rules</span></span>](create-time-zones-with-adjustment-rules.md)
