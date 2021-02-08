---
description: Más información acerca de cómo crear y ejecutar una instancia de flujo de trabajo
title: Crear y ejecutar una instancia de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
ms.openlocfilehash: 2efd4a0017f450c21954e363af33be69c659624e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787856"
---
# <a name="creating-and-running-a-workflow-instance"></a><span data-ttu-id="4d2aa-103">Crear y ejecutar una instancia de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="4d2aa-103">Creating and Running a Workflow Instance</span></span>

<span data-ttu-id="4d2aa-104">En este ejemplo se muestra cómo ejecutar una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4d2aa-104">This sample shows how to run a workflow instance.</span></span> <span data-ttu-id="4d2aa-105">Muestra cómo ejecutarla sincrónicamente y de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="4d2aa-105">It shows how to execute it synchronously and asynchronously.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="4d2aa-106">Muestra</span><span class="sxs-lookup"><span data-stu-id="4d2aa-106">Demonstrates</span></span>

<span data-ttu-id="4d2aa-107"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="4d2aa-107"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span></span>

## <a name="discussion"></a><span data-ttu-id="4d2aa-108">Debate</span><span class="sxs-lookup"><span data-stu-id="4d2aa-108">Discussion</span></span>

<span data-ttu-id="4d2aa-109">La primera parte del ejemplo utiliza <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d2aa-109">The first part of the sample uses <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span> <span data-ttu-id="4d2aa-110">Esta es la manera más básica de ejecutar un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4d2aa-110">This is the most basic way to execute a workflow.</span></span> <span data-ttu-id="4d2aa-111">Los flujos de trabajo ejecutados con <xref:System.Activities.WorkflowInvoker.Invoke%2A> se ejecutan de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="4d2aa-111">Workflows executed with <xref:System.Activities.WorkflowInvoker.Invoke%2A> are executed synchronously.</span></span>

<span data-ttu-id="4d2aa-112">La segunda parte del ejemplo usa la clase <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="4d2aa-112">The second part of the sample uses the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="4d2aa-113"><xref:System.Activities.WorkflowApplication> permite tener más control sobre cada instancia, incluida la capacidad de interactuar con el flujo de trabajo en ejecución y ejecutar el flujo de trabajo de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="4d2aa-113"><xref:System.Activities.WorkflowApplication> enables you to have more control over each instance, including the ability to interact with the running workflow and to run the workflow asynchronously.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d2aa-114">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="4d2aa-114">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4d2aa-115">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="4d2aa-115">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="4d2aa-116">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="4d2aa-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4d2aa-117">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="4d2aa-117">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`

## <a name="see-also"></a><span data-ttu-id="4d2aa-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d2aa-118">See also</span></span>

- [<span data-ttu-id="4d2aa-119">Usar WorkflowInvoker y WorkflowApplication</span><span class="sxs-lookup"><span data-stu-id="4d2aa-119">Using WorkflowInvoker and WorkflowApplication</span></span>](../using-workflowinvoker-and-workflowapplication.md)
