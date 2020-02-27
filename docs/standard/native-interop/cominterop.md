---
title: Interoperabilidad COM en .NET
description: Obtenga información sobre cómo interoperar con bibliotecas COM en .NET.
ms.date: 07/11/2019
ms.openlocfilehash: 63205ae5c09d6c3929da13788eb781cd975ca814
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627379"
---
# <a name="com-interop-in-net"></a><span data-ttu-id="d3044-103">Interoperabilidad COM en .NET</span><span class="sxs-lookup"><span data-stu-id="d3044-103">COM Interop in .NET</span></span>

<span data-ttu-id="d3044-104">El Modelo de objetos componentes (COM) permite que un objeto exponga su funcionalidad a otros componentes y aplicaciones host en plataformas de Windows.</span><span class="sxs-lookup"><span data-stu-id="d3044-104">The Component Object Model (COM) lets an object expose its functionality to other components and to host applications on Windows platforms.</span></span> <span data-ttu-id="d3044-105">Para ayudar a los usuarios a interoperar con sus bases de código existentes, .NET Framework siempre ha brindado una compatibilidad total para interoperar con las bibliotecas COM.</span><span class="sxs-lookup"><span data-stu-id="d3044-105">To help enable users to interoperate with their existing code bases, the .NET Framework has always provided strong support for interoperating with COM libraries.</span></span> <span data-ttu-id="d3044-106">En .NET Core 3.0, se agregó una gran parte de esta compatibilidad a .NET Core en Windows.</span><span class="sxs-lookup"><span data-stu-id="d3044-106">In .NET Core 3.0, a large portion of this support has been added to .NET Core on Windows.</span></span> <span data-ttu-id="d3044-107">En esta documentación se explicará cómo funcionan las tecnologías comunes de interoperabilidad COM y cómo puede usarlas para interoperar con las bibliotecas COM existentes.</span><span class="sxs-lookup"><span data-stu-id="d3044-107">The documentation here will explain how the common COM interop technologies work and how you can utilize them to interoperate with your existing COM libraries.</span></span>

- [<span data-ttu-id="d3044-108">Contenedores COM</span><span class="sxs-lookup"><span data-stu-id="d3044-108">COM Wrappers</span></span>](./com-wrappers.md)
- [<span data-ttu-id="d3044-109">Contenedores CCW</span><span class="sxs-lookup"><span data-stu-id="d3044-109">COM Callable Wrappers</span></span>](./com-callable-wrapper.md)
- [<span data-ttu-id="d3044-110">Contenedores RCW</span><span class="sxs-lookup"><span data-stu-id="d3044-110">Runtime Callable Wrappers</span></span>](./runtime-callable-wrapper.md)
- [<span data-ttu-id="d3044-111">Habilitar tipos de .NET para la interoperación con COM</span><span class="sxs-lookup"><span data-stu-id="d3044-111">Qualifying .NET Types for COM Interoperation</span></span>](./qualify-net-types-for-interoperation.md)
