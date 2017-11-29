---
title: "Ejemplo de detección de flujo de trabajo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f778fead0e09be36ca2a829dde9cf906f4fcaa9f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="workflow-discovery-sample"></a><span data-ttu-id="9ef39-102">Ejemplo de detección de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="9ef39-102">Workflow Discovery Sample</span></span>
<span data-ttu-id="9ef39-103">En este ejemplo se muestra cómo hacer que un servicio de flujo de trabajo se pueda detectar y cómo crear una actividad de código personalizada que busque un servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="9ef39-103">This sample demonstrates how to make a workflow service discoverable and how to author a custom code activity that searches for a particular service.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="9ef39-104">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="9ef39-104">Demonstrates</span></span>  
 <span data-ttu-id="9ef39-105">Actividad de búsqueda de detección y uso del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="9ef39-105">Discovery Find Activity and Workflow Usage</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="9ef39-106">Explicación</span><span class="sxs-lookup"><span data-stu-id="9ef39-106">Discussion</span></span>  
 <span data-ttu-id="9ef39-107">En la primera parte del ejemplo, se hace que un servicio de flujo de trabajo se pueda detectar mediante la configuración.</span><span class="sxs-lookup"><span data-stu-id="9ef39-107">In the first part of the sample, a workflow service is made discoverable using configuration.</span></span> <span data-ttu-id="9ef39-108">La configuración también se puede utilizar para aplicar el servicio de forma apropiada con los metadatos personalizados (como los ámbitos).</span><span class="sxs-lookup"><span data-stu-id="9ef39-108">Configuration can also be used to apply the service appropriately with custom metadata (such as scopes).</span></span> <span data-ttu-id="9ef39-109">En el cliente, el ejemplo utiliza una actividad de código personalizada, que utiliza Detección para buscar un servicio que coincide con un contrato determinado.</span><span class="sxs-lookup"><span data-stu-id="9ef39-109">On the client, the sample uses a custom code activity, which uses Discovery to search for a service matching a particular contract.</span></span> <span data-ttu-id="9ef39-110">La actividad de código genera un URI, que se utiliza después en una actividad de envío.</span><span class="sxs-lookup"><span data-stu-id="9ef39-110">The code activity outputs a URI, which is later used by a send activity.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9ef39-111">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ef39-111">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="9ef39-112">Este ejemplo utiliza los extremos HTTP, que deben tener las ACL de dirección URL apropiadas para que se ejecute (vea [configurar HTTP y HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="9ef39-112">This sample uses HTTP endpoints, which must have proper URL ACLs to run (see [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) for details).</span></span> <span data-ttu-id="9ef39-113">Al ejecutar el siguiente comando en un símbolo del sistema con permisos elevados, se deberían agregar las ACL adecuadas.</span><span class="sxs-lookup"><span data-stu-id="9ef39-113">Executing the following command at an elevated command prompt should add the appropriate ACLs.</span></span> <span data-ttu-id="9ef39-114">Sustituya su dominio y nombre de usuario para los siguientes argumentos si su shell no entiende el formato de variable.</span><span class="sxs-lookup"><span data-stu-id="9ef39-114">Substitute your Domain and Username for the following arguments if your shell does not understand the variable format.</span></span>  
  
     <span data-ttu-id="9ef39-115">**netsh http agregar dirección url urlacl = http: / / +: 8000 / usuario = % DOMAIN %\\% UserName %**</span><span class="sxs-lookup"><span data-stu-id="9ef39-115">**netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\\%UserName%**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9ef39-116">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="9ef39-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9ef39-117">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="9ef39-117">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9ef39-118">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ef39-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9ef39-119">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="9ef39-119">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`
