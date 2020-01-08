---
title: Cómo obtener un certificado (WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: 485741f98c4a120669eafe85d3a3810374f61378
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347149"
---
# <a name="how-to-obtain-a-certificate-wcf"></a><span data-ttu-id="dc0fd-102">Cómo obtener un certificado (WCF)</span><span class="sxs-lookup"><span data-stu-id="dc0fd-102">How to: Obtain a Certificate (WCF)</span></span>
<span data-ttu-id="dc0fd-103">Para usar cualquiera de las características de Windows Communication Foundation (WCF) de que usan certificados X. 509, primero tiene que obtener certificados.</span><span class="sxs-lookup"><span data-stu-id="dc0fd-103">To use any of the Windows Communication Foundation (WCF) features of that use X.509 certificates, you just first obtain certificates.</span></span>  
  
### <a name="to-obtain-an-x509-certificate"></a><span data-ttu-id="dc0fd-104">Para obtener un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="dc0fd-104">To obtain an X.509 certificate</span></span>  
  
1. <span data-ttu-id="dc0fd-105">Elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="dc0fd-105">Choose one of the following:</span></span>  
  
    - <span data-ttu-id="dc0fd-106">Adquiera un certificado de una entidad emisora de certificados, como VeriSign, Inc.</span><span class="sxs-lookup"><span data-stu-id="dc0fd-106">Purchase a certificate from a certification authority, such as VeriSign, Inc.</span></span>  
  
    - <span data-ttu-id="dc0fd-107">Configure su propio servicio de certificados y haga que una entidad de certificación los firme.</span><span class="sxs-lookup"><span data-stu-id="dc0fd-107">Set up your own certificate service and have a certification authority sign the certificates.</span></span> <span data-ttu-id="dc0fd-108">Windows Server 2003, Windows 2000 Server, Windows 2000 Server Datacenter y Windows 2000 Datacenter Server incluyen servicios de servidor de certificados que admiten la infraestructura de clave pública (PKI).</span><span class="sxs-lookup"><span data-stu-id="dc0fd-108">Windows Server 2003, Windows 2000 Server, Windows 2000 Server Datacenter, and Windows 2000 Datacenter Server all include certificate services that support public key infrastructure (PKI).</span></span> <span data-ttu-id="dc0fd-109">En Windows Server 2008, use el rol [servicios de certificados de Active Directory](https://go.microsoft.com/fwlink/?LinkID=153483) para administrar una entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="dc0fd-109">In Windows Server 2008, use the [Active Directory Certificate Services](https://go.microsoft.com/fwlink/?LinkID=153483) role to manage a certification authority.</span></span>  
  
    - <span data-ttu-id="dc0fd-110">Configure su propio servicio de certificados y asegúrese de que los certificados no estén firmados.</span><span class="sxs-lookup"><span data-stu-id="dc0fd-110">Set up your own certificate service and do not have the certificates signed.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="dc0fd-111">Elija el método que elija, el destinatario de la solicitud SOAP que contiene el certificado X.509 debe confiar en el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="dc0fd-111">Whichever approach you take, the recipient of the SOAP request that contains the X.509 certificate must trust the X.509 certificate.</span></span> <span data-ttu-id="dc0fd-112">Esto significa que el certificado X.509 o un emisor en la cadena de certificados está en el almacén de certificados de gente de confianza y que el certificado X.509 no está en el almacén de certificados que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="dc0fd-112">This means that the X.509 certificate or an issuer in the certificate chain is in the Trusted People certificate store and that the X.509 certificate is not in the Untrusted Certificates store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc0fd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc0fd-113">See also</span></span>

- [<span data-ttu-id="dc0fd-114">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="dc0fd-114">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="dc0fd-115">Creación de certificados temporales que puedan utilizarse durante las operaciones de desarrollo</span><span class="sxs-lookup"><span data-stu-id="dc0fd-115">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
