---
title: "Servicio solo XAML básico"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c106feb0-0245-43b5-aefe-93ce0e4d38eb
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 004a37682b855135998ef4620e673421f769326d
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="basic-xaml-only-service"></a><span data-ttu-id="911bb-102">Servicio solo XAML básico</span><span class="sxs-lookup"><span data-stu-id="911bb-102">Basic XAML only Service</span></span>
<span data-ttu-id="911bb-103">En este ejemplo se muestra cómo crear un servicio solo XAML.</span><span class="sxs-lookup"><span data-stu-id="911bb-103">This sample demonstrates how to create a XAML only service.</span></span> <span data-ttu-id="911bb-104">El escenario es un servicio del diagnóstico de problemas relacionados con el coche.</span><span class="sxs-lookup"><span data-stu-id="911bb-104">The scenario is a diagnostics service for car-related problems.</span></span> <span data-ttu-id="911bb-105">El servicio se implementa como un flujo de trabajo que hace una serie de preguntas al cliente para diagnosticar el problema.</span><span class="sxs-lookup"><span data-stu-id="911bb-105">The service is implemented as a workflow that asks the client a series of questions to diagnose the problem.</span></span> <span data-ttu-id="911bb-106">Hay dos tipos de problemas que el servicio puede diagnosticar (el coche no arranca o el aire acondicionado no funciona).</span><span class="sxs-lookup"><span data-stu-id="911bb-106">There are two types of issues the service can diagnose (car does not start or air conditioning not working).</span></span> <span data-ttu-id="911bb-107">El flujo de trabajo utiliza la plantilla de solicitud/respuesta del diseñador para exponer tres operaciones de servicio simples.</span><span class="sxs-lookup"><span data-stu-id="911bb-107">The workflow uses Request/Reply template from the designer to expose three simple service operations.</span></span> <span data-ttu-id="911bb-108">El servicio se hospeda en IIS al crear un directorio virtual en IIS y copiar los archivos service1.xamlx y web.config en el directorio virtual; no se requiere ningún código compilado.</span><span class="sxs-lookup"><span data-stu-id="911bb-108">The service is hosted in IIS by creating a virtual directory in IIS and copying the service1.xamlx and Web.config files into the virtual directory, no compiled code is required.</span></span> <span data-ttu-id="911bb-109">De forma predeterminada en este ejemplo copiará automáticamente los archivos necesarios en el directorio virtual creado al seguir las instrucciones de instalación para los ejemplos de WCF y WF: [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) cuando se compila en Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="911bb-109">By default this sample will automatically copy the needed files into the virtual directory created when you follow the setup instructions for the WCF and WF samples: [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) when built in Visual Studio 2010.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="911bb-110">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="911bb-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="911bb-111">Cargue la solución de proyecto en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="911bb-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="911bb-112">Ejecute la aplicación cliente generada en [directorio base de la solución] \Client\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="911bb-112">Run the Client application generated in [solution base directory]\Client\bin\debug.</span></span>  
  
3.  <span data-ttu-id="911bb-113">La aplicación imprime las opciones; seleccione una.</span><span class="sxs-lookup"><span data-stu-id="911bb-113">The application prints out options, selects an option.</span></span> <span data-ttu-id="911bb-114">A continuación, la aplicación hace algunas preguntas, responda sí o no (utilizando las claves Y/N).</span><span class="sxs-lookup"><span data-stu-id="911bb-114">The application then asks some questions, answer them yes or no (using Y/N keys).</span></span> <span data-ttu-id="911bb-115">Cuando el servicio ha terminado de diagnosticar los problemas, la aplicación imprime un diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="911bb-115">When the service is done diagnosing the issues, the application prints out a diagnosis.</span></span>  
  
4.  <span data-ttu-id="911bb-116">La aplicación regresa a las opciones.</span><span class="sxs-lookup"><span data-stu-id="911bb-116">The application goes back to the options.</span></span> <span data-ttu-id="911bb-117">Puede diagnosticar otro problema o salir la aplicación.</span><span class="sxs-lookup"><span data-stu-id="911bb-117">You can diagnose another problem or exit the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="911bb-118">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="911bb-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="911bb-119">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="911bb-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="911bb-120">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="911bb-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="911bb-121">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="911bb-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLService`