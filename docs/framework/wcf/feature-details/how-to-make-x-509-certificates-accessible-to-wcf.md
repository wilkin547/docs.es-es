---
title: 'Cómo: Hacer los certificados X.509 accesibles para WCF'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- X.509 certificates [WCF]
- certificates [WCF], making X.509 certificates accessible to WCF
- X.509 certificates [WCF], making accessible to WCF
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 77ee21074b6f1bb5a2f5bd4ee653100d3534075d
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="649ed-102">Cómo: Hacer los certificados X.509 accesibles para WCF</span><span class="sxs-lookup"><span data-stu-id="649ed-102">How to: Make X.509 Certificates Accessible to WCF</span></span>
<span data-ttu-id="649ed-103">Para hacer un certificado X.509 accesible a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], el código de aplicación debe especificar el nombre del almacén de certificados y ubicación.</span><span class="sxs-lookup"><span data-stu-id="649ed-103">To make an X.509 certificate accessible to [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], application code must specify the certificate store name and location.</span></span> <span data-ttu-id="649ed-104">En ciertas circunstancias, la identidad del proceso debe tener el acceso al archivo que contiene la clave privada asociada al certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="649ed-104">In certain circumstances, the process identity must have access to the file that contains the private key associated with the X.509 certificate.</span></span> <span data-ttu-id="649ed-105">Para obtener la clave privada asociada a un certificado X.509 en un almacén de certificados, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] debe tener el permiso para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="649ed-105">To obtain the private key associated with an X.509 certificate in a certificate store, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] must have permission to do so.</span></span> <span data-ttu-id="649ed-106">De forma predeterminada, solo el propietario y la cuenta del sistema pueden tener acceso a la clave privada de un certificado.</span><span class="sxs-lookup"><span data-stu-id="649ed-106">By default, only the owner and the System account can access the private key of a certificate.</span></span>  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="649ed-107">Para hacer los certificados X.509 accesibles para WCF</span><span class="sxs-lookup"><span data-stu-id="649ed-107">To make X.509 certificates accessible to WCF</span></span>  
  
1.  <span data-ttu-id="649ed-108">Proporcione la cuenta donde [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] está ejecutando el acceso de lectura al archivo que contiene la clave privada asociada al certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="649ed-108">Give the account under which [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is running read access to the file that contains the private key associated with the X.509 certificate.</span></span>  
  
    1.  <span data-ttu-id="649ed-109">Determine si [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requiere el acceso de lectura a la clave privada para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="649ed-109">Determine whether [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires read access to the private key for the X.509 certificate.</span></span>  
  
         <span data-ttu-id="649ed-110">La tabla siguiente detalla si una clave privada debe estar disponible al utilizar un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="649ed-110">The following table details whether a private key must be available when using an X.509 certificate.</span></span>  
  
        |<span data-ttu-id="649ed-111">Uso del certificado X.509</span><span class="sxs-lookup"><span data-stu-id="649ed-111">X.509 certificate use</span></span>|<span data-ttu-id="649ed-112">Clave privada</span><span class="sxs-lookup"><span data-stu-id="649ed-112">Private key</span></span>|  
        |---------------------------|-----------------|  
        |<span data-ttu-id="649ed-113">Firmar digitalmente un mensaje SOAP saliente.</span><span class="sxs-lookup"><span data-stu-id="649ed-113">Digitally signing an outbound SOAP message.</span></span>|<span data-ttu-id="649ed-114">Sí</span><span class="sxs-lookup"><span data-stu-id="649ed-114">Yes</span></span>|  
        |<span data-ttu-id="649ed-115">Comprobar la firma de un mensaje SOAP entrante.</span><span class="sxs-lookup"><span data-stu-id="649ed-115">Verifying the signature of an inbound SOAP message.</span></span>|<span data-ttu-id="649ed-116">No</span><span class="sxs-lookup"><span data-stu-id="649ed-116">No</span></span>|  
        |<span data-ttu-id="649ed-117">Cifrar un mensaje SOAP saliente.</span><span class="sxs-lookup"><span data-stu-id="649ed-117">Encrypting an outbound SOAP message.</span></span>|<span data-ttu-id="649ed-118">No</span><span class="sxs-lookup"><span data-stu-id="649ed-118">No</span></span>|  
        |<span data-ttu-id="649ed-119">Descifrar un mensaje SOAP entrante.</span><span class="sxs-lookup"><span data-stu-id="649ed-119">Decrypting an inbound SOAP message.</span></span>|<span data-ttu-id="649ed-120">Sí</span><span class="sxs-lookup"><span data-stu-id="649ed-120">Yes</span></span>|  
  
    2.  <span data-ttu-id="649ed-121">Determine la ubicación del almacén de certificados y diga dónde está almacenado el certificado.</span><span class="sxs-lookup"><span data-stu-id="649ed-121">Determine the certificate store location and name in which the certificate is stored.</span></span>  
  
         <span data-ttu-id="649ed-122">El almacén de certificados en el que el certificado está almacenado se especifica en código de aplicación o en configuración.</span><span class="sxs-lookup"><span data-stu-id="649ed-122">The certificate store in which the certificate is stored is specified either in application code or in configuration.</span></span> <span data-ttu-id="649ed-123">Por ejemplo, el ejemplo siguiente especifica que el certificado se encuentra en el almacén de certificados `CurrentUser` denominado `My`.</span><span class="sxs-lookup"><span data-stu-id="649ed-123">For example, the following example specifies that the certificate is located in the `CurrentUser` certificate store named `My`.</span></span>  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3.  <span data-ttu-id="649ed-124">Determinar dónde se encuentra la clave privada del certificado en el equipo mediante el uso de la [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) herramienta.</span><span class="sxs-lookup"><span data-stu-id="649ed-124">Determine where the private key for the certificate is located on the computer by using the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool.</span></span>  
  
         <span data-ttu-id="649ed-125">El [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) herramienta requiere que el nombre del almacén de certificados, la ubicación del almacén de certificados y algo que identifica de forma única el certificado.</span><span class="sxs-lookup"><span data-stu-id="649ed-125">The [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool requires the certificate store name, certificate store location, and something that uniquely identifies the certificate.</span></span> <span data-ttu-id="649ed-126">La herramienta acepta el nombre de sujeto del certificado o su huella digital como identificador único.</span><span class="sxs-lookup"><span data-stu-id="649ed-126">The tool accepts either the certificate's subject name or its thumbprint as a unique identifier.</span></span> <span data-ttu-id="649ed-127">Para obtener más información acerca de cómo determinar la huella digital de un certificado, consulte [Cómo: recuperar la huella digital de un certificado](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="649ed-127">For more information about how to determine the thumbprint for a certificate, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
         <span data-ttu-id="649ed-128">El siguiente ejemplo de código utiliza el [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) herramienta para determinar la ubicación de la clave privada de un certificado en el `My` almacenar en `CurrentUser` con una huella digital de `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span><span class="sxs-lookup"><span data-stu-id="649ed-128">The following code example uses the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool to determine the location of the private key for a certificate in the `My` store in `CurrentUser` with a thumbprint of `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span></span>  
  
        ```  
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4.  <span data-ttu-id="649ed-129">Determine la cuenta donde [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="649ed-129">Determine the account that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is running under.</span></span>  
  
         <span data-ttu-id="649ed-130">La tabla siguiente detalla la cuenta donde [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se está ejecutando para un escenario determinado.</span><span class="sxs-lookup"><span data-stu-id="649ed-130">The following table details the account under which [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is running for a given scenario.</span></span>  
  
        |<span data-ttu-id="649ed-131">Escenario</span><span class="sxs-lookup"><span data-stu-id="649ed-131">Scenario</span></span>|<span data-ttu-id="649ed-132">Identidad de proceso</span><span class="sxs-lookup"><span data-stu-id="649ed-132">Process identity</span></span>|  
        |--------------|----------------------|  
        |<span data-ttu-id="649ed-133">Cliente (consola o aplicación WinForms).</span><span class="sxs-lookup"><span data-stu-id="649ed-133">Client (console or WinForms application).</span></span>|<span data-ttu-id="649ed-134">Usuario actualmente registrado.</span><span class="sxs-lookup"><span data-stu-id="649ed-134">Currently logged in user.</span></span>|  
        |<span data-ttu-id="649ed-135">Servicio que tiene host propio.</span><span class="sxs-lookup"><span data-stu-id="649ed-135">Service that is self-hosted.</span></span>|<span data-ttu-id="649ed-136">Usuario actualmente registrado.</span><span class="sxs-lookup"><span data-stu-id="649ed-136">Currently logged in user.</span></span>|  
        |<span data-ttu-id="649ed-137">Servicio que se hospeda en IIS 6.0 ([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) ó IIS 7.0 ([!INCLUDE[wv](../../../../includes/wv-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="649ed-137">Service that is hosted in IIS 6.0 ([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) or IIS 7.0 ([!INCLUDE[wv](../../../../includes/wv-md.md)]).</span></span>|<span data-ttu-id="649ed-138">NETWORK SERVICE</span><span class="sxs-lookup"><span data-stu-id="649ed-138">NETWORK SERVICE</span></span>|  
        |<span data-ttu-id="649ed-139">Servicio que se hospeda en IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="649ed-139">Service that is hosted in IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]).</span></span>|<span data-ttu-id="649ed-140">Controlado por el elemento `<processModel>` en el archivo Machine.config.</span><span class="sxs-lookup"><span data-stu-id="649ed-140">Controlled by the `<processModel>` element in the Machine.config file.</span></span> <span data-ttu-id="649ed-141">La cuenta predeterminada es ASPNET.</span><span class="sxs-lookup"><span data-stu-id="649ed-141">The default account is ASPNET.</span></span>|  
  
    5.  <span data-ttu-id="649ed-142">Conceda el acceso de lectura al archivo que contiene la clave privada a la cuenta donde [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se está ejecutando, utilizando una herramienta como cacls.exe.</span><span class="sxs-lookup"><span data-stu-id="649ed-142">Grant read access to the file that contains the private key to the account that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is running under, using a tool such as cacls.exe.</span></span>  
  
         <span data-ttu-id="649ed-143">El ejemplo de código siguiente edita (/E) la lista de control de acceso (ACL) para que el archivo especificado conceda (/G) el acceso de lectura (: R) de cuenta NETWORK SERVICE al archivo.</span><span class="sxs-lookup"><span data-stu-id="649ed-143">The following code example edits (/E) the access control list (ACL) for the specified file to grant (/G) the NETWORK SERVICE account read (:R) access to the file.</span></span>  
  
        ```  
        cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="649ed-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="649ed-144">See Also</span></span>  
 [<span data-ttu-id="649ed-145">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="649ed-145">FindPrivateKey</span></span>](../../../../docs/framework/wcf/samples/findprivatekey.md)  
 [<span data-ttu-id="649ed-146">Recuperación de la huella digital de un certificado</span><span class="sxs-lookup"><span data-stu-id="649ed-146">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)  
 [<span data-ttu-id="649ed-147">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="649ed-147">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
