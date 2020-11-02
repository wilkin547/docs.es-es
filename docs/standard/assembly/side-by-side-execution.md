---
title: Ensamblados y ejecución en paralelo
description: Aprenda sobre la ejecución en paralelo, que es la capacidad de almacenar y ejecutar varias versiones de una aplicación o de un componente en el mismo equipo.
ms.date: 08/20/2019
helpviewer_keywords:
- side-by-side execution [.NET]
- assemblies [.NET], side-by-side execution
ms.assetid: e42036ee-7590-47d1-b884-cc856e39bd5d
ms.openlocfilehash: 7bedd5a384ceace014412eb894adad5c92c00b05
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687976"
---
# <a name="assemblies-and-side-by-side-execution"></a><span data-ttu-id="fe08a-103">Ensamblados y ejecución en paralelo</span><span class="sxs-lookup"><span data-stu-id="fe08a-103">Assemblies and side-by-side execution</span></span>

<span data-ttu-id="fe08a-104">La ejecución en paralelo es la capacidad de almacenar y ejecutar varias versiones de una aplicación o un componente en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="fe08a-104">Side-by-side execution is the ability to store and execute multiple versions of an application or component on the same computer.</span></span> <span data-ttu-id="fe08a-105">Esto significa que puede tener varias versiones del motor en tiempo de ejecución y varias versiones de aplicaciones y componentes que utilizan una misma versión del motor en tiempo de ejecución en el mismo equipo y a la vez.</span><span class="sxs-lookup"><span data-stu-id="fe08a-105">This means that you can have multiple versions of the runtime, and multiple versions of applications and components that use a version of the runtime, on the same computer at the same time.</span></span> <span data-ttu-id="fe08a-106">La ejecución en paralelo ofrece un mayor control sobre las versiones de un componente a las que se enlaza una aplicación, y sobre la versión del motor en tiempo de ejecución que utiliza una aplicación.</span><span class="sxs-lookup"><span data-stu-id="fe08a-106">Side-by-side execution gives you more control over what versions of a component an application binds to, and more control over what version of the runtime an application uses.</span></span>  
  
<span data-ttu-id="fe08a-107">El hecho de que se admita el almacenamiento y la ejecución en paralelo de distintas versiones del mismo ensamblado es una parte integral de la creación de nombres seguros incluida en la infraestructura del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fe08a-107">Support for side-by-side storage and execution of different versions of the same assembly is an integral part of strong naming and is built into the infrastructure of the runtime.</span></span> <span data-ttu-id="fe08a-108">Debido a que el número de versión del ensamblado con nombre seguro forma parte de su identidad, el motor en tiempo de ejecución puede almacenar múltiples versiones del mismo ensamblado en la caché global de ensamblados y cargar esos ensamblados en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fe08a-108">Because the strong-named assembly's version number is part of its identity, the runtime can store multiple versions of the same assembly in the global assembly cache and load those assemblies at run time.</span></span>  
  
<span data-ttu-id="fe08a-109">Aunque el motor en tiempo de ejecución permite crear aplicaciones en paralelos, la ejecución en paralelo no es automática.</span><span class="sxs-lookup"><span data-stu-id="fe08a-109">Although the runtime provides you with the ability to create side-by-side applications, side-by-side execution is not automatic.</span></span> <span data-ttu-id="fe08a-110">Para más información sobre la creación de aplicaciones para la ejecución en paralelo, vea [Instrucciones para crear componentes para la ejecución en paralelo](../../framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).</span><span class="sxs-lookup"><span data-stu-id="fe08a-110">For more information on creating applications for side-by-side execution, see [Guidelines for creating components for side-by-side execution](../../framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe08a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe08a-111">See also</span></span>

- [<span data-ttu-id="fe08a-112">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="fe08a-112">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="fe08a-113">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="fe08a-113">Assemblies in .NET</span></span>](index.md)
