---
title: Interfaces de hospedaje
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
ms.openlocfilehash: d1668f52ff305ec36fb520c7828c822537da0d02
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616104"
---
# <a name="hosting-interfaces"></a><span data-ttu-id="8b876-102">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="8b876-102">Hosting Interfaces</span></span>
<span data-ttu-id="8b876-103">En esta sección se describen las interfaces que los hosts no administrados pueden utilizar para integrar el Common Language Runtime (CLR) en sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8b876-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="8b876-104">Las interfaces de hospedaje de .NET Framework versión 2,0 reemplazan a las interfaces de la versión 1,0 y 1,1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8b876-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="8b876-105">Existen diferencias importantes entre los dos conjuntos de interfaces.</span><span class="sxs-lookup"><span data-stu-id="8b876-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="8b876-106">La combinación de ellos podría provocar un comportamiento inesperado y no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="8b876-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="8b876-107">Las versiones .NET Framework 3,0 y 3,5 utilizan las interfaces de hospedaje de .NET Framework versión 2,0 y no presentan ninguna característica de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="8b876-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="8b876-108">Las interfaces de hospedaje de .NET Framework 4 reemplazan a las interfaces de .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="8b876-108">The .NET Framework 4 hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="8b876-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8b876-109">In This Section</span></span>  
 [<span data-ttu-id="8b876-110">Coclases e interfaces de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="8b876-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="8b876-111">Describe las interfaces de hospedaje introducidas en las .NET Framework versiones 1,0 y 1,1.</span><span class="sxs-lookup"><span data-stu-id="8b876-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="8b876-112">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="8b876-112">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)  
 <span data-ttu-id="8b876-113">Describe las interfaces de hospedaje introducidas en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="8b876-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="8b876-114">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="8b876-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="8b876-115">Describe las interfaces de hospedaje introducidas en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="8b876-115">Describes the hosting interfaces introduced in the .NET Framework 4.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8b876-116">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="8b876-116">Related Sections</span></span>  
 [<span data-ttu-id="8b876-117">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="8b876-117">Hosting Coclasses</span></span>](hosting-coclasses.md)  
  
 [<span data-ttu-id="8b876-118">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="8b876-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="8b876-119">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="8b876-119">Hosting Enumerations</span></span>](hosting-enumerations.md)  
  
 [<span data-ttu-id="8b876-120">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="8b876-120">Hosting Structures</span></span>](hosting-structures.md)  
  
 [<span data-ttu-id="8b876-121">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="8b876-121">Hosting</span></span>](index.md)  
  
 <span data-ttu-id="8b876-122">[Hosts de runtime](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8b876-122">[Runtime Hosts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>
