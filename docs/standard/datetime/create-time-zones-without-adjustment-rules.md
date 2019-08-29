---
title: Procedimiento para crear zonas horarias sin reglas de ajuste
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
ms.openlocfilehash: 510112c8b19ec002d1dcf918eb983b55dee68fd0
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106666"
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a><span data-ttu-id="516db-102">Procedimiento para crear zonas horarias sin reglas de ajuste</span><span class="sxs-lookup"><span data-stu-id="516db-102">How to: Create time zones without adjustment rules</span></span>

<span data-ttu-id="516db-103">La información precisa de zona horaria requerida por una aplicación puede no estar presente en un sistema determinado por varias razones:</span><span class="sxs-lookup"><span data-stu-id="516db-103">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

- <span data-ttu-id="516db-104">La zona horaria nunca se ha definido en el registro del sistema local.</span><span class="sxs-lookup"><span data-stu-id="516db-104">The time zone has never been defined in the local system's registry.</span></span>

- <span data-ttu-id="516db-105">Los datos sobre la zona horaria se han modificado o eliminado del registro.</span><span class="sxs-lookup"><span data-stu-id="516db-105">Data about the time zone has been modified or removed from the registry.</span></span>

- <span data-ttu-id="516db-106">La zona horaria existe pero no tiene información precisa sobre los ajustes de zona horaria para un determinado período histórico.</span><span class="sxs-lookup"><span data-stu-id="516db-106">The time zone exists but does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="516db-107">En estos casos, puede llamar <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> al método para definir la zona horaria requerida por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="516db-107">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="516db-108">Puede usar las sobrecargas de este método para crear una zona horaria con o sin reglas de ajuste.</span><span class="sxs-lookup"><span data-stu-id="516db-108">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="516db-109">Si la zona horaria admite el horario de verano, puede definir ajustes con reglas de ajuste fijas o flotantes.</span><span class="sxs-lookup"><span data-stu-id="516db-109">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="516db-110">(Para obtener definiciones de estos términos, consulte la sección "terminología de zona horaria" en [información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)).</span><span class="sxs-lookup"><span data-stu-id="516db-110">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](../../../docs/standard/datetime/time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="516db-111">Las zonas horarias personalizadas creadas <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> llamando al método no se agregan al registro.</span><span class="sxs-lookup"><span data-stu-id="516db-111">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="516db-112">En su lugar, solo se puede tener acceso a ellos a través de la referencia <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> de objeto devuelta por la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="516db-112">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="516db-113">En este tema se muestra cómo crear una zona horaria sin reglas de ajuste.</span><span class="sxs-lookup"><span data-stu-id="516db-113">This topic shows how to create a time zone without adjustment rules.</span></span> <span data-ttu-id="516db-114">Para crear una zona horaria que admita reglas de ajuste del horario de verano [, consulte How to: Cree zonas horarias con reglas](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)de ajuste.</span><span class="sxs-lookup"><span data-stu-id="516db-114">To create a time zone that supports daylight saving time adjustment rules, see [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-without-adjustment-rules"></a><span data-ttu-id="516db-115">Para crear una zona horaria sin reglas de ajuste</span><span class="sxs-lookup"><span data-stu-id="516db-115">To create a time zone without adjustment rules</span></span>

1. <span data-ttu-id="516db-116">Defina el nombre para mostrar de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="516db-116">Define the time zone's display name.</span></span>

   <span data-ttu-id="516db-117">El nombre para mostrar sigue un formato bastante estándar en el que el desplazamiento de la zona horaria de la hora universal coordinada (UTC) se escribe entre paréntesis y va seguido de una cadena que identifica la zona horaria, una o varias de las ciudades de la zona horaria, o una o varias de las COU movimientos o regiones de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="516db-117">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

2. <span data-ttu-id="516db-118">Defina el nombre de la hora estándar de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="516db-118">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="516db-119">Normalmente, esta cadena también se usa como identificador de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="516db-119">Typically, this string is also used as the time zone's identifier.</span></span>

3. <span data-ttu-id="516db-120">Si desea usar un identificador diferente del nombre estándar de la zona horaria, defina el identificador de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="516db-120">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

4. <span data-ttu-id="516db-121">Cree una instancia <xref:System.TimeSpan> de un objeto que defina el desplazamiento de la zona horaria con respecto a la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="516db-121">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="516db-122">Las zonas horarias con horas que son posteriores a la hora UTC tienen un desplazamiento positivo.</span><span class="sxs-lookup"><span data-stu-id="516db-122">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="516db-123">Las zonas horarias con horas anteriores a la hora UTC tienen un desplazamiento negativo.</span><span class="sxs-lookup"><span data-stu-id="516db-123">Time zones with times that are earlier than UTC have a negative offset.</span></span>

5. <span data-ttu-id="516db-124">Llame al <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> método para crear una instancia de la nueva zona horaria.</span><span class="sxs-lookup"><span data-stu-id="516db-124">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="516db-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="516db-125">Example</span></span>

<span data-ttu-id="516db-126">En el ejemplo siguiente se define una zona horaria personalizada para Mawson, Antártida, que no tiene reglas de ajuste.</span><span class="sxs-lookup"><span data-stu-id="516db-126">The following example defines a custom time zone for Mawson, Antarctica, which has no adjustment rules.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

<span data-ttu-id="516db-127">La cadena asignada a <xref:System.TimeZoneInfo.DisplayName%2A> la propiedad sigue un formato estándar en el que el desplazamiento de la zona horaria con respecto a la hora UTC va seguido de una descripción detallada de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="516db-127">The string assigned to the <xref:System.TimeZoneInfo.DisplayName%2A> property follows a standard format in which the time zone's offset from UTC is followed by a friendly description of the time zone.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="516db-128">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="516db-128">Compiling the code</span></span>

<span data-ttu-id="516db-129">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="516db-129">This example requires:</span></span>

- <span data-ttu-id="516db-130">Que se importen los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="516db-130">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="516db-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="516db-131">See also</span></span>

- [<span data-ttu-id="516db-132">Fechas, horas y zonas horarias</span><span class="sxs-lookup"><span data-stu-id="516db-132">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="516db-133">Información general sobre zonas horarias</span><span class="sxs-lookup"><span data-stu-id="516db-133">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="516db-134">Cómo: Crear zonas horarias con reglas de ajuste</span><span class="sxs-lookup"><span data-stu-id="516db-134">How to: Create time zones with adjustment rules</span></span>](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)
