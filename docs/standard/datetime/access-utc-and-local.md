---
title: Procedimiento para obtener acceso a los objetos de zona horaria local y UTC predefinidos
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], local
- predefined time zones
- UTC times, predefined
- local time zone access
- time zones [.NET Framework], retrieving
- time zones [.NET Framework], UTC
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8aa19118ce0837b9ce0eb523f3e086fcbcecb9e8
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106564"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="8f5f9-102">Procedimiento para obtener acceso a los objetos de zona horaria local y UTC predefinidos</span><span class="sxs-lookup"><span data-stu-id="8f5f9-102">How to: Access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="8f5f9-103">La <xref:System.TimeZoneInfo> clase proporciona dos propiedades, <xref:System.TimeZoneInfo.Utc%2A> y <xref:System.TimeZoneInfo.Local%2A>, que dan al código acceso a los objetos de zona horaria predefinidos.</span><span class="sxs-lookup"><span data-stu-id="8f5f9-103">The <xref:System.TimeZoneInfo> class provides two properties, <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A>, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="8f5f9-104">En este tema, se describe cómo obtener acceso a los objetos <xref:System.TimeZoneInfo> que devuelven esas propiedades.</span><span class="sxs-lookup"><span data-stu-id="8f5f9-104">This topic discusses how to access the <xref:System.TimeZoneInfo> objects returned by those properties.</span></span>

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="8f5f9-105">Para obtener acceso al objeto TimeZoneInfo de la hora universal coordinada (UTC)</span><span class="sxs-lookup"><span data-stu-id="8f5f9-105">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="8f5f9-106">Utilice la `static` propiedad`Shared` (en el <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Visual Basic) para obtener acceso a la hora universal coordinada.</span><span class="sxs-lookup"><span data-stu-id="8f5f9-106">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="8f5f9-107">En lugar de asignar el <xref:System.TimeZoneInfo> objeto devuelto por la propiedad a una variable de objeto, siga accediendo a la hora universal coordinada a través de la <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="8f5f9-107">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property.</span></span>

### <a name="to-access-the-local-time-zone"></a><span data-ttu-id="8f5f9-108">Para obtener acceso a la zona horaria local</span><span class="sxs-lookup"><span data-stu-id="8f5f9-108">To access the local time zone</span></span>

1. <span data-ttu-id="8f5f9-109">Utilice la `static` propiedad`Shared` (en el <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Visual Basic) para tener acceso a la zona horaria del sistema local.</span><span class="sxs-lookup"><span data-stu-id="8f5f9-109">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property to access the local system time zone.</span></span>

2. <span data-ttu-id="8f5f9-110">En lugar de asignar el <xref:System.TimeZoneInfo> objeto devuelto por la propiedad a una variable de objeto, siga accediendo a la zona horaria local a través de la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="8f5f9-110">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property.</span></span>

## <a name="example"></a><span data-ttu-id="8f5f9-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f5f9-111">Example</span></span>

<span data-ttu-id="8f5f9-112">El código siguiente utiliza las <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> propiedades <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> y para convertir una hora de la zona horaria estándar del este de EE. UU. y Canadá, así como para mostrar el nombre de la zona horaria en la consola.</span><span class="sxs-lookup"><span data-stu-id="8f5f9-112">The following code uses the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> and <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

<span data-ttu-id="8f5f9-113">Siempre debe tener acceso a la zona horaria local a <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> través de la propiedad en lugar de asignar la zona horaria local <xref:System.TimeZoneInfo> a una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="8f5f9-113">You should always access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property rather than assigning the local time zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="8f5f9-114">Del mismo modo, siempre debe obtener acceso a la hora <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> universal coordinada a través de la propiedad en lugar de <xref:System.TimeZoneInfo> asignar la zona UTC a una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="8f5f9-114">Similarly, you should always access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property rather than assigning the UTC zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="8f5f9-115">Esto evita que <xref:System.TimeZoneInfo> una llamada <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> al método invalide la variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="8f5f9-115">This prevents the <xref:System.TimeZoneInfo> object variable from being invalidated by a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="8f5f9-116">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="8f5f9-116">Compiling the code</span></span>

<span data-ttu-id="8f5f9-117">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="8f5f9-117">This example requires:</span></span>

- <span data-ttu-id="8f5f9-118">Que el <xref:System> espacio de nombres se debe `using` importar con la instrucción C# (necesario en el código).</span><span class="sxs-lookup"><span data-stu-id="8f5f9-118">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="8f5f9-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f5f9-119">See also</span></span>

- [<span data-ttu-id="8f5f9-120">Fechas, horas y zonas horarias</span><span class="sxs-lookup"><span data-stu-id="8f5f9-120">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="8f5f9-121">Búsqueda de las zonas horarias definidas en un sistema local</span><span class="sxs-lookup"><span data-stu-id="8f5f9-121">Finding the time zones defined on a local system</span></span>](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [<span data-ttu-id="8f5f9-122">Cómo: Crear instancias de un objeto TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="8f5f9-122">How to: Instantiate a TimeZoneInfo object</span></span>](../../../docs/standard/datetime/instantiate-time-zone-info.md)
