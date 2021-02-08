---
description: 'Más información acerca de cómo: obtener un certificado (WCF)'
title: Cómo obtener un certificado (WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: 2ca40c9646bbdeb6c29a94966fd24ec00d9b5306
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793706"
---
# <a name="how-to-obtain-a-certificate-wcf"></a><span data-ttu-id="8ab27-103">Cómo obtener un certificado (WCF)</span><span class="sxs-lookup"><span data-stu-id="8ab27-103">How to: Obtain a Certificate (WCF)</span></span>

<span data-ttu-id="8ab27-104">Para usar cualquiera de las características de Windows Communication Foundation (WCF) de que usan certificados X. 509, primero tiene que obtener certificados.</span><span class="sxs-lookup"><span data-stu-id="8ab27-104">To use any of the Windows Communication Foundation (WCF) features of that use X.509 certificates, you just first obtain certificates.</span></span>  
  
### <a name="to-obtain-an-x509-certificate"></a><span data-ttu-id="8ab27-105">Para obtener un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="8ab27-105">To obtain an X.509 certificate</span></span>  
  
1. <span data-ttu-id="8ab27-106">Elija alguna de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="8ab27-106">Choose one of the following:</span></span>  
  
    - <span data-ttu-id="8ab27-107">Adquiera un certificado de una entidad emisora de certificados, como VeriSign, Inc.</span><span class="sxs-lookup"><span data-stu-id="8ab27-107">Purchase a certificate from a certification authority, such as VeriSign, Inc.</span></span>  
  
    - <span data-ttu-id="8ab27-108">Configure su propio servicio de certificados y haga que una entidad de certificación los firme.</span><span class="sxs-lookup"><span data-stu-id="8ab27-108">Set up your own certificate service and have a certification authority sign the certificates.</span></span> <span data-ttu-id="8ab27-109">Windows Server 2003, Windows 2000 Server, Windows 2000 Server Datacenter y Windows 2000 Datacenter Server incluyen servicios de servidor de certificados que admiten la infraestructura de clave pública (PKI).</span><span class="sxs-lookup"><span data-stu-id="8ab27-109">Windows Server 2003, Windows 2000 Server, Windows 2000 Server Datacenter, and Windows 2000 Datacenter Server all include certificate services that support public key infrastructure (PKI).</span></span> <span data-ttu-id="8ab27-110">En Windows Server 2008, use el rol [servicios de certificados de Active Directory](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731564(v=ws.10)) para administrar una entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="8ab27-110">In Windows Server 2008, use the [Active Directory Certificate Services](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731564(v=ws.10)) role to manage a certification authority.</span></span>  
  
    - <span data-ttu-id="8ab27-111">Configure su propio servicio de certificados y asegúrese de que los certificados no estén firmados.</span><span class="sxs-lookup"><span data-stu-id="8ab27-111">Set up your own certificate service and do not have the certificates signed.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8ab27-112">Elija el método que elija, el destinatario de la solicitud SOAP que contiene el certificado X.509 debe confiar en el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="8ab27-112">Whichever approach you take, the recipient of the SOAP request that contains the X.509 certificate must trust the X.509 certificate.</span></span> <span data-ttu-id="8ab27-113">Esto significa que el certificado X.509 o un emisor en la cadena de certificados está en el almacén de certificados de gente de confianza y que el certificado X.509 no está en el almacén de certificados que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="8ab27-113">This means that the X.509 certificate or an issuer in the certificate chain is in the Trusted People certificate store and that the X.509 certificate is not in the Untrusted Certificates store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ab27-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ab27-114">See also</span></span>

- [<span data-ttu-id="8ab27-115">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="8ab27-115">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="8ab27-116">Procedimiento para crear certificados temporales que puedan usarse durante las operaciones de desarrollo</span><span class="sxs-lookup"><span data-stu-id="8ab27-116">How to: Create Temporary Certificates for Use During Development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
