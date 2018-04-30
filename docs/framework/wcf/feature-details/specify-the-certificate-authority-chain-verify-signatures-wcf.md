---
title: 'Cómo: Especificar la cadena de certificados de la entidad de certificación utilizada para comprobar las firmas (WCF)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 29637ea7f0a1e533a6735ebfa6f428fe20039e48
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a><span data-ttu-id="1d119-102">Cómo: Especificar la cadena de certificados de la entidad de certificación utilizada para comprobar las firmas (WCF)</span><span class="sxs-lookup"><span data-stu-id="1d119-102">How to: Specify the Certificate Authority Certificate Chain Used to Verify Signatures (WCF)</span></span>
<span data-ttu-id="1d119-103">Cuando [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] recibe un mensaje SOAP firmado usando un certificado X.509, de forma predeterminada comprueba que una entidad de certificación de confianza haya emitido el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="1d119-103">When [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] receives a SOAP message signed using an X.509 certificate, by default it verifies that the X.509 certificate was issued by a trusted certification authority.</span></span> <span data-ttu-id="1d119-104">Esto se hace consultando un almacén de certificados y determinando si el certificado para esa entidad de certificación se ha designado como de confianza.</span><span class="sxs-lookup"><span data-stu-id="1d119-104">This is done by looking in a certificate store and determining if the certificate for that certification authority has been designated as trusted.</span></span> <span data-ttu-id="1d119-105">Para que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] realice esta determinación, la cadena de certificados de la entidad de certificación debe estar instalada en el almacén de certificados correcto.</span><span class="sxs-lookup"><span data-stu-id="1d119-105">In order for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to make this determination, the certification authority certificate chain must be installed in the correct certificate store.</span></span>  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a><span data-ttu-id="1d119-106">Para instalar una cadena de certificados de la entidad de certificación</span><span class="sxs-lookup"><span data-stu-id="1d119-106">To install a certification authority certificate chain</span></span>  
  
-   <span data-ttu-id="1d119-107">Para cada entidad de certificación en cuyos certificados X.509 emitidos piense confiar un destinatario del mensaje SOAP, instale la cadena de certificados de la entidad de certificación en el almacén de certificados del que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] recupera los certificados X.509 de acuerdo con la configuración.</span><span class="sxs-lookup"><span data-stu-id="1d119-107">For each certification authority that a SOAP message recipient intends to trust X.509 certificates issued from, install the certification authority certificate chain into the certificate store that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is configured to retrieve X.509 certificates from.</span></span>  
  
     <span data-ttu-id="1d119-108">Por ejemplo, si un destinatario del mensaje SOAP piensa confiar en los certificados X.509 emitidos por Microsoft, la cadena de certificados de la entidad de certificación para Microsoft se debe instalar en el almacén de certificados en el que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] busca los certificados X.509 de acuerdo con la configuración.</span><span class="sxs-lookup"><span data-stu-id="1d119-108">For instance, if a SOAP message recipient intends to trust X.509 certificates issued by Microsoft, the certification authority certificate chain for Microsoft must be installed in the certificate store that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is set up to look for X.509 certificates from.</span></span> <span data-ttu-id="1d119-109">El almacén de certificados en el que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] busca los certificados X.509 se puede especificar en código o configuración.</span><span class="sxs-lookup"><span data-stu-id="1d119-109">The certificate store in which [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] looks for X.509 certificates can be specified in code or configuration.</span></span> <span data-ttu-id="1d119-110">Por ejemplo, esto puede especificarse en el código mediante el <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> método o en la configuración de varias maneras, incluido el [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .</span><span class="sxs-lookup"><span data-stu-id="1d119-110">For example, this can be specified in code using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method or in configuration a few ways, including the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .</span></span>  
  
     <span data-ttu-id="1d119-111">Dado que Windows distribuye con un conjunto de cadenas de certificados predeterminadas para entidades de certificación de confianza, quizás no sea necesario instalar la cadena de certificados para todas las entidades de certificación.</span><span class="sxs-lookup"><span data-stu-id="1d119-111">Because Windows ships with a set of default certificate chains for trusted certificate authorities, it may not be necessary to install the certificate chain for all certificate authorities.</span></span>  
  
    1.  <span data-ttu-id="1d119-112">Exporte la cadena de certificados de la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="1d119-112">Export the certification authority certificate chain.</span></span>  
  
         <span data-ttu-id="1d119-113">Cómo hacerlo exactamente depende de la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="1d119-113">Exactly how this is done depends on the certification authority.</span></span> <span data-ttu-id="1d119-114">Si la entidad de certificación está ejecutando servicios de Certificate Server de Microsoft, seleccione **descargar un certificado de CA, cadena de certificados o CRL**y, a continuación, elija **Descargar certificado de CA**.</span><span class="sxs-lookup"><span data-stu-id="1d119-114">If the certification authority is running Microsoft Certificate Services, select **Download a CA certificate, certificate chain, or CRL**, and then choose **Download CA certificate**.</span></span>  
  
    2.  <span data-ttu-id="1d119-115">Importe la cadena de certificados de la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="1d119-115">Import the certification authority certificate chain.</span></span>  
  
         <span data-ttu-id="1d119-116">En la Microsoft Management Console (MMC), abra el complemento Certificados.</span><span class="sxs-lookup"><span data-stu-id="1d119-116">In the Microsoft Management Console (MMC), open the Certificates snap-in.</span></span> <span data-ttu-id="1d119-117">Para el certificado de almacén que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] está configurado para recuperar los certificados X.509 en, seleccione la **raíz de confianza** **entidades emisoras de certificados**carpeta.</span><span class="sxs-lookup"><span data-stu-id="1d119-117">For the certificate store that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is configured to retrieve X.509 certificates from, select the **Trusted Root** **Certification Authorities**folder.</span></span> <span data-ttu-id="1d119-118">En el **entidades de certificación raíz de confianza** carpeta, haga clic en el **certificados**carpeta, seleccione **todas las tareas**y, a continuación, haga clic en **importación** .</span><span class="sxs-lookup"><span data-stu-id="1d119-118">Under the **Trusted Root Certification Authorities** folder, right-click the **Certificates**folder, point to **All Tasks**, and then click **Import**.</span></span> <span data-ttu-id="1d119-119">Proporcione el archivo exportado en el paso a.</span><span class="sxs-lookup"><span data-stu-id="1d119-119">Provide the file exported in step a.</span></span>  
  
         <span data-ttu-id="1d119-120">Para obtener más información acerca de cómo utilizar el complemento de certificados con MMC, consulte [Cómo: ver certificados con el complemento de MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="1d119-120">For more information about using the Certificates snap-in with MMC, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d119-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d119-121">See Also</span></span>  
 [<span data-ttu-id="1d119-122">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="1d119-122">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
