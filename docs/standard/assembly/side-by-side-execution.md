---
title: Ensamblados y ejecución en paralelo
ms.date: 08/20/2019
helpviewer_keywords:
- side-by-side execution [.NET Framework]
- assemblies [.NET Framework], side-by-side execution
ms.assetid: e42036ee-7590-47d1-b884-cc856e39bd5d
ms.openlocfilehash: 234efba66d87b520b54d6d113afcc4bba0bfe06a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138658"
---
# <a name="assemblies-and-side-by-side-execution"></a><span data-ttu-id="0c67f-102">Ensamblados y ejecución en paralelo</span><span class="sxs-lookup"><span data-stu-id="0c67f-102">Assemblies and side-by-side execution</span></span>

<span data-ttu-id="0c67f-103">La ejecución en paralelo es la capacidad de almacenar y ejecutar varias versiones de una aplicación o un componente en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="0c67f-103">Side-by-side execution is the ability to store and execute multiple versions of an application or component on the same computer.</span></span> <span data-ttu-id="0c67f-104">Esto significa que puede tener varias versiones del motor en tiempo de ejecución y varias versiones de aplicaciones y componentes que utilizan una misma versión del motor en tiempo de ejecución en el mismo equipo y a la vez.</span><span class="sxs-lookup"><span data-stu-id="0c67f-104">This means that you can have multiple versions of the runtime, and multiple versions of applications and components that use a version of the runtime, on the same computer at the same time.</span></span> <span data-ttu-id="0c67f-105">La ejecución en paralelo ofrece un mayor control sobre las versiones de un componente a las que se enlaza una aplicación, y sobre la versión del motor en tiempo de ejecución que utiliza una aplicación.</span><span class="sxs-lookup"><span data-stu-id="0c67f-105">Side-by-side execution gives you more control over what versions of a component an application binds to, and more control over what version of the runtime an application uses.</span></span>  
  
<span data-ttu-id="0c67f-106">El hecho de que se admita el almacenamiento y la ejecución en paralelo de distintas versiones del mismo ensamblado es una parte integral de la creación de nombres seguros incluida en la infraestructura del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c67f-106">Support for side-by-side storage and execution of different versions of the same assembly is an integral part of strong naming and is built into the infrastructure of the runtime.</span></span> <span data-ttu-id="0c67f-107">Debido a que el número de versión del ensamblado con nombre seguro forma parte de su identidad, el motor en tiempo de ejecución puede almacenar múltiples versiones del mismo ensamblado en la caché global de ensamblados y cargar esos ensamblados en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c67f-107">Because the strong-named assembly's version number is part of its identity, the runtime can store multiple versions of the same assembly in the global assembly cache and load those assemblies at run time.</span></span>  
  
<span data-ttu-id="0c67f-108">Aunque el motor en tiempo de ejecución permite crear aplicaciones en paralelos, la ejecución en paralelo no es automática.</span><span class="sxs-lookup"><span data-stu-id="0c67f-108">Although the runtime provides you with the ability to create side-by-side applications, side-by-side execution is not automatic.</span></span> <span data-ttu-id="0c67f-109">Para más información sobre la creación de aplicaciones para la ejecución en paralelo, vea [Instrucciones para crear componentes para la ejecución en paralelo](../../framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).</span><span class="sxs-lookup"><span data-stu-id="0c67f-109">For more information on creating applications for side-by-side execution, see [Guidelines for creating components for side-by-side execution](../../framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c67f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c67f-110">See also</span></span>

- [<span data-ttu-id="0c67f-111">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="0c67f-111">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="0c67f-112">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="0c67f-112">Assemblies in .NET</span></span>](index.md)
