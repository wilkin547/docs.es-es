---
title: Usar una actividad de .NET Framework 3.0 o .NET Framework 3.5 en un flujo de trabajo de .NET Framework 4.5
ms.date: 03/30/2017
ms.assetid: 6c53fd4c-5dd0-4fb4-ab6b-111302629548
ms.openlocfilehash: ec44e56a99660ba422c73bbbf00bf5ef6b7b61ff
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486136"
---
# <a name="using-a-net-framework-30-or-net-framework-35-activity-in-a-net-framework-45-workflow"></a><span data-ttu-id="6dcfe-102">Usar una actividad de .NET Framework 3.0 o .NET Framework 3.5 en un flujo de trabajo de .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="6dcfe-102">Using a .NET Framework 3.0 or .NET Framework 3.5 Activity in a .NET Framework 4.5 Workflow</span></span>
<span data-ttu-id="6dcfe-103">El <xref:System.Activities.Statements.Interop> actividad le permite ejecutar una actividad de Windows Workflow Foundation (WF) de .NET Framework 3.0 en un [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-103">The <xref:System.Activities.Statements.Interop> activity allows you to run a .NET Framework 3.0 Windows Workflow Foundation (WF) activity within a [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] workflow.</span></span> <span data-ttu-id="6dcfe-104">En este ejemplo se muestra cómo utilizar la actividad <xref:System.Activities.Statements.Interop> para pasar una cadena como un argumento a una actividad de [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] personalizada.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-104">This sample demonstrates how to use the <xref:System.Activities.Statements.Interop> activity to pass a string as an argument to a custom [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] activity.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="6dcfe-105">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="6dcfe-105">To use this sample</span></span>  
  
1.  <span data-ttu-id="6dcfe-106">Abra el archivo de solución SimpleInterop.sln con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6dcfe-106">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the SimpleInterop.sln solution file.</span></span>  
  
2.  <span data-ttu-id="6dcfe-107">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-107">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="6dcfe-108">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-108">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6dcfe-109">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6dcfe-110">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6dcfe-111">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6dcfe-112">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## <a name="see-also"></a><span data-ttu-id="6dcfe-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6dcfe-113">See Also</span></span>
