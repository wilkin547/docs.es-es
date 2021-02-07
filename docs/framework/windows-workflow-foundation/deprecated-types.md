---
description: 'Más información sobre: tipos desusados en Windows Workflow Foundation'
title: Tipos obsoletos en Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: a536f67708c5913040848df52f178dcc2a361f6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742438"
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a><span data-ttu-id="865d5-103">Tipos obsoletos en Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="865d5-103">Deprecated types in Windows Workflow Foundation</span></span>

<span data-ttu-id="865d5-104">En .NET 4 el equipo de Workflow presentó nuevo motor de Workflow en el espacio de nombres <xref:System.Activities> .</span><span class="sxs-lookup"><span data-stu-id="865d5-104">In .NET 4 the Workflow Team released an all new Workflow engine in the <xref:System.Activities> namespace.</span></span> <span data-ttu-id="865d5-105">Con el lanzamiento de .NET Framework beta 4,5, estamos marcando la mayoría de los tipos de los espacios de nombres "WF 3" <xref:System.Workflow.Activities> , <xref:System.Workflow.ComponentModel> y  <xref:System.Workflow.Runtime> como obsoletos.</span><span class="sxs-lookup"><span data-stu-id="865d5-105">With the release of .NET Framework 4.5 Beta we are marking most of the types in the "WF 3" <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, and  <xref:System.Workflow.Runtime> namespaces as obsolete.</span></span>

## <a name="obsolete-namespaces-and-tools"></a><span data-ttu-id="865d5-106">Espacios de nombres y herramientas obsoletos</span><span class="sxs-lookup"><span data-stu-id="865d5-106">Obsolete namespaces and tools</span></span>

 <span data-ttu-id="865d5-107">Los ensamblados siguientes tienen uno o varios tipos públicos que están en desuso:</span><span class="sxs-lookup"><span data-stu-id="865d5-107">The following assemblies have one or more public types that will be deprecated:</span></span>

- <span data-ttu-id="865d5-108">System.Workflow.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="865d5-108">System.Workflow.Activities.dll</span></span>

- <span data-ttu-id="865d5-109">System.Workflow.ComponentModel.dll</span><span class="sxs-lookup"><span data-stu-id="865d5-109">System.Workflow.ComponentModel.dll</span></span>

- <span data-ttu-id="865d5-110">System.Workflow.Runtime.dll</span><span class="sxs-lookup"><span data-stu-id="865d5-110">System.Workflow.Runtime.dll</span></span>

- <span data-ttu-id="865d5-111">System.WorkflowServices.dll</span><span class="sxs-lookup"><span data-stu-id="865d5-111">System.WorkflowServices.dll</span></span>

- <span data-ttu-id="865d5-112">Microsoft.Workflow.DebugController.dll</span><span class="sxs-lookup"><span data-stu-id="865d5-112">Microsoft.Workflow.DebugController.dll</span></span>

- <span data-ttu-id="865d5-113">Microsoft.Workflow.Compiler.exe</span><span class="sxs-lookup"><span data-stu-id="865d5-113">Microsoft.Workflow.Compiler.exe</span></span>

- <span data-ttu-id="865d5-114">Wfc.exe</span><span class="sxs-lookup"><span data-stu-id="865d5-114">Wfc.exe</span></span>

 <span data-ttu-id="865d5-115">Como resultado, los clientes que usan API obsoletas de WF 3 encontrarán advertencias de compilación con un mensaje similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="865d5-115">As a result, customers who are using the deprecated WF 3 APIs will encounter build warnings with a message similar to the following:</span></span>

 <span data-ttu-id="865d5-116">**ADVERTENCIA BC40000: X está obsoleto: los tipos de WF 3 están en desuso. En su lugar, use WF 4.**</span><span class="sxs-lookup"><span data-stu-id="865d5-116">**Warning BC40000: X is obsolete: WF 3 types are deprecated. Please use WF 4 instead.**</span></span> <span data-ttu-id="865d5-117">Eliminaremos los tipos de .NET Framework en una futura versión, pero aún no hemos decidido el calendario (no en 4.5).</span><span class="sxs-lookup"><span data-stu-id="865d5-117">We will remove the types from the .NET Framework in a future release, but we have not yet determined that timeframe (not in 4.5).</span></span> <span data-ttu-id="865d5-118">Este paso permite que comuniquemos nuestra dirección a nuestros clientes y les demos tiempo suficiente para migrar al nuevo modelo WF4.</span><span class="sxs-lookup"><span data-stu-id="865d5-118">This current step allows us to communicate our direction to our customers and allow them plenty of time to move to the new WF4 model.</span></span> <span data-ttu-id="865d5-119">Por supuesto, continuaremos admitiendo estos tipos de WF 3 en la [Directiva del ciclo de vida de soporte técnico de Microsoft](/lifecycle/).</span><span class="sxs-lookup"><span data-stu-id="865d5-119">We will, of course, continue to support these WF 3 types under the [Microsoft Support Lifecycle Policy](/lifecycle/).</span></span> <span data-ttu-id="865d5-120">Las aplicaciones de WF3 existentes se ejecutarán sin ningún problema en .NET Framework 4,5 y Visual Studio 2012 será compatible con las soluciones basadas en WF3 nuevas y existentes.</span><span class="sxs-lookup"><span data-stu-id="865d5-120">Existing WF3 applications will run without issue on .NET Framework 4.5, and Visual Studio 2012 will support new and existing WF3-based solutions.</span></span>

 <span data-ttu-id="865d5-121">Los tipos relacionados con reglas en el espacio de nombres <xref:System.Workflow.Activities.Rules>, que no tienen un reemplazo en WF 4.5, no se han quedado obsoletos.</span><span class="sxs-lookup"><span data-stu-id="865d5-121">Rules related types in the <xref:System.Workflow.Activities.Rules> namespace, which do not have a replacement in WF 4.5, have not been deprecated.</span></span>

 <span data-ttu-id="865d5-122">Los clientes que deseen migrar sus aplicaciones a WF 4 encontrarán ayuda en la [Guía de migración de flujo de trabajo 4](migration-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="865d5-122">Customers who want to migrate their applications to WF 4 will find help in the [Workflow 4 Migration Guidance](migration-guidance.md).</span></span>
