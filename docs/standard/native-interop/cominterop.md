---
title: Interoperabilidad COM en .NET
description: Obtenga información sobre cómo interoperar con bibliotecas COM en .NET.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 07/11/2019
ms.openlocfilehash: 9355e2ae84da623ffa725f5b2ac1bdee25b966d8
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971895"
---
# <a name="com-interop-in-net"></a><span data-ttu-id="516cb-103">Interoperabilidad COM en .NET</span><span class="sxs-lookup"><span data-stu-id="516cb-103">COM Interop in .NET</span></span>

<span data-ttu-id="516cb-104">El Modelo de objetos componentes (COM) permite que un objeto exponga su funcionalidad a otros componentes y aplicaciones host en plataformas de Windows.</span><span class="sxs-lookup"><span data-stu-id="516cb-104">The Component Object Model (COM) lets an object expose its functionality to other components and to host applications on Windows platforms.</span></span> <span data-ttu-id="516cb-105">Para ayudar a los usuarios a interoperar con sus bases de código existentes, .NET Framework siempre ha brindado una compatibilidad total para interoperar con las bibliotecas COM.</span><span class="sxs-lookup"><span data-stu-id="516cb-105">To help enable users to interoperate with their existing code bases, the .NET Framework has always provided strong support for interoperating with COM libraries.</span></span> <span data-ttu-id="516cb-106">En .NET Core 3.0, se agregó una gran parte de esta compatibilidad a .NET Core en Windows.</span><span class="sxs-lookup"><span data-stu-id="516cb-106">In .NET Core 3.0, a large portion of this support has been added to .NET Core on Windows.</span></span> <span data-ttu-id="516cb-107">En esta documentación se explica cómo funcionan las tecnologías de interoperabilidad COM y cómo puede utilizarlas para interoperar con sus bibliotecas COM existentes.</span><span class="sxs-lookup"><span data-stu-id="516cb-107">The documentation here will explain how the common COM interop techonologies work and how you can utilize them to interoperate with your existing COM libraries.</span></span>

- [<span data-ttu-id="516cb-108">Contenedores COM</span><span class="sxs-lookup"><span data-stu-id="516cb-108">COM Wrappers</span></span>](./com-wrappers.md)
- [<span data-ttu-id="516cb-109">Contenedores CCW</span><span class="sxs-lookup"><span data-stu-id="516cb-109">COM Callable Wrappers</span></span>](./com-callable-wrapper.md)
- [<span data-ttu-id="516cb-110">Contenedores RCW</span><span class="sxs-lookup"><span data-stu-id="516cb-110">Runtime Callable Wrappers</span></span>](./runtime-callable-wrapper.md)
- [<span data-ttu-id="516cb-111">Habilitar tipos de .NET para la interoperación con COM</span><span class="sxs-lookup"><span data-stu-id="516cb-111">Qualifying .NET Types for COM Interoperation</span></span>](./qualify-net-types-for-interoperation.md)
