---
title: Cómo obtener un certificado (WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: 664eb62997123ea248b0b69700b86bf794646d4b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43465867"
---
# <a name="how-to-obtain-a-certificate-wcf"></a><span data-ttu-id="cfc03-102">Cómo obtener un certificado (WCF)</span><span class="sxs-lookup"><span data-stu-id="cfc03-102">How to: Obtain a Certificate (WCF)</span></span>
<span data-ttu-id="cfc03-103">Para usar cualquiera de Windows Communication Foundation (WCF) características de los usan certificados X.509, ha de obtener primero los certificados.</span><span class="sxs-lookup"><span data-stu-id="cfc03-103">To use any of the Windows Communication Foundation (WCF) features of that use X.509 certificates, you just first obtain certificates.</span></span>  
  
### <a name="to-obtain-an-x509-certificate"></a><span data-ttu-id="cfc03-104">Para obtener un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="cfc03-104">To obtain an X.509 certificate</span></span>  
  
1.  <span data-ttu-id="cfc03-105">Elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="cfc03-105">Choose one of the following:</span></span>  
  
    -   <span data-ttu-id="cfc03-106">Adquiera un certificado de una entidad emisora de certificados, como VeriSign, Inc.</span><span class="sxs-lookup"><span data-stu-id="cfc03-106">Purchase a certificate from a certification authority, such as VeriSign, Inc.</span></span>  
  
    -   <span data-ttu-id="cfc03-107">Configure su propio servicio de certificados y haga que una entidad de certificación los firme.</span><span class="sxs-lookup"><span data-stu-id="cfc03-107">Set up your own certificate service and have a certification authority sign the certificates.</span></span> [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]<span data-ttu-id="cfc03-108">, Windows 2000 Server, Windows 2000 Server Datacenter y Windows 2000 Datacenter Server incluyen servicios de servidor de certificados que admiten la infraestructura de clave pública (PKI).</span><span class="sxs-lookup"><span data-stu-id="cfc03-108">, Windows 2000 Server, Windows 2000 Server Datacenter, and Windows 2000 Datacenter Server all include certificate services that support public key infrastructure (PKI).</span></span> <span data-ttu-id="cfc03-109">En Windows Server 2008, use la [Active Directory Certificate Services](https://go.microsoft.com/fwlink/?LinkID=153483) rol para administrar una entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="cfc03-109">In Windows Server 2008, use the [Active Directory Certificate Services](https://go.microsoft.com/fwlink/?LinkID=153483) role to manage a certification authority.</span></span>  
  
    -   <span data-ttu-id="cfc03-110">Configure su propio servicio de certificados y asegúrese de que los certificados no estén firmados.</span><span class="sxs-lookup"><span data-stu-id="cfc03-110">Set up your own certificate service and do not have the certificates signed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cfc03-111">Elija el método que elija, el destinatario de la solicitud SOAP que contiene el certificado X.509 debe confiar en el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="cfc03-111">Whichever approach you take, the recipient of the SOAP request that contains the X.509 certificate must trust the X.509 certificate.</span></span> <span data-ttu-id="cfc03-112">Esto significa que el certificado X.509 o un emisor en la cadena de certificados está en el almacén de certificados de gente de confianza y que el certificado X.509 no está en el almacén de certificados que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="cfc03-112">This means that the X.509 certificate or an issuer in the certificate chain is in the Trusted People certificate store and that the X.509 certificate is not in the Untrusted Certificates store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfc03-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfc03-113">See Also</span></span>  
 [<span data-ttu-id="cfc03-114">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="cfc03-114">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="cfc03-115">Creación de certificados temporales que puedan utilizarse durante las operaciones de desarrollo</span><span class="sxs-lookup"><span data-stu-id="cfc03-115">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
