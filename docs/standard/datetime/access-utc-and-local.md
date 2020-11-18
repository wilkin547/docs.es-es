---
title: Procedimiento para obtener acceso a los objetos de zona horaria local y UTC predefinidos
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], local
- predefined time zones
- UTC times, predefined
- local time zone access
- time zones [.NET], retrieving
- time zones [.NET], UTC
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
ms.openlocfilehash: b92ac812ed0bd0e80bb3a6ab03b52746eb15db97
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94818113"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="d4b1e-102">Procedimiento para obtener acceso a los objetos de zona horaria local y UTC predefinidos</span><span class="sxs-lookup"><span data-stu-id="d4b1e-102">How to: Access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="d4b1e-103">La <xref:System.TimeZoneInfo> clase proporciona dos propiedades, <xref:System.TimeZoneInfo.Utc%2A> y <xref:System.TimeZoneInfo.Local%2A> , que dan al código acceso a los objetos de zona horaria predefinidos.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-103">The <xref:System.TimeZoneInfo> class provides two properties, <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A>, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="d4b1e-104">En este tema, se describe cómo obtener acceso a los objetos <xref:System.TimeZoneInfo> que devuelven esas propiedades.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-104">This topic discusses how to access the <xref:System.TimeZoneInfo> objects returned by those properties.</span></span>

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="d4b1e-105">Para obtener acceso al objeto TimeZoneInfo de la hora universal coordinada (UTC)</span><span class="sxs-lookup"><span data-stu-id="d4b1e-105">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="d4b1e-106">Utilice la `static` `Shared` propiedad (en el Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> para obtener acceso a la hora universal coordinada.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-106">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="d4b1e-107">En lugar de asignar el <xref:System.TimeZoneInfo> objeto devuelto por la propiedad a una variable de objeto, siga accediendo a la hora universal coordinada a través de la <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-107">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property.</span></span>

### <a name="to-access-the-local-time-zone"></a><span data-ttu-id="d4b1e-108">Para obtener acceso a la zona horaria local</span><span class="sxs-lookup"><span data-stu-id="d4b1e-108">To access the local time zone</span></span>

1. <span data-ttu-id="d4b1e-109">Utilice la `static` `Shared` propiedad (en el Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> para tener acceso a la zona horaria del sistema local.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-109">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property to access the local system time zone.</span></span>

2. <span data-ttu-id="d4b1e-110">En lugar de asignar el <xref:System.TimeZoneInfo> objeto devuelto por la propiedad a una variable de objeto, siga accediendo a la zona horaria local a través de la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-110">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property.</span></span>

## <a name="example"></a><span data-ttu-id="d4b1e-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4b1e-111">Example</span></span>

<span data-ttu-id="d4b1e-112">El código siguiente utiliza las <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> propiedades y para convertir una hora de la zona horaria estándar del este de EE. UU. y Canadá, así como para mostrar el nombre de la zona horaria en la consola.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-112">The following code uses the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> and <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

<span data-ttu-id="d4b1e-113">Siempre debe tener acceso a la zona horaria local a través de la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> propiedad en lugar de asignar la zona horaria local a una <xref:System.TimeZoneInfo> variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-113">You should always access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property rather than assigning the local time zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="d4b1e-114">Del mismo modo, siempre debe obtener acceso a la hora universal coordinada a través de la <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> propiedad en lugar de asignar la zona UTC a una <xref:System.TimeZoneInfo> variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-114">Similarly, you should always access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property rather than assigning the UTC zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="d4b1e-115">Esto evita que <xref:System.TimeZoneInfo> una llamada al método invalide la variable de objeto <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="d4b1e-115">This prevents the <xref:System.TimeZoneInfo> object variable from being invalidated by a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="d4b1e-116">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="d4b1e-116">Compiling the code</span></span>

<span data-ttu-id="d4b1e-117">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="d4b1e-117">This example requires:</span></span>

- <span data-ttu-id="d4b1e-118">Que el <xref:System> espacio de nombres se debe importar con la `using` instrucción (necesaria en el código de C#).</span><span class="sxs-lookup"><span data-stu-id="d4b1e-118">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="d4b1e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4b1e-119">See also</span></span>

- [<span data-ttu-id="d4b1e-120">Fechas, horas y zonas horarias</span><span class="sxs-lookup"><span data-stu-id="d4b1e-120">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="d4b1e-121">Buscar las zonas horarias definidas en un sistema local</span><span class="sxs-lookup"><span data-stu-id="d4b1e-121">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)
- [<span data-ttu-id="d4b1e-122">Cómo: crear instancias de un objeto TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="d4b1e-122">How to: Instantiate a TimeZoneInfo object</span></span>](instantiate-time-zone-info.md)
