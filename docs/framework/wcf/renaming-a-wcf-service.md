---
description: Más información acerca de cómo cambiar el nombre de un servicio WCF
title: Cambiar el nombre de un servicio WCF
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: 8d75e43f4bda97e8ee6de34b039eb1236d6c4a6d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779171"
---
# <a name="renaming-a-wcf-service"></a><span data-ttu-id="8755a-103">Cambiar el nombre de un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="8755a-103">Renaming a WCF Service</span></span>

<span data-ttu-id="8755a-104">En este tema se describe cómo se puede cambiar el nombre de un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8755a-104">This topic describes how you can rename a Windows Communication Foundation (WCF) service.</span></span>  
  
## <a name="renaming-a-wcf-service"></a><span data-ttu-id="8755a-105">Cambiar el nombre de un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="8755a-105">Renaming a WCF Service</span></span>  

 <span data-ttu-id="8755a-106">Realice los pasos siguientes para cambiar el nombre de un servicio en una plantilla Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8755a-106">Perform the following steps to rename a service in a Windows Communication Foundation (WCF) template,</span></span>  
  
- <span data-ttu-id="8755a-107">Cambie el nombre de la clase que implementa el servicio.</span><span class="sxs-lookup"><span data-stu-id="8755a-107">Change the name of the class that implements the service.</span></span>  
  
- <span data-ttu-id="8755a-108">En el archivo de configuración del servicio, cambie el nombre del servicio al nuevo nombre que haya elegido, tal y como se indica en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8755a-108">In the configuration file of the service, change the name of the service to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="8755a-109">El archivo de configuración puede ser app.config o web.config, en función de de su modelo de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="8755a-109">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- <span data-ttu-id="8755a-110">Si el servicio es webhosted, usa un archivo *\* . SVC* .</span><span class="sxs-lookup"><span data-stu-id="8755a-110">If your service is webhosted, it uses an *\*.svc* file.</span></span> <span data-ttu-id="8755a-111">Abra el archivo svc y modifique el nombre de su servicio tal y como se indica en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8755a-111">Open the svc file and modify the name of your service as indicated in the following example.</span></span> <span data-ttu-id="8755a-112">Este paso no es necesario para aplicaciones autohospedadas, puesto que no hay ningún archivo svc.</span><span class="sxs-lookup"><span data-stu-id="8755a-112">This step is not necessary for self-hosted applications, as there is no svc file.</span></span>  
  
```aspx-csharp
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a><span data-ttu-id="8755a-113">Cambio del nombre de un contrato de servicios de WCF</span><span class="sxs-lookup"><span data-stu-id="8755a-113">Renaming a WCF Service Contract</span></span>  
  
- <span data-ttu-id="8755a-114">Realice los siguientes pasos para cambiar el nombre del contrato de servicios:</span><span class="sxs-lookup"><span data-stu-id="8755a-114">Perform the following steps to rename the service contract,</span></span>  
  
- <span data-ttu-id="8755a-115">Cambie el nombre del contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="8755a-115">Change the name of the service contract.</span></span>  
  
- <span data-ttu-id="8755a-116">En el archivo de configuración del servicio, cambie el nombre del contrato de servicios al nuevo nombre que haya elegido, tal y como se indica en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8755a-116">In the configuration file of the service, change the name of the service contract to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="8755a-117">El archivo de configuración puede ser app.config o web.config, en función de de su modelo de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="8755a-117">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
