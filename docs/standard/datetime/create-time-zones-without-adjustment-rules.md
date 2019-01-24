---
title: Procedimiento Crear zonas horarias sin reglas de ajuste
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb3ffc7b6f1f7baec7ce6beb5a50b706ff78bfa1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681721"
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a><span data-ttu-id="9940b-102">Procedimiento Crear zonas horarias sin reglas de ajuste</span><span class="sxs-lookup"><span data-stu-id="9940b-102">How to: Create time zones without adjustment rules</span></span>

<span data-ttu-id="9940b-103">La información de zona horaria exacta requerida por una aplicación puede no encontrarse en un sistema determinado por varias razones:</span><span class="sxs-lookup"><span data-stu-id="9940b-103">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

* <span data-ttu-id="9940b-104">Nunca se definió la zona horaria en el registro del sistema local.</span><span class="sxs-lookup"><span data-stu-id="9940b-104">The time zone has never been defined in the local system's registry.</span></span>

* <span data-ttu-id="9940b-105">Datos sobre la zona horaria se ha modificado o quitado del registro.</span><span class="sxs-lookup"><span data-stu-id="9940b-105">Data about the time zone has been modified or removed from the registry.</span></span>

* <span data-ttu-id="9940b-106">La zona horaria existe pero no tiene información precisa sobre los ajustes de zona horaria para un período histórico determinado.</span><span class="sxs-lookup"><span data-stu-id="9940b-106">The time zone exists but does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="9940b-107">En estos casos, puede llamar a la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método para definir la zona horaria requerida por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9940b-107">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="9940b-108">Puede utilizar las sobrecargas de este método para crear una zona horaria con o sin reglas de ajuste.</span><span class="sxs-lookup"><span data-stu-id="9940b-108">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="9940b-109">Si la zona horaria admite el horario de verano, puede definir los ajustes con cualquier reglas de ajuste fija o flotante.</span><span class="sxs-lookup"><span data-stu-id="9940b-109">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="9940b-110">(Para obtener definiciones de estos términos, vea la sección "Terminología de zona horaria" en [Introducción a zona horaria](../../../docs/standard/datetime/time-zone-overview.md).)</span><span class="sxs-lookup"><span data-stu-id="9940b-110">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](../../../docs/standard/datetime/time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9940b-111">Zonas horarias personalizadas creadas mediante una llamada a la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método no se agregan al registro.</span><span class="sxs-lookup"><span data-stu-id="9940b-111">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="9940b-112">En su lugar, puede obtenerse únicamente a través de la referencia de objeto devuelta por la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> llamada al método.</span><span class="sxs-lookup"><span data-stu-id="9940b-112">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="9940b-113">En este tema se muestra cómo crear una zona horaria sin reglas de ajuste.</span><span class="sxs-lookup"><span data-stu-id="9940b-113">This topic shows how to create a time zone without adjustment rules.</span></span> <span data-ttu-id="9940b-114">Para crear una zona horaria que es compatible con las reglas de ajuste al horario de verano, vea [Cómo: Creación de zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span><span class="sxs-lookup"><span data-stu-id="9940b-114">To create a time zone that supports daylight saving time adjustment rules, see [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-without-adjustment-rules"></a><span data-ttu-id="9940b-115">Para crear una zona horaria sin reglas de ajuste</span><span class="sxs-lookup"><span data-stu-id="9940b-115">To create a time zone without adjustment rules</span></span>

1. <span data-ttu-id="9940b-116">Definir el nombre para mostrar de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="9940b-116">Define the time zone's display name.</span></span>

   <span data-ttu-id="9940b-117">El nombre para mostrar sigue un formato bastante estándar en el que se encierra entre paréntesis el desplazamiento de la zona horaria de hora Universal coordinada (UTC) y seguido de una cadena que identifica la zona horaria, uno o más de las ciudades de la zona horaria o uno o varios de lo cou movimientos o regiones en la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="9940b-117">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

2. <span data-ttu-id="9940b-118">Defina el nombre de la hora de la zona horaria estándar.</span><span class="sxs-lookup"><span data-stu-id="9940b-118">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="9940b-119">Normalmente, esta cadena también se utiliza como identificador de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="9940b-119">Typically, this string is also used as the time zone's identifier.</span></span>

3. <span data-ttu-id="9940b-120">Si desea utilizar un identificador diferente que el nombre de la zona horaria estándar, definir el identificador de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="9940b-120">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

4. <span data-ttu-id="9940b-121">Crear una instancia de un <xref:System.TimeSpan> objeto que define el desplazamiento de la zona horaria a la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="9940b-121">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="9940b-122">Zonas horarias con horas posteriores a la hora UTC tienen una diferencia positiva.</span><span class="sxs-lookup"><span data-stu-id="9940b-122">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="9940b-123">Zonas horarias con tiempos anteriores a la hora UTC tienen una diferencia negativa.</span><span class="sxs-lookup"><span data-stu-id="9940b-123">Time zones with times that are earlier than UTC have a negative offset.</span></span>

5. <span data-ttu-id="9940b-124">Llame a la <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> método para crear una instancia de la nueva zona horaria.</span><span class="sxs-lookup"><span data-stu-id="9940b-124">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="9940b-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9940b-125">Example</span></span>

<span data-ttu-id="9940b-126">El ejemplo siguiente define una zona horaria personalizada para Mawson, Antártida, que no tiene ninguna regla de ajuste.</span><span class="sxs-lookup"><span data-stu-id="9940b-126">The following example defines a custom time zone for Mawson, Antarctica, which has no adjustment rules.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

<span data-ttu-id="9940b-127">La cadena asignada a la <xref:System.TimeZoneInfo.DisplayName%2A> propiedad sigue un formato estándar en que el desplazamiento de la zona horaria a la hora UTC va seguido de una descripción detallada de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="9940b-127">The string assigned to the <xref:System.TimeZoneInfo.DisplayName%2A> property follows a standard format in which the time zone's offset from UTC is followed by a friendly description of the time zone.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="9940b-128">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="9940b-128">Compiling the code</span></span>

<span data-ttu-id="9940b-129">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="9940b-129">This example requires:</span></span>

* <span data-ttu-id="9940b-130">Que se agregarán al proyecto una referencia a System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="9940b-130">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="9940b-131">Que se importarán los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="9940b-131">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="9940b-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="9940b-132">See also</span></span>

- [<span data-ttu-id="9940b-133">Fechas, horas y zonas horarias</span><span class="sxs-lookup"><span data-stu-id="9940b-133">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="9940b-134">Información general sobre zonas horarias</span><span class="sxs-lookup"><span data-stu-id="9940b-134">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="9940b-135">Cómo: Creación de zonas horarias con reglas de ajuste</span><span class="sxs-lookup"><span data-stu-id="9940b-135">How to: Create time zones with adjustment rules</span></span>](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)
