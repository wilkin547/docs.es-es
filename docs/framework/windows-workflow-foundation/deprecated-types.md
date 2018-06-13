---
title: Tipos en desuso en Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: 899d21f23c0500a1df01916d1da210b2f9bea95b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512432"
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a><span data-ttu-id="ce8d8-102">Tipos en desuso en Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="ce8d8-102">Deprecated types in Windows Workflow Foundation</span></span>
<span data-ttu-id="ce8d8-103">En .NET 4 el equipo de Workflow presentó nuevo motor de Workflow en el espacio de nombres <xref:System.Activities> .</span><span class="sxs-lookup"><span data-stu-id="ce8d8-103">In .NET 4 the Workflow Team released an all new Workflow engine in the <xref:System.Activities> namespace.</span></span> <span data-ttu-id="ce8d8-104">Con la versión de .NET 4.5 Beta vamos a marcar la mayoría de los tipos en el "WF 3" <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, y <xref:System.Workflow.Runtime> los espacios de nombres como obsoleto.</span><span class="sxs-lookup"><span data-stu-id="ce8d8-104">With the release of .NET 4.5 Beta we are marking most of the types in the "WF 3" <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, and  <xref:System.Workflow.Runtime> namespaces as obsolete.</span></span>  
  
## <a name="obsolete-namespaces-and-tools"></a><span data-ttu-id="ce8d8-105">Espacios de nombres y herramientas obsoletos</span><span class="sxs-lookup"><span data-stu-id="ce8d8-105">Obsolete namespaces and tools</span></span>  
 <span data-ttu-id="ce8d8-106">Los ensamblados siguientes tienen uno o varios tipos públicos que están obsoletos:</span><span class="sxs-lookup"><span data-stu-id="ce8d8-106">The following assemblies have one or more public types that will be deprecated:</span></span>  
  
-   <span data-ttu-id="ce8d8-107">System.Workflow.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="ce8d8-107">System.Workflow.Activities.dll</span></span>  
  
-   <span data-ttu-id="ce8d8-108">System.Workflow.ComponentModel.dll</span><span class="sxs-lookup"><span data-stu-id="ce8d8-108">System.Workflow.ComponentModel.dll</span></span>  
  
-   <span data-ttu-id="ce8d8-109">System.Workflow.Runtime.dll</span><span class="sxs-lookup"><span data-stu-id="ce8d8-109">System.Workflow.Runtime.dll</span></span>  
  
-   <span data-ttu-id="ce8d8-110">System.WorkflowServices.dll</span><span class="sxs-lookup"><span data-stu-id="ce8d8-110">System.WorkflowServices.dll</span></span>  
  
-   <span data-ttu-id="ce8d8-111">Microsoft.Workflow.DebugController.dll</span><span class="sxs-lookup"><span data-stu-id="ce8d8-111">Microsoft.Workflow.DebugController.dll</span></span>  
  
-   <span data-ttu-id="ce8d8-112">Microsoft.Workflow.Compiler.exe</span><span class="sxs-lookup"><span data-stu-id="ce8d8-112">Microsoft.Workflow.Compiler.exe</span></span>  
  
-   <span data-ttu-id="ce8d8-113">Wfc.exe</span><span class="sxs-lookup"><span data-stu-id="ce8d8-113">Wfc.exe</span></span>  
  
 <span data-ttu-id="ce8d8-114">Como resultado, los clientes que usan API en desuso de WF 3 encontrarán advertencias de compilación con un mensaje similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="ce8d8-114">As a result, customers who are using the deprecated WF 3 APIs will encounter build warnings with a message similar to the following:</span></span>  
  
 <span data-ttu-id="ce8d8-115">**Advertencia BC40000: X está obsoleta: tipos de WF 3 están en desuso. Use W4 en su lugar.**</span><span class="sxs-lookup"><span data-stu-id="ce8d8-115">**Warning BC40000: X is obsolete: WF 3 types are deprecated. Please use WF 4 instead.**</span></span> <span data-ttu-id="ce8d8-116">Eliminaremos los tipos de .NET Framework en una futura versión, pero aún no hemos decidido el calendario (no en 4.5).</span><span class="sxs-lookup"><span data-stu-id="ce8d8-116">We will remove the types from the .NET Framework in a future release, but we have not yet determined that timeframe (not in 4.5).</span></span> <span data-ttu-id="ce8d8-117">Este paso permite que comuniquemos nuestra dirección a nuestros clientes y les demos tiempo suficiente para migrar al nuevo modelo WF4.</span><span class="sxs-lookup"><span data-stu-id="ce8d8-117">This current step allows us to communicate our direction to our customers and allow them plenty of time to move to the new WF4 model.</span></span> <span data-ttu-id="ce8d8-118">Por supuesto, continuaremos admitir estos tipos de WF 3 en el [directiva de ciclo de vida de Microsoft admiten](http://aka.ms/MicrosoftSupportLifecycle).</span><span class="sxs-lookup"><span data-stu-id="ce8d8-118">We will, of course, continue to support these WF 3 types under the [Microsoft Support Lifecycle Policy](http://aka.ms/MicrosoftSupportLifecycle).</span></span> <span data-ttu-id="ce8d8-119">Las aplicaciones WF3 existentes se ejecutarán sin problema en .NET 4.5, y [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] admitirá nuevas y existentes soluciones basadas en WF3.</span><span class="sxs-lookup"><span data-stu-id="ce8d8-119">Existing WF3 applications will run without issue on .NET 4.5, and [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] will support new and existing WF3-based solutions.</span></span>  
  
 <span data-ttu-id="ce8d8-120">Los tipos relacionados con reglas en el espacio de nombres <xref:System.Workflow.Activities.Rules>, que no tienen un reemplazo en WF 4.5, no se han quedado obsoletos.</span><span class="sxs-lookup"><span data-stu-id="ce8d8-120">Rules related types in the <xref:System.Workflow.Activities.Rules> namespace, which do not have a replacement in WF 4.5, have not been deprecated.</span></span>  
  
 <span data-ttu-id="ce8d8-121">Los clientes que deseen migrar sus aplicaciones a WF 4 encontrarán ayuda en la [Guía de migración de flujo de trabajo 4](migration-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="ce8d8-121">Customers who want to migrate their applications to WF 4 will find help in the [Workflow 4 Migration Guidance](migration-guidance.md).</span></span>
