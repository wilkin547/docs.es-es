---
title: Cambiar el nombre de un servicio WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ee707a898bf915491cc1ca44e0606c261dc87dc6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="renaming-a-wcf-service"></a><span data-ttu-id="1e437-102">Cambiar el nombre de un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="1e437-102">Renaming a WCF Service</span></span>
<span data-ttu-id="1e437-103">En este tema se describe cómo cambiar el nombre de un servicio de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e437-103">This topic describes how you can rename a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service.</span></span>  
  
## <a name="renaming-a-wcf-service"></a><span data-ttu-id="1e437-104">Cambiar el nombre de un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="1e437-104">Renaming a WCF Service</span></span>  
 <span data-ttu-id="1e437-105">Realice los pasos siguientes para cambiar el nombre de un servicio en una plantilla de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e437-105">Perform the following steps to rename a service in a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] template,</span></span>  
  
-   <span data-ttu-id="1e437-106">Cambie el nombre de la clase que implementa el servicio.</span><span class="sxs-lookup"><span data-stu-id="1e437-106">Change the name of the class that implements the service.</span></span>  
  
-   <span data-ttu-id="1e437-107">En el archivo de configuración del servicio, cambie el nombre del servicio al nuevo nombre que haya elegido, tal y como se indica en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1e437-107">In the configuration file of the service, change the name of the service to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="1e437-108">El archivo de configuración puede ser app.config o web.config, en función de de su modelo de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="1e437-108">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
-   <span data-ttu-id="1e437-109">Si su servicio es hospedado mediante web, utiliza un * archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="1e437-109">If your service is webhosted, it uses an *.svc file.</span></span> <span data-ttu-id="1e437-110">Abra el archivo svc y modifique el nombre de su servicio tal y como se indica en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1e437-110">Open the svc file and modify the name of your service as indicated in the following example.</span></span> <span data-ttu-id="1e437-111">Este paso no es necesario para aplicaciones autohospedadas, puesto que no hay ningún archivo svc.</span><span class="sxs-lookup"><span data-stu-id="1e437-111">This step is not necessary for self-hosted applications, as there is no svc file.</span></span>  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a><span data-ttu-id="1e437-112">Cambio del nombre de un contrato de servicios de WCF</span><span class="sxs-lookup"><span data-stu-id="1e437-112">Renaming a WCF Service Contract</span></span>  
  
-   <span data-ttu-id="1e437-113">Realice los siguientes pasos para cambiar el nombre del contrato de servicios:</span><span class="sxs-lookup"><span data-stu-id="1e437-113">Perform the following steps to rename the service contract,</span></span>  
  
-   <span data-ttu-id="1e437-114">Cambie el nombre del contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="1e437-114">Change the name of the service contract.</span></span>  
  
-   <span data-ttu-id="1e437-115">En el archivo de configuración del servicio, cambie el nombre del contrato de servicios al nuevo nombre que haya elegido, tal y como se indica en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1e437-115">In the configuration file of the service, change the name of the service contract to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="1e437-116">El archivo de configuración puede ser app.config o web.config, en función de de su modelo de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="1e437-116">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
