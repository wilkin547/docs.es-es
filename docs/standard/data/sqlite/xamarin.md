---
title: Limitaciones de Xamarin
ms.date: 12/13/2019
description: Se describen algunas de las limitaciones que encontrará al usar Xamarin.
ms.openlocfilehash: 192f25954726919dc66d706e755e0853404b4d85
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450409"
---
# <a name="xamarin-limitations"></a><span data-ttu-id="1d07c-103">Limitaciones de Xamarin</span><span class="sxs-lookup"><span data-stu-id="1d07c-103">Xamarin limitations</span></span>

<span data-ttu-id="1d07c-104">Microsoft.Data.SQLite tiene como destino .NET Standard 2.0 y es compatible con Xamarin.</span><span class="sxs-lookup"><span data-stu-id="1d07c-104">Microsoft.Data.Sqlite targets .NET Standard 2.0 and is supported on Xamarin.</span></span> <span data-ttu-id="1d07c-105">En la tabla siguiente se muestran las plataformas para las que la agrupación SQLitePCLRaw predeterminada proporciona archivos binarios nativos de SQLite.</span><span class="sxs-lookup"><span data-stu-id="1d07c-105">The following table shows which platforms the default SQLitePCLRaw bundle provides native SQLite binaries for.</span></span> <span data-ttu-id="1d07c-106">Vea [Versiones personalizadas de SQLite](custom-versions.md) para obtener más información sobre el uso de otra agrupación o cómo suministrar archivos binarios nativos de SQLite propios.</span><span class="sxs-lookup"><span data-stu-id="1d07c-106">See [Custom SQLite versions](custom-versions.md) for details on using a different bundle or providing your own native SQLite binaries.</span></span>

| <span data-ttu-id="1d07c-107">Plataforma</span><span class="sxs-lookup"><span data-stu-id="1d07c-107">Platform</span></span> | <span data-ttu-id="1d07c-108">Archivos binarios de SQLite</span><span class="sxs-lookup"><span data-stu-id="1d07c-108">SQLite binaries</span></span> |
| --- | --- |
| <span data-ttu-id="1d07c-109">**Xamarin.Android**</span><span class="sxs-lookup"><span data-stu-id="1d07c-109">**Xamarin.Android**</span></span> | <span data-ttu-id="1d07c-110">—</span><span class="sxs-lookup"><span data-stu-id="1d07c-110">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64-v8a` | <span data-ttu-id="1d07c-111">✔</span><span class="sxs-lookup"><span data-stu-id="1d07c-111">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`armeabi-v7a` | <span data-ttu-id="1d07c-112">✔</span><span class="sxs-lookup"><span data-stu-id="1d07c-112">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="1d07c-113">✔</span><span class="sxs-lookup"><span data-stu-id="1d07c-113">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86_64` | <span data-ttu-id="1d07c-114">✔</span><span class="sxs-lookup"><span data-stu-id="1d07c-114">✔</span></span> |
| <span data-ttu-id="1d07c-115">**Xamarin.iOS**</span><span class="sxs-lookup"><span data-stu-id="1d07c-115">**Xamarin.iOS**</span></span> | <span data-ttu-id="1d07c-116">✔</span><span class="sxs-lookup"><span data-stu-id="1d07c-116">✔</span></span> |
| <span data-ttu-id="1d07c-117">**Xamarin.Mac**</span><span class="sxs-lookup"><span data-stu-id="1d07c-117">**Xamarin.Mac**</span></span> | <span data-ttu-id="1d07c-118">✔</span><span class="sxs-lookup"><span data-stu-id="1d07c-118">✔</span></span> |
| <span data-ttu-id="1d07c-119">**Xamarin.TVOS**</span><span class="sxs-lookup"><span data-stu-id="1d07c-119">**Xamarin.TVOS**</span></span> | <span data-ttu-id="1d07c-120">✔</span><span class="sxs-lookup"><span data-stu-id="1d07c-120">✔</span></span> |
| <span data-ttu-id="1d07c-121">**UWP**</span><span class="sxs-lookup"><span data-stu-id="1d07c-121">**UWP**</span></span> | <span data-ttu-id="1d07c-122">—</span><span class="sxs-lookup"><span data-stu-id="1d07c-122">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm` | <span data-ttu-id="1d07c-123">✔</span><span class="sxs-lookup"><span data-stu-id="1d07c-123">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64` | <span data-ttu-id="1d07c-124">✔</span><span class="sxs-lookup"><span data-stu-id="1d07c-124">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x64` | <span data-ttu-id="1d07c-125">✔</span><span class="sxs-lookup"><span data-stu-id="1d07c-125">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="1d07c-126">✔</span><span class="sxs-lookup"><span data-stu-id="1d07c-126">✔</span></span> |

## <a name="ios"></a><span data-ttu-id="1d07c-127">iOS</span><span class="sxs-lookup"><span data-stu-id="1d07c-127">iOS</span></span>

<span data-ttu-id="1d07c-128">Microsoft.Data.SQLite intenta inicializar automáticamente las agrupaciones SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="1d07c-128">Microsoft.Data.Sqlite tries to automatically initialize SQLitePCLRaw bundles.</span></span> <span data-ttu-id="1d07c-129">Desafortunadamente, debido a las limitaciones de la compilación Ahead Of Time (AOT) de Xamarin.iOS, no se puede realizar el intento y se obtiene el siguiente error.</span><span class="sxs-lookup"><span data-stu-id="1d07c-129">Unfortunately, because of limitations in the ahead-of-time (AOT) compilation for Xamarin.iOS, the attempt fails and you get the following error.</span></span>

> <span data-ttu-id="1d07c-130">Debe llamar a `SQLitePCL.raw.SetProvider()`.</span><span class="sxs-lookup"><span data-stu-id="1d07c-130">You need to call `SQLitePCL.raw.SetProvider()`.</span></span> <span data-ttu-id="1d07c-131">Si usa un paquete de agrupaciones, debe llamar a `SQLitePCL.Batteries.Init()`.</span><span class="sxs-lookup"><span data-stu-id="1d07c-131">If you're using a bundle package, this is done by calling `SQLitePCL.Batteries.Init()`.</span></span>

<span data-ttu-id="1d07c-132">Para inicializar la agrupación, agregue la línea de código siguiente a la aplicación antes de usar Microsoft.Data.SQLite.</span><span class="sxs-lookup"><span data-stu-id="1d07c-132">To initialize the bundle, add the following line of code to your app before using Microsoft.Data.Sqlite.</span></span>

```csharp
SQLitePCL.Batteries_V2.Init();
```

## <a name="see-also"></a><span data-ttu-id="1d07c-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d07c-133">See also</span></span>

* [<span data-ttu-id="1d07c-134">Limitaciones de Async</span><span class="sxs-lookup"><span data-stu-id="1d07c-134">Async limitations</span></span>](async.md)
* [<span data-ttu-id="1d07c-135">Versiones personalizadas de SQLite</span><span class="sxs-lookup"><span data-stu-id="1d07c-135">Custom SQLite versions</span></span>](custom-versions.md)
