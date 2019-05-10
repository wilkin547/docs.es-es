---
title: Cambiar el nombre de un servicio WCF
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: 8cb86621972423f55bfa18c60c1d4eb60cacb205
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651041"
---
# <a name="renaming-a-wcf-service"></a><span data-ttu-id="67ddd-102">Cambiar el nombre de un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="67ddd-102">Renaming a WCF Service</span></span>
<span data-ttu-id="67ddd-103">Este tema describe cómo puede cambiar el nombre de un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="67ddd-103">This topic describes how you can rename a Windows Communication Foundation (WCF) service.</span></span>  
  
## <a name="renaming-a-wcf-service"></a><span data-ttu-id="67ddd-104">Cambiar el nombre de un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="67ddd-104">Renaming a WCF Service</span></span>  
 <span data-ttu-id="67ddd-105">Realice los pasos siguientes para cambiar el nombre de un servicio en una plantilla de Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="67ddd-105">Perform the following steps to rename a service in a Windows Communication Foundation (WCF) template,</span></span>  
  
- <span data-ttu-id="67ddd-106">Cambie el nombre de la clase que implementa el servicio.</span><span class="sxs-lookup"><span data-stu-id="67ddd-106">Change the name of the class that implements the service.</span></span>  
  
- <span data-ttu-id="67ddd-107">En el archivo de configuración del servicio, cambie el nombre del servicio al nuevo nombre que haya elegido, tal y como se indica en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="67ddd-107">In the configuration file of the service, change the name of the service to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="67ddd-108">El archivo de configuración puede ser app.config o web.config, en función de de su modelo de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="67ddd-108">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- <span data-ttu-id="67ddd-109">Si su servicio es hospedado mediante web, utiliza un \* archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="67ddd-109">If your service is webhosted, it uses an \*.svc file.</span></span> <span data-ttu-id="67ddd-110">Abra el archivo svc y modifique el nombre de su servicio tal y como se indica en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="67ddd-110">Open the svc file and modify the name of your service as indicated in the following example.</span></span> <span data-ttu-id="67ddd-111">Este paso no es necesario para aplicaciones autohospedadas, puesto que no hay ningún archivo svc.</span><span class="sxs-lookup"><span data-stu-id="67ddd-111">This step is not necessary for self-hosted applications, as there is no svc file.</span></span>  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a><span data-ttu-id="67ddd-112">Cambio del nombre de un contrato de servicios de WCF</span><span class="sxs-lookup"><span data-stu-id="67ddd-112">Renaming a WCF Service Contract</span></span>  
  
- <span data-ttu-id="67ddd-113">Realice los siguientes pasos para cambiar el nombre del contrato de servicios:</span><span class="sxs-lookup"><span data-stu-id="67ddd-113">Perform the following steps to rename the service contract,</span></span>  
  
- <span data-ttu-id="67ddd-114">Cambie el nombre del contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="67ddd-114">Change the name of the service contract.</span></span>  
  
- <span data-ttu-id="67ddd-115">En el archivo de configuración del servicio, cambie el nombre del contrato de servicios al nuevo nombre que haya elegido, tal y como se indica en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="67ddd-115">In the configuration file of the service, change the name of the service contract to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="67ddd-116">El archivo de configuración puede ser app.config o web.config, en función de de su modelo de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="67ddd-116">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
