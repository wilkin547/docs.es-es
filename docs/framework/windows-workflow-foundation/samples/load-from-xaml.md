---
title: Cargar de XAML
ms.date: 03/30/2017
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
ms.openlocfilehash: 3344f8d35400835ed022ba507954f7f962ff75c8
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086510"
---
# <a name="load-from-xaml"></a><span data-ttu-id="29c85-102">Cargar de XAML</span><span class="sxs-lookup"><span data-stu-id="29c85-102">Load From XAML</span></span>
<span data-ttu-id="29c85-103">En este ejemplo se muestra cómo cargar dinámicamente un flujo de trabajo de XAML sin tener que ejecutar la herramienta XamlBuildTask.</span><span class="sxs-lookup"><span data-stu-id="29c85-103">This sample demonstrates how to dynamically load a XAML workflow without having to run the XamlBuildTask tool.</span></span> <span data-ttu-id="29c85-104">En su lugar, el ejemplo llama al método <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="29c85-104">Instead, the sample calls the <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method.</span></span> <span data-ttu-id="29c85-105">El ejemplo es una aplicación de cliente de Windows Presentation Foundation (WPF) que carga flujos de trabajo XAML mediante el <xref:System.Activities.XamlIntegration.ActivityXamlServices> de clases y los ejecuta.</span><span class="sxs-lookup"><span data-stu-id="29c85-105">The sample is a Windows Presentation Foundation (WPF) client application that loads XAML workflows using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class and executes them.</span></span> <span data-ttu-id="29c85-106">Una vez cargados utilizando la clase <xref:System.Activities.XamlIntegration.ActivityXamlServices>, se devuelve una actividad <xref:System.Activities.DynamicActivity%601> que se puede ejecutar.</span><span class="sxs-lookup"><span data-stu-id="29c85-106">After they have been loaded using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class, a <xref:System.Activities.DynamicActivity%601> is returned that can be executed.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="29c85-107">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="29c85-107">To use this sample</span></span>  
  
1.  <span data-ttu-id="29c85-108">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución LoadFromXAML.sln.</span><span class="sxs-lookup"><span data-stu-id="29c85-108">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LoadFromXAML.sln solution file.</span></span>  
  
2.  <span data-ttu-id="29c85-109">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="29c85-109">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="29c85-110">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="29c85-110">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="29c85-111">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="29c85-111">The samples may already be installed on your machine.</span></span> <span data-ttu-id="29c85-112">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="29c85-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="29c85-113">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="29c85-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="29c85-114">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="29c85-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`