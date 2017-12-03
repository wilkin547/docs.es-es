---
title: "Activación XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ac691e3d24e3526b43a6818fbe6bbb33a3375a7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="xaml-activation"></a><span data-ttu-id="bd04c-102">Activación XAML</span><span class="sxs-lookup"><span data-stu-id="bd04c-102">XAML Activation</span></span>
<span data-ttu-id="bd04c-103">En este ejemplo se muestra cómo hospedar un flujo de trabajo declarativo en IIS.</span><span class="sxs-lookup"><span data-stu-id="bd04c-103">This sample demonstrates how to host a declarative workflow in IIS.</span></span> <span data-ttu-id="bd04c-104">El ejemplo es un flujo de trabajo básico llamado `EchoService` que incluye una operación.</span><span class="sxs-lookup"><span data-stu-id="bd04c-104">The sample is a basic workflow called `EchoService` that has one operation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bd04c-105">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="bd04c-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bd04c-106">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="bd04c-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bd04c-107">Si este directorio no existe, vaya a (página de descarga) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd04c-107">If this directory does not exist, go to (download page) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bd04c-108">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="bd04c-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bd04c-109">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd04c-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="bd04c-110">Abra la solución XAMLActivation.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd04c-110">Open the XAMLActivation.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="bd04c-111">Compile la solución presionando **F5**.</span><span class="sxs-lookup"><span data-stu-id="bd04c-111">Build the solution by pressing **F5**.</span></span>  
  
3.  <span data-ttu-id="bd04c-112">Ejecute WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="bd04c-112">Run WcfTestClient.exe.</span></span> <span data-ttu-id="bd04c-113">En un símbolo del sistema, escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="bd04c-113">From a command prompt, type in the following:</span></span>  
  
    1.  <span data-ttu-id="bd04c-114">cd %SystemDrive%\Archivos de programa\Microsoft Visual Studio 10.0\Common7\IDE</span><span class="sxs-lookup"><span data-stu-id="bd04c-114">cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE</span></span>  
  
    2.  <span data-ttu-id="bd04c-115">Ejecute WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="bd04c-115">Run WcfTestClient.exe.</span></span>  
  
4.  <span data-ttu-id="bd04c-116">Establezca la dirección del servicio en WcfTestClient.exe presionando CTRL+SHIFT+A y estableciendo la dirección de servicio en http://localhost:56133/Service.xamlx.</span><span class="sxs-lookup"><span data-stu-id="bd04c-116">Set the address of the service on WcfTestClient.exe by pressing CTRL+SHIFT+A and setting the service address to http://localhost:56133/Service.xamlx.</span></span>  
  
5.  <span data-ttu-id="bd04c-117">Realice la operación de eco para probar el servicio.</span><span class="sxs-lookup"><span data-stu-id="bd04c-117">Perform the echo operation to test the service.</span></span>  
  
6.  <span data-ttu-id="bd04c-118">Implemente el servicio en IIS usando DeployToIIS.Bat en un símbolo del sistema con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="bd04c-118">Deploy the Service in IIS using DeployToIIS.Bat in a command prompt with administrator privileges.</span></span>  
  
7.  <span data-ttu-id="bd04c-119">Actualice la dirección de servicio en el cliente a http://localhost/XAMLActivation/Service.xamlx y pruebe el servicio de nuevo mediante WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="bd04c-119">Update the service address in the client to http://localhost/XAMLActivation/Service.xamlx and test the service again using WcfTestClient.exe.</span></span>
