---
description: 'Más información sobre: Cómo: hacer referencia a los certificados X. 509 de forma coherente'
title: Procedimiento para hacer referencia a los certificados X.509 de forma coherente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
ms.openlocfilehash: cdf5535373490e8cb78e28a8fc0cf881df40e041
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734807"
---
# <a name="how-to-consistently-reference-x509-certificates"></a><span data-ttu-id="e4960-103">Procedimiento para hacer referencia a los certificados X.509 de forma coherente</span><span class="sxs-lookup"><span data-stu-id="e4960-103">How to: Consistently Reference X.509 Certificates</span></span>

<span data-ttu-id="e4960-104">Hay varias maneras de identificar un certificado: por el hash del certificado, por el emisor y número de serie y por el identificador clave del sujeto (SKI).</span><span class="sxs-lookup"><span data-stu-id="e4960-104">You can identify a certificate in several ways: by the hash of the certificate, by the issuer and serial number, or by the subject key identifier (SKI).</span></span> <span data-ttu-id="e4960-105">El SKI proporciona una identificación única para la clave pública del sujeto del certificado y se suele utilizar al trabajar con firmas digitales XML.</span><span class="sxs-lookup"><span data-stu-id="e4960-105">The SKI provides a unique identification for the certificate's subject public key and is often used when working with XML digital signing.</span></span> <span data-ttu-id="e4960-106">El valor de SKI suele ser parte del certificado X. 509 como una *extensión de certificado x. 509*.</span><span class="sxs-lookup"><span data-stu-id="e4960-106">The SKI value is usually part of the X.509 certificate as an *X.509 certificate extension*.</span></span> <span data-ttu-id="e4960-107">Windows Communication Foundation (WCF) tiene un *estilo de referencia* predeterminado que usa el emisor y el número de serie si la extensión de Ski falta en el certificado.</span><span class="sxs-lookup"><span data-stu-id="e4960-107">Windows Communication Foundation (WCF) has a default *referencing style* that uses the issuer and serial number if the SKI extension is missing from the certificate.</span></span> <span data-ttu-id="e4960-108">Si el certificado contiene la extensión SKI, el estilo de referencia predeterminado utiliza el SKI para señalar al certificado.</span><span class="sxs-lookup"><span data-stu-id="e4960-108">If the certificate contains the SKI extension, the default referencing style uses the SKI to point to the certificate.</span></span> <span data-ttu-id="e4960-109">Si se usa el desarrollo de una aplicación de forma intermedia, se pasa del uso de certificados que no usan la extensión de SKI a certificados que usan la extensión de SKI, el estilo de referencia que se usa en los mensajes generados por WCF también cambia.</span><span class="sxs-lookup"><span data-stu-id="e4960-109">If mid-way through development of an application, you switch from using certificates that do not use the SKI extension to certificates that use the SKI extension, the referencing style used in WCF-generated messages also changes.</span></span>  
  
 <span data-ttu-id="e4960-110">Si un estilo de referencia coherente se requiere independientemente de la presencia de extensión SKI, es posible configurar el estilo de referencia deseado como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e4960-110">If a consistent referencing style is required regardless of SKI extension presence, it is possible to configure the desired referencing style as shown in the following code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4960-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4960-111">Example</span></span>  

 <span data-ttu-id="e4960-112">El ejemplo siguiente crea un elemento de enlace de seguridad personalizado que utiliza un estilo de referencia coherente único, el nombre del emisor y número de serie.</span><span class="sxs-lookup"><span data-stu-id="e4960-112">The following example creates a custom security binding element that uses a single consistent referencing style, the issuer name and serial number.</span></span>  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e4960-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e4960-113">Compiling the Code</span></span>  

 <span data-ttu-id="e4960-114">Los espacios de nombres siguientes son necesarios para compilar el código:</span><span class="sxs-lookup"><span data-stu-id="e4960-114">The following namespaces are required to compile the code:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a><span data-ttu-id="e4960-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4960-115">See also</span></span>

- [<span data-ttu-id="e4960-116">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="e4960-116">Working with Certificates</span></span>](working-with-certificates.md)
