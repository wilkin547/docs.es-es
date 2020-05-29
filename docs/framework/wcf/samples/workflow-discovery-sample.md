---
title: Ejemplo de detección de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
ms.openlocfilehash: 1c6210472b594aec02bdf47f472a1a8b1823230c
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202072"
---
# <a name="workflow-discovery-sample"></a><span data-ttu-id="7c88a-102">Ejemplo de detección de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="7c88a-102">Workflow Discovery Sample</span></span>
<span data-ttu-id="7c88a-103">En este ejemplo se muestra cómo hacer que un servicio de flujo de trabajo se pueda detectar y cómo crear una actividad de código personalizada que busque un servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="7c88a-103">This sample demonstrates how to make a workflow service discoverable and how to author a custom code activity that searches for a particular service.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="7c88a-104">Muestra</span><span class="sxs-lookup"><span data-stu-id="7c88a-104">Demonstrates</span></span>  
 <span data-ttu-id="7c88a-105">Actividad de búsqueda de detección y uso del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="7c88a-105">Discovery Find Activity and Workflow Usage</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="7c88a-106">Discusión</span><span class="sxs-lookup"><span data-stu-id="7c88a-106">Discussion</span></span>  
 <span data-ttu-id="7c88a-107">En la primera parte del ejemplo, se hace que un servicio de flujo de trabajo se pueda detectar mediante la configuración.</span><span class="sxs-lookup"><span data-stu-id="7c88a-107">In the first part of the sample, a workflow service is made discoverable using configuration.</span></span> <span data-ttu-id="7c88a-108">La configuración también se puede utilizar para aplicar el servicio de forma apropiada con los metadatos personalizados (como los ámbitos).</span><span class="sxs-lookup"><span data-stu-id="7c88a-108">Configuration can also be used to apply the service appropriately with custom metadata (such as scopes).</span></span> <span data-ttu-id="7c88a-109">En el cliente, el ejemplo utiliza una actividad de código personalizada, que utiliza Detección para buscar un servicio que coincide con un contrato determinado.</span><span class="sxs-lookup"><span data-stu-id="7c88a-109">On the client, the sample uses a custom code activity, which uses Discovery to search for a service matching a particular contract.</span></span> <span data-ttu-id="7c88a-110">La actividad de código genera un URI, que se utiliza después en una actividad de envío.</span><span class="sxs-lookup"><span data-stu-id="7c88a-110">The code activity outputs a URI, which is later used by a send activity.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7c88a-111">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c88a-111">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="7c88a-112">Este ejemplo utiliza puntos de conexión HTTP, que deben tener las ACL de dirección URL apropiadas para ejecutarse (consulte [configuración de http y https](../feature-details/configuring-http-and-https.md) para obtener detalles).</span><span class="sxs-lookup"><span data-stu-id="7c88a-112">This sample uses HTTP endpoints, which must have proper URL ACLs to run (see [Configuring HTTP and HTTPS](../feature-details/configuring-http-and-https.md) for details).</span></span> <span data-ttu-id="7c88a-113">Al ejecutar el siguiente comando en un símbolo del sistema con permisos elevados, se deberían agregar las ACL adecuadas.</span><span class="sxs-lookup"><span data-stu-id="7c88a-113">Executing the following command at an elevated command prompt should add the appropriate ACLs.</span></span> <span data-ttu-id="7c88a-114">Si el shell no entiende el formato de variable, sustituya el dominio y el nombre de usuario por los argumentos siguientes.</span><span class="sxs-lookup"><span data-stu-id="7c88a-114">If your shell does not understand the variable format, substitute your Domain and Username for the following arguments.</span></span>  
  
    `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`
  
> [!IMPORTANT]
> <span data-ttu-id="7c88a-115">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="7c88a-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7c88a-116">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="7c88a-116">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="7c88a-117">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="7c88a-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7c88a-118">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="7c88a-118">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`
