---
title: Fechas, horas y zonas horarias
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time zone objects [.NET Framework]
- date and time data [.NET Framework]
- time zones [.NET Framework]
- times [.NET Framework], time zones
- time [.NET Framework], time zones
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1e85fc8eac25cc6fdfb8cb3aaa77318019695c51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="dates-times-and-time-zones"></a><span data-ttu-id="13fcf-102">Fechas, horas y zonas horarias</span><span class="sxs-lookup"><span data-stu-id="13fcf-102">Dates, times, and time zones</span></span>

<span data-ttu-id="13fcf-103">Además de la estructura básica <xref:System.DateTime>, .NET proporciona las siguientes clases que permiten trabajar con zonas horarias:</span><span class="sxs-lookup"><span data-stu-id="13fcf-103">In addition to the basic <xref:System.DateTime> structure, .NET provides the following classes that support working with time zones:</span></span>

* <xref:System.TimeZone>

  <span data-ttu-id="13fcf-104">Use esta clase para trabajar con la zona horaria local del sistema y la zona de la hora universal coordinada (UTC). La clase <xref:System.TimeZoneInfo> reemplaza en gran medida la funcionalidad de la clase <xref:System.TimeZone>.</span><span class="sxs-lookup"><span data-stu-id="13fcf-104">Use this class to work with the system's local time zone and the Coordinated Universal Time (UTC) zone.The functionality of the <xref:System.TimeZone> class is largely superseded by the <xref:System.TimeZoneInfo> class.</span></span>

* <xref:System.TimeZoneInfo>

  <span data-ttu-id="13fcf-105">Use esta clase para trabajar con cualquier zona horaria predefinida en un sistema, para crear zonas horarias nuevas y para convertir fácilmente fechas y horas desde una zona horaria a otra.</span><span class="sxs-lookup"><span data-stu-id="13fcf-105">Use this class to work with any time zone that is predefined on a system, to create new time zones, and to easily convert dates and times from one time zone to another.</span></span> <span data-ttu-id="13fcf-106">Para desarrollo nuevo, debe usar la clase <xref:System.TimeZoneInfo>, en lugar de la clase <xref:System.TimeZone>.</span><span class="sxs-lookup"><span data-stu-id="13fcf-106">For new development, use the <xref:System.TimeZoneInfo> class instead of the <xref:System.TimeZone> class.</span></span>

* <xref:System.DateTimeOffset>

  <span data-ttu-id="13fcf-107">Use esta estructura para trabajar con fechas y horas cuyo desplazamiento (o diferencia) con respecto a la hora UTC es conocido.</span><span class="sxs-lookup"><span data-stu-id="13fcf-107">Use this structure to work with dates and times whose offset (or difference) from UTC is known.</span></span> <span data-ttu-id="13fcf-108">La estructura <xref:System.DateTimeOffset> combina un valor de fecha y hora con ese desplazamiento de hora de UTC.</span><span class="sxs-lookup"><span data-stu-id="13fcf-108">The <xref:System.DateTimeOffset> structure combines a date and time value with that time's offset from UTC.</span></span> <span data-ttu-id="13fcf-109">Debido a su relación con la hora UTC, un valor individual de fecha y hora identifica de forma inequívoca un punto temporal único.</span><span class="sxs-lookup"><span data-stu-id="13fcf-109">Because of its relationship to UTC, an individual date and time value unambiguously identifies a single point in time.</span></span> <span data-ttu-id="13fcf-110">Esto hace que un valor de <xref:System.DateTimeOffset> sea más portátil de un equipo a otro que un valor de <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="13fcf-110">This makes a <xref:System.DateTimeOffset> value more portable from one computer to another than a <xref:System.DateTime> value.</span></span>

<span data-ttu-id="13fcf-111">Esta sección de la documentación proporciona la información que necesita para trabajar con zonas horarias y para crear aplicaciones basadas en la zona horaria que puedan convertir fechas y horas de una zona horaria a otra.</span><span class="sxs-lookup"><span data-stu-id="13fcf-111">This section of the documentation provides the information that you need to work with time zones and to create time zone-aware applications that can convert dates and times from one time zone to another.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="13fcf-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="13fcf-112">In this section</span></span>

<span data-ttu-id="13fcf-113">En [Time zone overview](../../../docs/standard/datetime/time-zone-overview.md) (Información general sobre zonas horarias) se describe la terminología, los conceptos y los problemas relacionados con la creación de aplicaciones basadas en la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="13fcf-113">[Time zone overview](../../../docs/standard/datetime/time-zone-overview.md) Discusses the terminology, concepts, and issues involved in creating time zone-aware applications.</span></span>

<span data-ttu-id="13fcf-114">En [Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md) (Elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo) se explica cuándo usar los tipos <xref:System.DateTime>, <xref:System.DateTimeOffset> y <xref:System.TimeZoneInfo> al trabajar con datos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="13fcf-114">[Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md) Discusses when to use the <xref:System.DateTime>, <xref:System.DateTimeOffset>, and <xref:System.TimeZoneInfo> types when working with date and time data.</span></span>

<span data-ttu-id="13fcf-115">En [Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) (Buscar las zonas horarias definidas en un sistema local) se describe cómo enumerar las zonas horarias que se encuentran en un sistema local.</span><span class="sxs-lookup"><span data-stu-id="13fcf-115">[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) Describes how to enumerate the time zones found on a local system.</span></span>

<span data-ttu-id="13fcf-116">En [How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md) (Cómo: enumerar zonas horarias presentes en un equipo) se proporcionan ejemplos que enumeran las zonas horarias definidas en el Registro de un equipo y que permiten a los usuarios seleccionar una zona horaria predefinida de una lista.</span><span class="sxs-lookup"><span data-stu-id="13fcf-116">[How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md) Provides examples that enumerate the time zones defined in a computer's registry and that let users select a predefined time zone from a list.</span></span>

<span data-ttu-id="13fcf-117">En [How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md) (Cómo: obtener acceso a los objetos de zona horaria local y UTC predefinidos) se describe cómo tener acceso a la hora universal coordinada y a la zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="13fcf-117">[How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md) Describes how to access Coordinated Universal Time and the local time zone.</span></span>

<span data-ttu-id="13fcf-118">En [How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md) (Cómo: crear instancias de un objeto TimeZoneInfo) se describe cómo crear una instancia de un objeto <xref:System.TimeZoneInfo> desde el Registro del sistema local.</span><span class="sxs-lookup"><span data-stu-id="13fcf-118">[How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md) Describes how to instantiate a <xref:System.TimeZoneInfo> object from the local system registry.</span></span>

<span data-ttu-id="13fcf-119">En [Instantiating a DateTimeOffset object](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md) (Crear instancias de un objeto DateTimeOffset) se describen las formas en que pueden crearse instancias de un objeto <xref:System.DateTimeOffset> y las formas en que un valor <xref:System.DateTime> se puede convertir en un valor <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="13fcf-119">[Instantiating a DateTimeOffset object](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md) Discusses the ways in which a <xref:System.DateTimeOffset> object can be instantiated, and the ways in which a <xref:System.DateTime> value can be converted to a <xref:System.DateTimeOffset> value.</span></span>

<span data-ttu-id="13fcf-120">En [How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) (Cómo: crear zonas horarias sin reglas de ajuste) se describe cómo crear una zona horaria personalizada que no admite la transición al horario de verano o desde este.</span><span class="sxs-lookup"><span data-stu-id="13fcf-120">[How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) Describes how to create a custom time zone that does not support the transition to and from daylight saving time.</span></span>

<span data-ttu-id="13fcf-121">En [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) (Cómo: crear zonas horarias con reglas de ajuste) se describe cómo crear una zona horaria personalizada que admite una o más transiciones al horario de verano o desde este.</span><span class="sxs-lookup"><span data-stu-id="13fcf-121">[How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) Describes how to create a custom time zone that supports one or more transitions to and from daylight saving time.</span></span>

<span data-ttu-id="13fcf-122">En [Saving and restoring time zones](../../../docs/standard/datetime/saving-and-restoring-time-zones.md) (Guardar y restaurar zonas horarias) se describe la compatibilidad de <xref:System.TimeZoneInfo> con la serialización y la deserialización de datos de zona horaria y muestra algunos de los escenarios en que se pueden usar estas características.</span><span class="sxs-lookup"><span data-stu-id="13fcf-122">[Saving and restoring time zones](../../../docs/standard/datetime/saving-and-restoring-time-zones.md) Describes <xref:System.TimeZoneInfo> support for serialization and deserialization of time zone data and illustrates some of the scenarios in which these features can be used.</span></span>

<span data-ttu-id="13fcf-123">En [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) (Cómo: guardar zonas horarias en un recurso insertado) se describe cómo crear una zona horaria personalizada y guardar su información en un archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="13fcf-123">[How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) Describes how to create a custom time zone and save its information in a resource file.</span></span>

<span data-ttu-id="13fcf-124">En [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) (Cómo: restaurar zonas horarias de un recurso insertado) se describe cómo crear instancias de zonas horarias personalizadas que se han guardado en un archivo de recursos insertado.</span><span class="sxs-lookup"><span data-stu-id="13fcf-124">[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) Describes how to instantiate custom time zones that have been saved to an embedded resource file.</span></span>

<span data-ttu-id="13fcf-125">En [Performing arithmetic operations with dates and times](../../../docs/standard/datetime/performing-arithmetic-operations.md) (Efectuar operaciones aritméticas con fechas y horas) se describen los aspectos necesarios para agregar, sustraer y comparar los valores <xref:System.DateTime> y <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="13fcf-125">[Performing arithmetic operations with dates and times](../../../docs/standard/datetime/performing-arithmetic-operations.md) Discusses the issues involved in adding, subtracting, and comparing <xref:System.DateTime> and <xref:System.DateTimeOffset> values.</span></span>

<span data-ttu-id="13fcf-126">En [How to: Use time zones in date and time arithmetic](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md) (Cómo: usar zonas horarias en aritmética de fecha y hora) se describe cómo realizar la aritmética de fecha y hora que refleja las reglas de ajuste de una zona horaria.</span><span class="sxs-lookup"><span data-stu-id="13fcf-126">[How to: Use time zones in date and time arithmetic](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md) Discusses how to perform date and time arithmetic that reflects a time zone's adjustment rules.</span></span>

<span data-ttu-id="13fcf-127">En [Converting between DateTime and DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md) (Convertir entre DateTime y DateTimeOffset) se describe cómo convertir entre valores <xref:System.DateTime> y <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="13fcf-127">[Converting between DateTime and DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md) Describes how to convert between <xref:System.DateTime> and <xref:System.DateTimeOffset> values.</span></span>

<span data-ttu-id="13fcf-128">En [Converting times between time zones](../../../docs/standard/datetime/converting-between-time-zones.md) (Convertir horas entre zonas horarias) se describe cómo convertir las horas de una zona horaria a otra.</span><span class="sxs-lookup"><span data-stu-id="13fcf-128">[Converting times between time zones](../../../docs/standard/datetime/converting-between-time-zones.md) Describes how to convert times from one time zone to another.</span></span>

<span data-ttu-id="13fcf-129">En [How to: Resolve ambiguous times](../../../docs/standard/datetime/resolve-ambiguous-times.md) (Cómo: resolver horas ambiguas) se describe cómo resolver una hora ambigua mediante su asignación a la hora estándar de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="13fcf-129">[How to: Resolve ambiguous times](../../../docs/standard/datetime/resolve-ambiguous-times.md) Describes how to resolve an ambiguous time by mapping it to the time zone's standard time.</span></span>

<span data-ttu-id="13fcf-130">En [How to: Let users resolve ambiguous times](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md) (Cómo: permitir que los usuarios resuelvan horas ambiguas) se describe cómo permitir que los usuarios determinen la asignación entre una hora local ambigua y la hora universal coordinada.</span><span class="sxs-lookup"><span data-stu-id="13fcf-130">[How to: Let users resolve ambiguous times](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md) Describes how to let a user determine the mapping between an ambiguous local time and Coordinated Universal Time.</span></span>

## <a name="reference"></a><span data-ttu-id="13fcf-131">Referencia</span><span class="sxs-lookup"><span data-stu-id="13fcf-131">Reference</span></span>

<xref:System.TimeZoneInfo?displayProperty=nameWithType>
