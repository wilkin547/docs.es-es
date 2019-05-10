---
title: Tipos obsoletos en Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: c8325e60d708b53e1701a980355d5d2bf20e8a4b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64644965"
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a><span data-ttu-id="0824f-102">Tipos obsoletos en Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="0824f-102">Deprecated types in Windows Workflow Foundation</span></span>
<span data-ttu-id="0824f-103">En .NET 4 el equipo de Workflow presentó nuevo motor de Workflow en el espacio de nombres <xref:System.Activities> .</span><span class="sxs-lookup"><span data-stu-id="0824f-103">In .NET 4 the Workflow Team released an all new Workflow engine in the <xref:System.Activities> namespace.</span></span> <span data-ttu-id="0824f-104">Con la versión de .NET 4.5 Beta vamos a marcar la mayoría de los tipos en el "WF 3" <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, y <xref:System.Workflow.Runtime> espacios de nombres como obsoleto.</span><span class="sxs-lookup"><span data-stu-id="0824f-104">With the release of .NET 4.5 Beta we are marking most of the types in the "WF 3" <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, and  <xref:System.Workflow.Runtime> namespaces as obsolete.</span></span>  
  
## <a name="obsolete-namespaces-and-tools"></a><span data-ttu-id="0824f-105">Espacios de nombres y herramientas obsoletos</span><span class="sxs-lookup"><span data-stu-id="0824f-105">Obsolete namespaces and tools</span></span>  
 <span data-ttu-id="0824f-106">Los ensamblados siguientes tienen uno o varios tipos públicos que están en desuso:</span><span class="sxs-lookup"><span data-stu-id="0824f-106">The following assemblies have one or more public types that will be deprecated:</span></span>  
  
- <span data-ttu-id="0824f-107">System.Workflow.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="0824f-107">System.Workflow.Activities.dll</span></span>  
  
- <span data-ttu-id="0824f-108">System.Workflow.ComponentModel.dll</span><span class="sxs-lookup"><span data-stu-id="0824f-108">System.Workflow.ComponentModel.dll</span></span>  
  
- <span data-ttu-id="0824f-109">System.Workflow.Runtime.dll</span><span class="sxs-lookup"><span data-stu-id="0824f-109">System.Workflow.Runtime.dll</span></span>  
  
- <span data-ttu-id="0824f-110">System.WorkflowServices.dll</span><span class="sxs-lookup"><span data-stu-id="0824f-110">System.WorkflowServices.dll</span></span>  
  
- <span data-ttu-id="0824f-111">Microsoft.Workflow.DebugController.dll</span><span class="sxs-lookup"><span data-stu-id="0824f-111">Microsoft.Workflow.DebugController.dll</span></span>  
  
- <span data-ttu-id="0824f-112">Microsoft.Workflow.Compiler.exe</span><span class="sxs-lookup"><span data-stu-id="0824f-112">Microsoft.Workflow.Compiler.exe</span></span>  
  
- <span data-ttu-id="0824f-113">Wfc.exe</span><span class="sxs-lookup"><span data-stu-id="0824f-113">Wfc.exe</span></span>  
  
 <span data-ttu-id="0824f-114">Como resultado, los clientes que usan API obsoletas de WF 3 encontrarán advertencias de compilación con un mensaje similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="0824f-114">As a result, customers who are using the deprecated WF 3 APIs will encounter build warnings with a message similar to the following:</span></span>  
  
 <span data-ttu-id="0824f-115">**Advertencia BC40000: X está obsoleta: WF 3 están desusados. Use W4 en su lugar.**</span><span class="sxs-lookup"><span data-stu-id="0824f-115">**Warning BC40000: X is obsolete: WF 3 types are deprecated. Please use WF 4 instead.**</span></span> <span data-ttu-id="0824f-116">Eliminaremos los tipos de .NET Framework en una futura versión, pero aún no hemos decidido el calendario (no en 4.5).</span><span class="sxs-lookup"><span data-stu-id="0824f-116">We will remove the types from the .NET Framework in a future release, but we have not yet determined that timeframe (not in 4.5).</span></span> <span data-ttu-id="0824f-117">Este paso permite que comuniquemos nuestra dirección a nuestros clientes y les demos tiempo suficiente para migrar al nuevo modelo WF4.</span><span class="sxs-lookup"><span data-stu-id="0824f-117">This current step allows us to communicate our direction to our customers and allow them plenty of time to move to the new WF4 model.</span></span> <span data-ttu-id="0824f-118">Por supuesto, continuaremos admitir estos tipos de WF 3 con el [directiva de ciclo de vida de soporte técnico de Microsoft](https://aka.ms/MicrosoftSupportLifecycle).</span><span class="sxs-lookup"><span data-stu-id="0824f-118">We will, of course, continue to support these WF 3 types under the [Microsoft Support Lifecycle Policy](https://aka.ms/MicrosoftSupportLifecycle).</span></span> <span data-ttu-id="0824f-119">Aplicaciones WF3 existentes se ejecutarán sin problema en .NET 4.5 y Visual Studio 2012 será compatible con las soluciones basadas en WF3 nuevas y existentes.</span><span class="sxs-lookup"><span data-stu-id="0824f-119">Existing WF3 applications will run without issue on .NET 4.5, and Visual Studio 2012 will support new and existing WF3-based solutions.</span></span>  
  
 <span data-ttu-id="0824f-120">Los tipos relacionados con reglas en el espacio de nombres <xref:System.Workflow.Activities.Rules>, que no tienen un reemplazo en WF 4.5, no se han quedado obsoletos.</span><span class="sxs-lookup"><span data-stu-id="0824f-120">Rules related types in the <xref:System.Workflow.Activities.Rules> namespace, which do not have a replacement in WF 4.5, have not been deprecated.</span></span>  
  
 <span data-ttu-id="0824f-121">Los clientes que deseen migrar sus aplicaciones a WF 4 encontrarán ayuda en la [Guía de migración de flujo de trabajo 4](migration-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="0824f-121">Customers who want to migrate their applications to WF 4 will find help in the [Workflow 4 Migration Guidance](migration-guidance.md).</span></span>
