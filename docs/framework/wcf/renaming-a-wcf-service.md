---
title: Cambiar el nombre de un servicio WCF
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: 1179e7b235130e1967c79843b7a11f55622a01fb
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052057"
---
# <a name="renaming-a-wcf-service"></a><span data-ttu-id="a07a2-102">Cambiar el nombre de un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="a07a2-102">Renaming a WCF Service</span></span>
<span data-ttu-id="a07a2-103">En este tema se describe cómo se puede cambiar el nombre de un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a07a2-103">This topic describes how you can rename a Windows Communication Foundation (WCF) service.</span></span>  
  
## <a name="renaming-a-wcf-service"></a><span data-ttu-id="a07a2-104">Cambiar el nombre de un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="a07a2-104">Renaming a WCF Service</span></span>  
 <span data-ttu-id="a07a2-105">Realice los pasos siguientes para cambiar el nombre de un servicio en una plantilla Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a07a2-105">Perform the following steps to rename a service in a Windows Communication Foundation (WCF) template,</span></span>  
  
- <span data-ttu-id="a07a2-106">Cambie el nombre de la clase que implementa el servicio.</span><span class="sxs-lookup"><span data-stu-id="a07a2-106">Change the name of the class that implements the service.</span></span>  
  
- <span data-ttu-id="a07a2-107">En el archivo de configuración del servicio, cambie el nombre del servicio al nuevo nombre que haya elegido, tal y como se indica en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a07a2-107">In the configuration file of the service, change the name of the service to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="a07a2-108">El archivo de configuración puede ser app.config o web.config, en función de de su modelo de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="a07a2-108">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- <span data-ttu-id="a07a2-109">Si el servicio es webhosted, usa un archivo \* \* . SVC\* .</span><span class="sxs-lookup"><span data-stu-id="a07a2-109">If your service is webhosted, it uses an *\*.svc* file.</span></span> <span data-ttu-id="a07a2-110">Abra el archivo svc y modifique el nombre de su servicio tal y como se indica en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a07a2-110">Open the svc file and modify the name of your service as indicated in the following example.</span></span> <span data-ttu-id="a07a2-111">Este paso no es necesario para aplicaciones autohospedadas, puesto que no hay ningún archivo svc.</span><span class="sxs-lookup"><span data-stu-id="a07a2-111">This step is not necessary for self-hosted applications, as there is no svc file.</span></span>  
  
```aspx-csharp
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a><span data-ttu-id="a07a2-112">Cambio del nombre de un contrato de servicios de WCF</span><span class="sxs-lookup"><span data-stu-id="a07a2-112">Renaming a WCF Service Contract</span></span>  
  
- <span data-ttu-id="a07a2-113">Realice los siguientes pasos para cambiar el nombre del contrato de servicios:</span><span class="sxs-lookup"><span data-stu-id="a07a2-113">Perform the following steps to rename the service contract,</span></span>  
  
- <span data-ttu-id="a07a2-114">Cambie el nombre del contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="a07a2-114">Change the name of the service contract.</span></span>  
  
- <span data-ttu-id="a07a2-115">En el archivo de configuración del servicio, cambie el nombre del contrato de servicios al nuevo nombre que haya elegido, tal y como se indica en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a07a2-115">In the configuration file of the service, change the name of the service contract to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="a07a2-116">El archivo de configuración puede ser app.config o web.config, en función de de su modelo de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="a07a2-116">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
