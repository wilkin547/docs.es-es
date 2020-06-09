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
ms.openlocfilehash: dc3bbe0ee72ca5583b1e52a61c914ad866a22a05
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596815"
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="c1462-102">Integración en aplicaciones COM</span><span class="sxs-lookup"><span data-stu-id="c1462-102">Integrating with COM Applications</span></span>
<span data-ttu-id="c1462-103">Los servicios Windows Communication Foundation (WCF) se pueden integrar directamente en el código existente mediante el moniker de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="c1462-103">Windows Communication Foundation (WCF) services can be integrated directly into your existing code by using the WCF service moniker.</span></span> <span data-ttu-id="c1462-104">El moniker de servicio se puede utilizar a partir de una gama amplia de entornos de desarrollo basados en COM, como Office VBA, Visual Basic 6.0 o Visual C++ 6.0.</span><span class="sxs-lookup"><span data-stu-id="c1462-104">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1462-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c1462-105">In This Section</span></span>  
 [<span data-ttu-id="c1462-106">Integración con la información general de las aplicaciones COM</span><span class="sxs-lookup"><span data-stu-id="c1462-106">Integrating with COM Applications Overview</span></span>](integrating-with-com-applications-overview.md)  
 <span data-ttu-id="c1462-107">Proporciona información general de las partes principales del proceso de la integración.</span><span class="sxs-lookup"><span data-stu-id="c1462-107">Gives an overview of the major parts of the integration process.</span></span>  
  
 [<span data-ttu-id="c1462-108">Procedimiento para registrar y configurar un moniker de servicio</span><span class="sxs-lookup"><span data-stu-id="c1462-108">How to: Register and Configure a Service Moniker</span></span>](how-to-register-and-configure-a-service-moniker.md)  
 <span data-ttu-id="c1462-109">Para utilizar el moniker de servicio de WCF en una aplicación COM, registre los tipos con atributos necesarios en COM y configure la aplicación COM y el moniker con la configuración de enlace necesaria.</span><span class="sxs-lookup"><span data-stu-id="c1462-109">To use the WCF service moniker within a COM application, register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
 [<span data-ttu-id="c1462-110">Procedimiento para usar el moniker de servicio de Windows Communication Foundation sin registrarse</span><span class="sxs-lookup"><span data-stu-id="c1462-110">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](use-the-wcf-service-moniker-without-registration.md)  
 <span data-ttu-id="c1462-111">Explica cómo obtener la definición del contrato en forma de un documento de Lenguaje de Definición de servicios Web (WSDL) o de un extremo de WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="c1462-111">Explains how to obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document or from a WS-MetadataExchange endpoint.</span></span>  
  
 [<span data-ttu-id="c1462-112">Procedimiento para usar un moniker de servicio con contratos WSDL</span><span class="sxs-lookup"><span data-stu-id="c1462-112">How to: Use a Service Moniker with WSDL Contracts</span></span>](how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 <span data-ttu-id="c1462-113">Describe cómo llamar a un ejemplo WCF con un moniker WSDL de WCF.</span><span class="sxs-lookup"><span data-stu-id="c1462-113">Describes how to call a WCF sample using a WCF WSDL moniker.</span></span>  
  
 [<span data-ttu-id="c1462-114">Procedimiento para usar un moniker de servicio con contratos de intercambio de metadatos</span><span class="sxs-lookup"><span data-stu-id="c1462-114">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>](how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 <span data-ttu-id="c1462-115">Describe cómo llamar a un ejemplo de WCF con un moniker de WCF que especifica un extremo de Mex.</span><span class="sxs-lookup"><span data-stu-id="c1462-115">Describes how to call a WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
 [<span data-ttu-id="c1462-116">Procedimiento para especificar las credenciales de seguridad de los canales</span><span class="sxs-lookup"><span data-stu-id="c1462-116">How to: Specify Channel Security Credentials</span></span>](how-to-specify-channel-security-credentials.md)  
 <span data-ttu-id="c1462-117">El moniker de servicio de WCF admite la `IChannelCredentials` interfaz que permite una variedad de métodos alternativos para especificar las credenciales del canal.</span><span class="sxs-lookup"><span data-stu-id="c1462-117">The WCF service moniker supports the `IChannelCredentials` interface that allows a range of alternate methods for specifying channel credentials.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c1462-118">Referencia</span><span class="sxs-lookup"><span data-stu-id="c1462-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="c1462-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1462-119">See also</span></span>

- [<span data-ttu-id="c1462-120">Integración con aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="c1462-120">Integrating with COM+ Applications</span></span>](integrating-with-com-plus-applications.md)
