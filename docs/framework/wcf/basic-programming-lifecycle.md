---
title: "Ciclo de vida de programación básica"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
caps.latest.revision: "36"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f17b37b77c157f1ce3d5ee40fd6464ab378039d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="basic-programming-lifecycle"></a><span data-ttu-id="a11fb-102">Ciclo de vida de programación básica</span><span class="sxs-lookup"><span data-stu-id="a11fb-102">Basic Programming Lifecycle</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="a11fb-103"> permite a las aplicaciones comunicar si están en el mismo equipo, en Internet o en diferentes plataformas de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a11fb-103"> enables applications to communicate whether they are on the same computer, across the Internet, or on different application platforms.</span></span> <span data-ttu-id="a11fb-104">En este tema se describen las tareas necesarias para crear una aplicación de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a11fb-104">This topic outlines the tasks that are required to build a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="a11fb-105">Para una aplicación de ejemplo de trabajo, consulte [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="a11fb-105">For a working sample application, see [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
## <a name="the-basic-tasks"></a><span data-ttu-id="a11fb-106">Las tareas básicas</span><span class="sxs-lookup"><span data-stu-id="a11fb-106">The Basic Tasks</span></span>  
 <span data-ttu-id="a11fb-107">Las tareas básicas que se van a realizar son, en orden:</span><span class="sxs-lookup"><span data-stu-id="a11fb-107">The basic tasks to perform are, in order:</span></span>  
  
1.  <span data-ttu-id="a11fb-108">Definir el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="a11fb-108">Define the service contract.</span></span> <span data-ttu-id="a11fb-109">Un contrato de servicio especifica la firma de un servicio, los datos que intercambia y el resto de los datos necesarios contractualmente.</span><span class="sxs-lookup"><span data-stu-id="a11fb-109">A service contract specifies the signature of a service, the data it exchanges, and other contractually required data.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="a11fb-110">[Diseñar contratos de servicio](../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="a11fb-110"> [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
2.  <span data-ttu-id="a11fb-111">Implementar el contrato.</span><span class="sxs-lookup"><span data-stu-id="a11fb-111">Implement the contract.</span></span> <span data-ttu-id="a11fb-112">Para implementar un contrato de servicio, cree una clase que implemente el contrato y especifique comportamientos personalizados que deba tener el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a11fb-112">To implement a service contract, create a class that implements the contract and specify custom behaviors that the runtime should have.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="a11fb-113">[Implementación de contratos de servicio](../../../docs/framework/wcf/implementing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="a11fb-113"> [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md).</span></span>  
  
3.  <span data-ttu-id="a11fb-114">Configurar el servicio especificando los extremos y el resto de la información de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="a11fb-114">Configure the service by specifying endpoints and other behavior information.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="a11fb-115">[Configuración de servicios](../../../docs/framework/wcf/configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="a11fb-115"> [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
4.  <span data-ttu-id="a11fb-116">Hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="a11fb-116">Host the service.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="a11fb-117">[Servicios de hospedaje](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="a11fb-117"> [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
5.  <span data-ttu-id="a11fb-118">Compilar una aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="a11fb-118">Build a client application.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="a11fb-119">[Generar clientes](../../../docs/framework/wcf/building-clients.md).</span><span class="sxs-lookup"><span data-stu-id="a11fb-119"> [Building Clients](../../../docs/framework/wcf/building-clients.md).</span></span>  
  
 <span data-ttu-id="a11fb-120">Aunque los temas de esta sección sigan este orden, algunos escenarios no se inician al principio.</span><span class="sxs-lookup"><span data-stu-id="a11fb-120">Although the topics in this section follow this order, some scenarios do not start at the beginning.</span></span> <span data-ttu-id="a11fb-121">Por ejemplo, si desea crear un cliente para un servicio existente, ha de comenzar en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="a11fb-121">For example, if you want to build a client for a pre-existing service, you start at step 5.</span></span> <span data-ttu-id="a11fb-122">O si está creando un servicio que usarán otros, puede omitir el paso 5.</span><span class="sxs-lookup"><span data-stu-id="a11fb-122">Or if you are building a service that others will use, you may skip step 5.</span></span>  
  
 <span data-ttu-id="a11fb-123">Una vez que esté familiarizado con el desarrollo de contratos de servicio, también se puede leer [Introducción a la extensibilidad](../../../docs/framework/wcf/introduction-to-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="a11fb-123">Once you are familiar with developing service contracts, you can also read [Introduction to Extensibility](../../../docs/framework/wcf/introduction-to-extensibility.md).</span></span> <span data-ttu-id="a11fb-124">Si tiene problemas con el servicio, consulte [inicio rápido de solución de problemas de WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) para ver si otros usuarios tienen los problemas de iguales o similares.</span><span class="sxs-lookup"><span data-stu-id="a11fb-124">If you have problems with your service, check [WCF Troubleshooting Quickstart](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) to see whether others have the same or similar problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a11fb-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a11fb-125">See Also</span></span>  
 [<span data-ttu-id="a11fb-126">Implementación de contratos de servicio</span><span class="sxs-lookup"><span data-stu-id="a11fb-126">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
