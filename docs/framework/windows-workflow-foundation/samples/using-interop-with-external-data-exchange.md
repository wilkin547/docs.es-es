---
title: Utilizar interoperabilidad con intercambio de datos externos
ms.date: 03/30/2017
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
ms.openlocfilehash: 534321e5b5568e0dd0988333dc98ccc18ff33df8
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46326258"
---
# <a name="using-interop-with-external-data-exchange"></a><span data-ttu-id="ad52a-102">Utilizar interoperabilidad con intercambio de datos externos</span><span class="sxs-lookup"><span data-stu-id="ad52a-102">Using Interop with External Data Exchange</span></span>
<span data-ttu-id="ad52a-103">El <xref:System.Activities.Statements.Interop> actividad se puede usar para ejecutar actividades de Windows Workflow Foundation (WF) en [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] y [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3) y los flujos de trabajo dentro de Windows Workflow Foundation en [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4).</span><span class="sxs-lookup"><span data-stu-id="ad52a-103">The <xref:System.Activities.Statements.Interop> activity can be used to execute activities from Windows Workflow Foundation (WF) in [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] and [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3), and workflows within Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4).</span></span> <span data-ttu-id="ad52a-104">En este ejemplo se muestra cómo configurar y ejecutar un flujo de trabajo WF3 que utiliza <xref:System.Workflow.Activities.ExternalDataExchangeService> (y las actividades personalizadas correspondientes para llamar a los métodos y administrar los eventos) utilizando la actividad <xref:System.Activities.Statements.Interop> en un servicio de flujo de trabajo WF4.</span><span class="sxs-lookup"><span data-stu-id="ad52a-104">This sample shows how to configure and run a WF3 workflow that uses <xref:System.Workflow.Activities.ExternalDataExchangeService> (and corresponding custom activities for calling methods and handling events) by using the <xref:System.Activities.Statements.Interop> activity in a WF4 workflow service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ad52a-105">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ad52a-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ad52a-106">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ad52a-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ad52a-107">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ad52a-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ad52a-108">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="ad52a-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ad52a-109">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad52a-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="ad52a-110">Abra el archivo ExternalDataExchange.sln de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad52a-110">Open the ExternalDataExchange.sln file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="ad52a-111">Para generar el ejemplo, presione Ctrl+Mayús+B.</span><span class="sxs-lookup"><span data-stu-id="ad52a-111">To build the sample, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="ad52a-112">Para ejecutar el ejemplo, presione F5.</span><span class="sxs-lookup"><span data-stu-id="ad52a-112">To run the sample, press F5.</span></span>
