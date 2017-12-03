---
title: "Excepciones, transacciones y compensación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7fab7247540ba4e098a793adebab54ca4219e503
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="050e3-102">Excepciones, transacciones y compensación</span><span class="sxs-lookup"><span data-stu-id="050e3-102">Exceptions, Transactions, and Compensation</span></span>
[!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="050e3-103"> proporciona varios mecanismos diferentes para administrar las condiciones de error en tiempo de ejecución en flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="050e3-103"> provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="050e3-104">Los flujos de trabajo pueden usar una combinación de controladores de excepciones, transacciones, cancelación y compensación para administrar y recuperar sin contratiempos las condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="050e3-104">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="050e3-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="050e3-105">In This Section</span></span>  
 [<span data-ttu-id="050e3-106">Excepciones</span><span class="sxs-lookup"><span data-stu-id="050e3-106">Exceptions</span></span>](../../../docs/framework/windows-workflow-foundation/exceptions.md)  
 <span data-ttu-id="050e3-107">Muestra cómo usar la actividad <xref:System.Activities.Statements.TryCatch> para administrar las excepciones en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="050e3-107">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="050e3-108">Transacciones</span><span class="sxs-lookup"><span data-stu-id="050e3-108">Transactions</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)  
 <span data-ttu-id="050e3-109">Muestra cómo usar la actividad <xref:System.Activities.Statements.TransactionScope> para utilizar excepciones en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="050e3-109">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="050e3-110">Compensación</span><span class="sxs-lookup"><span data-stu-id="050e3-110">Compensation</span></span>](../../../docs/framework/windows-workflow-foundation/compensation.md)  
 <span data-ttu-id="050e3-111">Describe la compensación en flujos de trabajo y muestra cómo usar actividades de compensación como <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate> y <xref:System.Activities.Statements.Confirm>.</span><span class="sxs-lookup"><span data-stu-id="050e3-111">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="050e3-112">Cancelación</span><span class="sxs-lookup"><span data-stu-id="050e3-112">Cancellation</span></span>](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="050e3-113">Describe cómo realizar el control de la cancelación en flujos de trabajo utilizando actividades integradas así como actividades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="050e3-113">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="050e3-114">Depuración de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="050e3-114">Debugging Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/debugging-workflows.md)  
 <span data-ttu-id="050e3-115">Describe cómo depurar los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="050e3-115">Describes how to debug workflows.</span></span>
