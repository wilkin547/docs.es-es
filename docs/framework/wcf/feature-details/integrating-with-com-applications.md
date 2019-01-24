---
title: Integración en aplicaciones COM
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
ms.openlocfilehash: 8fa802ce20bfde3579258a5d34bc5d7f68aaaea3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657407"
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="e813b-102">Integración en aplicaciones COM</span><span class="sxs-lookup"><span data-stu-id="e813b-102">Integrating with COM Applications</span></span>
<span data-ttu-id="e813b-103">Servicios Windows Communication Foundation (WCF) se pueden integrar directamente en el código existente mediante el moniker de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="e813b-103">Windows Communication Foundation (WCF) services can be integrated directly into your existing code by using the WCF service moniker.</span></span> <span data-ttu-id="e813b-104">El moniker de servicio se puede utilizar a partir de una gama amplia de entornos de desarrollo basados en COM, como Office VBA, Visual Basic 6.0 o Visual C++ 6.0.</span><span class="sxs-lookup"><span data-stu-id="e813b-104">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e813b-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e813b-105">In This Section</span></span>  
 [<span data-ttu-id="e813b-106">Integración en la información general de las aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="e813b-106">Integrating with COM Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 <span data-ttu-id="e813b-107">Proporciona información general de las partes principales del proceso de la integración.</span><span class="sxs-lookup"><span data-stu-id="e813b-107">Gives an overview of the major parts of the integration process.</span></span>  
  
 [<span data-ttu-id="e813b-108">Cómo: Registrar y configurar un Moniker de servicio</span><span class="sxs-lookup"><span data-stu-id="e813b-108">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 <span data-ttu-id="e813b-109">Para utilizar el moniker de servicio WCF dentro de una aplicación de COM, registre los tipos con atributos necesarios con COM y configurar la aplicación COM y el moniker con la configuración de enlace necesaria.</span><span class="sxs-lookup"><span data-stu-id="e813b-109">To use the WCF service moniker within a COM application, register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
 [<span data-ttu-id="e813b-110">Cómo: Utilice el Moniker de servicio de Windows Communication Foundation sin registrarse</span><span class="sxs-lookup"><span data-stu-id="e813b-110">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 <span data-ttu-id="e813b-111">Explica cómo obtener la definición del contrato en forma de un documento de Lenguaje de Definición de servicios Web (WSDL) o de un punto de conexión de WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="e813b-111">Explains how to obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document or from a WS-MetadataExchange endpoint.</span></span>  
  
 [<span data-ttu-id="e813b-112">Cómo: Utilizar un Moniker de servicio con contratos WSDL</span><span class="sxs-lookup"><span data-stu-id="e813b-112">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 <span data-ttu-id="e813b-113">Describe cómo llamar a un ejemplo WCF mediante un moniker WSDL de WCF.</span><span class="sxs-lookup"><span data-stu-id="e813b-113">Describes how to call a WCF sample using a WCF WSDL moniker.</span></span>  
  
 [<span data-ttu-id="e813b-114">Cómo: Uso de un Moniker de servicio con contratos de intercambio de metadatos</span><span class="sxs-lookup"><span data-stu-id="e813b-114">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 <span data-ttu-id="e813b-115">Describe cómo llamar a un ejemplo de WCF mediante un moniker WCF que especifica un punto de conexión Mex.</span><span class="sxs-lookup"><span data-stu-id="e813b-115">Describes how to call a WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
 [<span data-ttu-id="e813b-116">Cómo: Especifique las credenciales de seguridad del canal</span><span class="sxs-lookup"><span data-stu-id="e813b-116">How to: Specify Channel Security Credentials</span></span>](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 <span data-ttu-id="e813b-117">El moniker de servicio WCF es compatible con la `IChannelCredentials` interfaz que permite una serie de métodos alternativos para especificar las credenciales del canal.</span><span class="sxs-lookup"><span data-stu-id="e813b-117">The WCF service moniker supports the `IChannelCredentials` interface that allows a range of alternate methods for specifying channel credentials.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e813b-118">Referencia</span><span class="sxs-lookup"><span data-stu-id="e813b-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="e813b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e813b-119">See also</span></span>
- [<span data-ttu-id="e813b-120">Integración en aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="e813b-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
