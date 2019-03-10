---
title: Flujos de trabajo de procedimiento
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: fcf50296a8ce3e7e2e0631057467af8a8efd9215
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715716"
---
# <a name="procedural-workflows"></a><span data-ttu-id="f6e2b-102">Flujos de trabajo de procedimiento</span><span class="sxs-lookup"><span data-stu-id="f6e2b-102">Procedural Workflows</span></span>
<span data-ttu-id="f6e2b-103">Los flujos de trabajo de procedimiento usan métodos de control de flujo similares a los que se encuentren en lenguajes de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f6e2b-103">Procedural workflows use flow-control methods similar to those found in procedural languages.</span></span> <span data-ttu-id="f6e2b-104">Estas construcciones incluyen `While` y `If`.</span><span class="sxs-lookup"><span data-stu-id="f6e2b-104">These constructs include `While` and `If`.</span></span> <span data-ttu-id="f6e2b-105">Estos flujos de trabajo se pueden crear libremente con otras actividades de control de flujo como <xref:System.Activities.Statements.Flowchart> y <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="f6e2b-105">These workflows can be freely composed using other flow control activities such as <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Sequence>.</span></span>  
  
## <a name="controlling-execution-flow"></a><span data-ttu-id="f6e2b-106">Controlar el flujo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f6e2b-106">Controlling Execution Flow</span></span>  
 <span data-ttu-id="f6e2b-107">La biblioteca de actividades del flujo de trabajo tiene actividades para modelar la mayoría de los métodos de control de flujo usados en lenguajes de procedimientos.</span><span class="sxs-lookup"><span data-stu-id="f6e2b-107">The workflow activity library has activities for modeling most flow-control methods used in procedural languages.</span></span> <span data-ttu-id="f6e2b-108">Se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f6e2b-108">These include:</span></span>  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.DoWhile>  
  
-   <xref:System.Activities.Statements.ForEach%601>  
  
-   <xref:System.Activities.Statements.Parallel>  
  
-   <xref:System.Activities.Statements.ParallelForEach%601>  
  
-   <xref:System.Activities.Statements.If>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.Pick>  
  
 <span data-ttu-id="f6e2b-109">Para usar actividades de flujo de control, arrastrar y colocar desde el **actividad** cuadro de herramientas en una actividad compuesta dentro de la ventana del diseñador.</span><span class="sxs-lookup"><span data-stu-id="f6e2b-109">To use flow control activities, drag and drop them from the **Activity** toolbox into a composite activity inside the designer window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6e2b-110">Si se usa [!INCLUDE[dublin](../../../includes/dublin-md.md)] para hospedar flujos de trabajo en una granja de servidores web, AppFabric moverá instancias entre diferentes servidores de AppFabric.</span><span class="sxs-lookup"><span data-stu-id="f6e2b-110">If using the [!INCLUDE[dublin](../../../includes/dublin-md.md)] to host workflows on a Web farm, AppFabric will move instances between different AppFabric servers.</span></span> <span data-ttu-id="f6e2b-111">Esto necesita que los recursos se puedan compartir entre todos los nodos.</span><span class="sxs-lookup"><span data-stu-id="f6e2b-111">This requires that the resources are able to be shared between all nodes.</span></span>  <span data-ttu-id="f6e2b-112">Ninguna de las actividades de flujo de trabajo predeterminadas de .NET 4 contiene ninguna operación que tenga acceso a recursos locales.</span><span class="sxs-lookup"><span data-stu-id="f6e2b-112">None of the default NET 4 workflow activities contain any operations that access local resources.</span></span> <span data-ttu-id="f6e2b-113">Puesto que AppFabric no ofrece ningún mecanismo para marcar un flujo de trabajo como inamovible, un desarrollador no debe crear actividades personalizadas que produzcan errores cuando se mueva un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f6e2b-113">Since AppFabric does not offer any mechanism to mark a workflow as immovable, a developer must not create custom activities that fail when a workflow is moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6e2b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6e2b-114">See also</span></span>
- [<span data-ttu-id="f6e2b-115">Flujos de trabajo del diagrama de flujo</span><span class="sxs-lookup"><span data-stu-id="f6e2b-115">Flowchart Workflows</span></span>](flowchart-workflows.md)
