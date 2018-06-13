---
title: Introducción a la escritura de una actividad personalizada
ms.date: 03/30/2017
ms.assetid: 3902f5fa-8a43-4048-8a6a-6b15472f90f0
ms.openlocfilehash: 1c455009a0c658429c13da5e93d07c744402dd61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513323"
---
# <a name="getting-started-writing-a-custom-activity"></a><span data-ttu-id="eb361-102">Introducción a la escritura de una actividad personalizada</span><span class="sxs-lookup"><span data-stu-id="eb361-102">Getting Started Writing a Custom Activity</span></span>
<span data-ttu-id="eb361-103">En este ejemplo se muestra cómo definir una actividad personalizada simple en XAML.</span><span class="sxs-lookup"><span data-stu-id="eb361-103">This sample demonstrates how to define a simple custom activity in XAML.</span></span> <span data-ttu-id="eb361-104">La actividad tiene el nombre `Rhyme` y su lógica es una secuencia de tres actividades <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="eb361-104">The activity is given the name `Rhyme`, and its logic is a sequence of three <xref:System.Activities.Statements.WriteLine> activities.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="eb361-105">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb361-105">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="eb361-106">Abra la **Simple.sln** solución en de ejemplo [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb361-106">Open the **Simple.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="eb361-107">Compile y ejecute la solución.</span><span class="sxs-lookup"><span data-stu-id="eb361-107">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eb361-108">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="eb361-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="eb361-109">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="eb361-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="eb361-110">Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="eb361-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="eb361-111">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="eb361-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\GettingStarted`