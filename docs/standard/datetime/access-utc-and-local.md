---
title: 'Cómo: obtener acceso a los objetos de zona horaria local y UTC predefinidos'
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
ms.openlocfilehash: ef22753d9934a52d955412a4493b608f265519aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132607"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="78ca1-102">Cómo: obtener acceso a los objetos de zona horaria local y UTC predefinidos</span><span class="sxs-lookup"><span data-stu-id="78ca1-102">How to: Access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="78ca1-103">La clase <xref:System.TimeZoneInfo> proporciona dos propiedades, <xref:System.TimeZoneInfo.Utc%2A> y <xref:System.TimeZoneInfo.Local%2A>, que proporcionan al código acceso a los objetos de zona horaria predefinidos.</span><span class="sxs-lookup"><span data-stu-id="78ca1-103">The <xref:System.TimeZoneInfo> class provides two properties, <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A>, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="78ca1-104">En este tema, se describe cómo obtener acceso a los objetos <xref:System.TimeZoneInfo> que devuelven esas propiedades.</span><span class="sxs-lookup"><span data-stu-id="78ca1-104">This topic discusses how to access the <xref:System.TimeZoneInfo> objects returned by those properties.</span></span>

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="78ca1-105">Para obtener acceso al objeto TimeZoneInfo de la hora universal coordinada (UTC)</span><span class="sxs-lookup"><span data-stu-id="78ca1-105">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="78ca1-106">Use la propiedad `static` (`Shared` en Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> para obtener acceso a la hora universal coordinada.</span><span class="sxs-lookup"><span data-stu-id="78ca1-106">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="78ca1-107">En lugar de asignar el objeto <xref:System.TimeZoneInfo> devuelto por la propiedad a una variable de objeto, siga accediendo a la hora universal coordinada a través de la propiedad <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="78ca1-107">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property.</span></span>

### <a name="to-access-the-local-time-zone"></a><span data-ttu-id="78ca1-108">Para obtener acceso a la zona horaria local</span><span class="sxs-lookup"><span data-stu-id="78ca1-108">To access the local time zone</span></span>

1. <span data-ttu-id="78ca1-109">Use la propiedad `static` (`Shared` en Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> para tener acceso a la zona horaria del sistema local.</span><span class="sxs-lookup"><span data-stu-id="78ca1-109">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property to access the local system time zone.</span></span>

2. <span data-ttu-id="78ca1-110">En lugar de asignar el objeto <xref:System.TimeZoneInfo> devuelto por la propiedad a una variable de objeto, siga accediendo a la zona horaria local a través de la propiedad <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="78ca1-110">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property.</span></span>

## <a name="example"></a><span data-ttu-id="78ca1-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="78ca1-111">Example</span></span>

<span data-ttu-id="78ca1-112">En el código siguiente se usan las propiedades <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> y <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> para convertir una hora de la zona horaria estándar del este de EE. UU. y Canadá, así como para mostrar el nombre de la zona horaria en la consola.</span><span class="sxs-lookup"><span data-stu-id="78ca1-112">The following code uses the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> and <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

<span data-ttu-id="78ca1-113">Siempre debe tener acceso a la zona horaria local a través de la propiedad <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> en lugar de asignar la zona horaria local a una variable de objeto <xref:System.TimeZoneInfo>.</span><span class="sxs-lookup"><span data-stu-id="78ca1-113">You should always access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property rather than assigning the local time zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="78ca1-114">Del mismo modo, siempre debe obtener acceso a la hora universal coordinada a través de la propiedad <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> en lugar de asignar la zona UTC a una variable de objeto <xref:System.TimeZoneInfo>.</span><span class="sxs-lookup"><span data-stu-id="78ca1-114">Similarly, you should always access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property rather than assigning the UTC zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="78ca1-115">Esto evita que la variable de objeto <xref:System.TimeZoneInfo> se invalide mediante una llamada al método <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="78ca1-115">This prevents the <xref:System.TimeZoneInfo> object variable from being invalidated by a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="78ca1-116">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="78ca1-116">Compiling the code</span></span>

<span data-ttu-id="78ca1-117">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="78ca1-117">This example requires:</span></span>

- <span data-ttu-id="78ca1-118">Que el espacio de nombres <xref:System> se importe con la instrucción `using` ( C# necesaria en el código).</span><span class="sxs-lookup"><span data-stu-id="78ca1-118">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="78ca1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="78ca1-119">See also</span></span>

- [<span data-ttu-id="78ca1-120">Fechas, horas y zonas horarias</span><span class="sxs-lookup"><span data-stu-id="78ca1-120">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="78ca1-121">Búsqueda de las zonas horarias definidas en un sistema local</span><span class="sxs-lookup"><span data-stu-id="78ca1-121">Finding the time zones defined on a local system</span></span>](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [<span data-ttu-id="78ca1-122">Crear instancias de un objeto TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="78ca1-122">How to: Instantiate a TimeZoneInfo object</span></span>](../../../docs/standard/datetime/instantiate-time-zone-info.md)
