---
title: Crear y ejecutar una instancia de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
ms.openlocfilehash: d895cfa9e924ecf4d1571cf67f1c1e7069e25da5
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715201"
---
# <a name="creating-and-running-a-workflow-instance"></a><span data-ttu-id="f16d0-102">Crear y ejecutar una instancia de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="f16d0-102">Creating and Running a Workflow Instance</span></span>

<span data-ttu-id="f16d0-103">En este ejemplo se muestra cómo ejecutar una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f16d0-103">This sample shows how to run a workflow instance.</span></span> <span data-ttu-id="f16d0-104">Muestra cómo ejecutarla sincrónicamente y de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="f16d0-104">It shows how to execute it synchronously and asynchronously.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="f16d0-105">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="f16d0-105">Demonstrates</span></span>

<span data-ttu-id="f16d0-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="f16d0-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span></span>

## <a name="discussion"></a><span data-ttu-id="f16d0-107">Discusión</span><span class="sxs-lookup"><span data-stu-id="f16d0-107">Discussion</span></span>

<span data-ttu-id="f16d0-108">La primera parte del ejemplo utiliza <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span><span class="sxs-lookup"><span data-stu-id="f16d0-108">The first part of the sample uses <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span> <span data-ttu-id="f16d0-109">Esta es la manera más básica de ejecutar un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f16d0-109">This is the most basic way to execute a workflow.</span></span> <span data-ttu-id="f16d0-110">Los flujos de trabajo ejecutados con <xref:System.Activities.WorkflowInvoker.Invoke%2A> se ejecutan de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="f16d0-110">Workflows executed with <xref:System.Activities.WorkflowInvoker.Invoke%2A> are executed synchronously.</span></span>

<span data-ttu-id="f16d0-111">La segunda parte del ejemplo usa la clase <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="f16d0-111">The second part of the sample uses the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="f16d0-112"><xref:System.Activities.WorkflowApplication> permite tener más control sobre cada instancia, incluida la capacidad de interactuar con el flujo de trabajo en ejecución y ejecutar el flujo de trabajo de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="f16d0-112"><xref:System.Activities.WorkflowApplication> enables you to have more control over each instance, including the ability to interact with the running workflow and to run the workflow asynchronously.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f16d0-113">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="f16d0-113">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f16d0-114">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="f16d0-114">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="f16d0-115">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f16d0-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f16d0-116">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="f16d0-116">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`

## <a name="see-also"></a><span data-ttu-id="f16d0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f16d0-117">See also</span></span>

- [<span data-ttu-id="f16d0-118">Usar WorkflowInvoker y WorkflowApplication</span><span class="sxs-lookup"><span data-stu-id="f16d0-118">Using WorkflowInvoker and WorkflowApplication</span></span>](../using-workflowinvoker-and-workflowapplication.md)
