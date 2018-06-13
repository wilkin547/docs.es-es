---
title: Activación XAML
ms.date: 03/30/2017
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
ms.openlocfilehash: 8621b0ea7b390c81e76ac7eeedb0b547b44320d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517717"
---
# <a name="xaml-activation"></a><span data-ttu-id="f380d-102">Activación XAML</span><span class="sxs-lookup"><span data-stu-id="f380d-102">XAML Activation</span></span>
<span data-ttu-id="f380d-103">En este ejemplo se muestra cómo hospedar un flujo de trabajo declarativo en IIS.</span><span class="sxs-lookup"><span data-stu-id="f380d-103">This sample demonstrates how to host a declarative workflow in IIS.</span></span> <span data-ttu-id="f380d-104">El ejemplo es un flujo de trabajo básico llamado `EchoService` que incluye una operación.</span><span class="sxs-lookup"><span data-stu-id="f380d-104">The sample is a basic workflow called `EchoService` that has one operation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f380d-105">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="f380d-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f380d-106">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="f380d-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f380d-107">Si este directorio no existe, vaya a (página de descarga) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f380d-107">If this directory does not exist, go to (download page) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f380d-108">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="f380d-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f380d-109">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="f380d-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f380d-110">Abra la solución XAMLActivation.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f380d-110">Open the XAMLActivation.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="f380d-111">Compile la solución presionando **F5**.</span><span class="sxs-lookup"><span data-stu-id="f380d-111">Build the solution by pressing **F5**.</span></span>  
  
3.  <span data-ttu-id="f380d-112">Ejecute WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="f380d-112">Run WcfTestClient.exe.</span></span> <span data-ttu-id="f380d-113">En un símbolo del sistema, escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="f380d-113">From a command prompt, type in the following:</span></span>  
  
    1.  <span data-ttu-id="f380d-114">cd %SystemDrive%\Archivos de programa\Microsoft Visual Studio 10.0\Common7\IDE</span><span class="sxs-lookup"><span data-stu-id="f380d-114">cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE</span></span>  
  
    2.  <span data-ttu-id="f380d-115">Ejecute WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="f380d-115">Run WcfTestClient.exe.</span></span>  
  
4.  <span data-ttu-id="f380d-116">Establece la dirección del servicio en WcfTestClient.exe presionando CTRL + MAYÚS + A y si se establece la dirección del servicio en http://localhost:56133/Service.xamlx.</span><span class="sxs-lookup"><span data-stu-id="f380d-116">Set the address of the service on WcfTestClient.exe by pressing CTRL+SHIFT+A and setting the service address to http://localhost:56133/Service.xamlx.</span></span>  
  
5.  <span data-ttu-id="f380d-117">Realice la operación de eco para probar el servicio.</span><span class="sxs-lookup"><span data-stu-id="f380d-117">Perform the echo operation to test the service.</span></span>  
  
6.  <span data-ttu-id="f380d-118">Implemente el servicio en IIS usando DeployToIIS.Bat en un símbolo del sistema con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="f380d-118">Deploy the Service in IIS using DeployToIIS.Bat in a command prompt with administrator privileges.</span></span>  
  
7.  <span data-ttu-id="f380d-119">Actualizar la dirección del servicio en el cliente para http://localhost/XAMLActivation/Service.xamlx y pruebe el servicio nuevo mediante WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="f380d-119">Update the service address in the client to http://localhost/XAMLActivation/Service.xamlx and test the service again using WcfTestClient.exe.</span></span>
