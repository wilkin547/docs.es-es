---
title: "Integración en aplicaciones COM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bfe452b41c39598e237633490d09cd267fda04ec
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="afeac-102">Integración en aplicaciones COM</span><span class="sxs-lookup"><span data-stu-id="afeac-102">Integrating with COM Applications</span></span>
<span data-ttu-id="afeac-103">Los servicios [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se pueden integrar directamente en su código existente mediante el moniker del servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="afeac-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services can be integrated directly into your existing code by using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker.</span></span> <span data-ttu-id="afeac-104">El moniker de servicio se puede utilizar a partir de una gama amplia de entornos de desarrollo basados en COM, como Office VBA, Visual Basic 6.0 o Visual C++ 6.0.</span><span class="sxs-lookup"><span data-stu-id="afeac-104">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="afeac-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="afeac-105">In This Section</span></span>  
 [<span data-ttu-id="afeac-106">Integración con la introducción a las aplicaciones COM</span><span class="sxs-lookup"><span data-stu-id="afeac-106">Integrating with COM Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 <span data-ttu-id="afeac-107">Proporciona información general de las partes principales del proceso de la integración.</span><span class="sxs-lookup"><span data-stu-id="afeac-107">Gives an overview of the major parts of the integration process.</span></span>  
  
 [<span data-ttu-id="afeac-108">Cómo: registrar y configurar un Moniker de servicio</span><span class="sxs-lookup"><span data-stu-id="afeac-108">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 <span data-ttu-id="afeac-109">Para utilizar el moniker del servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dentro de una aplicación COM, registre los tipos de atributos necesarios con COM y configure la aplicación COM y el moniker con la configuración de enlace necesaria.</span><span class="sxs-lookup"><span data-stu-id="afeac-109">To use the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker within a COM application, register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
 [<span data-ttu-id="afeac-110">Cómo: utilizar el Moniker de servicio de Windows Communication Foundation sin registro</span><span class="sxs-lookup"><span data-stu-id="afeac-110">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 <span data-ttu-id="afeac-111">Explica cómo obtener la definición del contrato en forma de un documento de Lenguaje de Definición de servicios Web (WSDL) o de un punto de conexión de WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="afeac-111">Explains how to obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document or from a WS-MetadataExchange endpoint.</span></span>  
  
 [<span data-ttu-id="afeac-112">Cómo: utilizar un Moniker de servicio con contratos WSDL</span><span class="sxs-lookup"><span data-stu-id="afeac-112">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 <span data-ttu-id="afeac-113">Describe cómo llamar a un ejemplo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante un moniker de WSDL [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="afeac-113">Describes how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WSDL moniker.</span></span>  
  
 [<span data-ttu-id="afeac-114">Cómo: utilizar un Moniker de servicio con contratos de intercambio de metadatos</span><span class="sxs-lookup"><span data-stu-id="afeac-114">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 <span data-ttu-id="afeac-115">Describe cómo llamar a un ejemplo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante un moniker [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que especifica un extremo de Mex.</span><span class="sxs-lookup"><span data-stu-id="afeac-115">Describes how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker that specifies a Mex endpoint.</span></span>  
  
 [<span data-ttu-id="afeac-116">Cómo: especificar las credenciales de seguridad del canal</span><span class="sxs-lookup"><span data-stu-id="afeac-116">How to: Specify Channel Security Credentials</span></span>](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 <span data-ttu-id="afeac-117">El moniker del servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite la interfaz `IChannelCredentials` que permite una serie de métodos alternativos para especificar las credenciales del canal.</span><span class="sxs-lookup"><span data-stu-id="afeac-117">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker supports the `IChannelCredentials` interface that allows a range of alternate methods for specifying channel credentials.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="afeac-118">Referencia</span><span class="sxs-lookup"><span data-stu-id="afeac-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="afeac-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="afeac-119">See Also</span></span>  
 [<span data-ttu-id="afeac-120">Integración con aplicaciones COM +</span><span class="sxs-lookup"><span data-stu-id="afeac-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
