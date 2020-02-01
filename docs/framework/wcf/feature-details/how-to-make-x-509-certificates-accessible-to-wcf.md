---
title: 'Cómo: Hacer los certificados X.509 accesibles para WCF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- X.509 certificates [WCF]
- certificates [WCF], making X.509 certificates accessible to WCF
- X.509 certificates [WCF], making accessible to WCF
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
ms.openlocfilehash: 71dbf395f43c8028a703a342c032f2b8d022a61c
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921295"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="01dbb-102">Cómo: Hacer los certificados X.509 accesibles para WCF</span><span class="sxs-lookup"><span data-stu-id="01dbb-102">How to: Make X.509 Certificates Accessible to WCF</span></span>
<span data-ttu-id="01dbb-103">Para que un certificado X. 509 sea accesible para Windows Communication Foundation (WCF), el código de aplicación debe especificar el nombre y la ubicación del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="01dbb-103">To make an X.509 certificate accessible to Windows Communication Foundation (WCF), application code must specify the certificate store name and location.</span></span> <span data-ttu-id="01dbb-104">En ciertas circunstancias, la identidad del proceso debe tener el acceso al archivo que contiene la clave privada asociada al certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="01dbb-104">In certain circumstances, the process identity must have access to the file that contains the private key associated with the X.509 certificate.</span></span> <span data-ttu-id="01dbb-105">Para obtener la clave privada asociada a un certificado X. 509 en un almacén de certificados, WCF debe tener permiso para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="01dbb-105">To obtain the private key associated with an X.509 certificate in a certificate store, WCF must have permission to do so.</span></span> <span data-ttu-id="01dbb-106">De forma predeterminada, solo el propietario y la cuenta del sistema pueden tener acceso a la clave privada de un certificado.</span><span class="sxs-lookup"><span data-stu-id="01dbb-106">By default, only the owner and the System account can access the private key of a certificate.</span></span>  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="01dbb-107">Para hacer los certificados X.509 accesibles para WCF</span><span class="sxs-lookup"><span data-stu-id="01dbb-107">To make X.509 certificates accessible to WCF</span></span>  
  
1. <span data-ttu-id="01dbb-108">Proporcione a la cuenta con la que WCF está ejecutando acceso de lectura al archivo que contiene la clave privada asociada al certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="01dbb-108">Give the account under which WCF is running read access to the file that contains the private key associated with the X.509 certificate.</span></span>  
  
    1. <span data-ttu-id="01dbb-109">Determine si WCF requiere acceso de lectura a la clave privada para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="01dbb-109">Determine whether WCF requires read access to the private key for the X.509 certificate.</span></span>  
  
         <span data-ttu-id="01dbb-110">La tabla siguiente detalla si una clave privada debe estar disponible al utilizar un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="01dbb-110">The following table details whether a private key must be available when using an X.509 certificate.</span></span>  
  
        |<span data-ttu-id="01dbb-111">Uso del certificado X.509</span><span class="sxs-lookup"><span data-stu-id="01dbb-111">X.509 certificate use</span></span>|<span data-ttu-id="01dbb-112">Clave privada</span><span class="sxs-lookup"><span data-stu-id="01dbb-112">Private key</span></span>|  
        |---------------------------|-----------------|  
        |<span data-ttu-id="01dbb-113">Firmar digitalmente un mensaje SOAP saliente.</span><span class="sxs-lookup"><span data-stu-id="01dbb-113">Digitally signing an outbound SOAP message.</span></span>|<span data-ttu-id="01dbb-114">Sí</span><span class="sxs-lookup"><span data-stu-id="01dbb-114">Yes</span></span>|  
        |<span data-ttu-id="01dbb-115">Comprobar la firma de un mensaje SOAP entrante.</span><span class="sxs-lookup"><span data-stu-id="01dbb-115">Verifying the signature of an inbound SOAP message.</span></span>|<span data-ttu-id="01dbb-116">No</span><span class="sxs-lookup"><span data-stu-id="01dbb-116">No</span></span>|  
        |<span data-ttu-id="01dbb-117">Cifrar un mensaje SOAP saliente.</span><span class="sxs-lookup"><span data-stu-id="01dbb-117">Encrypting an outbound SOAP message.</span></span>|<span data-ttu-id="01dbb-118">No</span><span class="sxs-lookup"><span data-stu-id="01dbb-118">No</span></span>|  
        |<span data-ttu-id="01dbb-119">Descifrar un mensaje SOAP entrante.</span><span class="sxs-lookup"><span data-stu-id="01dbb-119">Decrypting an inbound SOAP message.</span></span>|<span data-ttu-id="01dbb-120">Sí</span><span class="sxs-lookup"><span data-stu-id="01dbb-120">Yes</span></span>|  
  
    2. <span data-ttu-id="01dbb-121">Determine la ubicación del almacén de certificados y diga dónde está almacenado el certificado.</span><span class="sxs-lookup"><span data-stu-id="01dbb-121">Determine the certificate store location and name in which the certificate is stored.</span></span>  
  
         <span data-ttu-id="01dbb-122">El almacén de certificados en el que el certificado está almacenado se especifica en código de aplicación o en configuración.</span><span class="sxs-lookup"><span data-stu-id="01dbb-122">The certificate store in which the certificate is stored is specified either in application code or in configuration.</span></span> <span data-ttu-id="01dbb-123">Por ejemplo, el ejemplo siguiente especifica que el certificado se encuentra en el almacén de certificados `CurrentUser` denominado `My`.</span><span class="sxs-lookup"><span data-stu-id="01dbb-123">For example, the following example specifies that the certificate is located in the `CurrentUser` certificate store named `My`.</span></span>  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3. <span data-ttu-id="01dbb-124">Determine dónde se encuentra la clave privada para el certificado en el equipo mediante la herramienta [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) .</span><span class="sxs-lookup"><span data-stu-id="01dbb-124">Determine where the private key for the certificate is located on the computer by using the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool.</span></span>  
  
         <span data-ttu-id="01dbb-125">La herramienta [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) requiere el nombre del almacén de certificados, la ubicación del almacén de certificados y algo que identifica de forma única el certificado.</span><span class="sxs-lookup"><span data-stu-id="01dbb-125">The [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool requires the certificate store name, certificate store location, and something that uniquely identifies the certificate.</span></span> <span data-ttu-id="01dbb-126">La herramienta acepta el nombre de sujeto del certificado o su huella digital como identificador único.</span><span class="sxs-lookup"><span data-stu-id="01dbb-126">The tool accepts either the certificate's subject name or its thumbprint as a unique identifier.</span></span> <span data-ttu-id="01dbb-127">Para obtener más información sobre cómo determinar la huella digital de un certificado, consulte [Cómo: recuperar la huella digital de un certificado](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="01dbb-127">For more information about how to determine the thumbprint for a certificate, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
         <span data-ttu-id="01dbb-128">En el ejemplo de código siguiente se usa la herramienta [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) para determinar la ubicación de la clave privada de un certificado en el almacén de `My` en `CurrentUser` con una huella digital de `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span><span class="sxs-lookup"><span data-stu-id="01dbb-128">The following code example uses the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool to determine the location of the private key for a certificate in the `My` store in `CurrentUser` with a thumbprint of `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span></span>  
  
        ```console
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4. <span data-ttu-id="01dbb-129">Determine la cuenta con la que se ejecuta WCF.</span><span class="sxs-lookup"><span data-stu-id="01dbb-129">Determine the account that WCF is running under.</span></span>  
  
         <span data-ttu-id="01dbb-130">En la tabla siguiente se detalla la cuenta con la que se ejecuta WCF para un escenario determinado.</span><span class="sxs-lookup"><span data-stu-id="01dbb-130">The following table details the account under which WCF is running for a given scenario.</span></span>  
  
        |<span data-ttu-id="01dbb-131">Escenario</span><span class="sxs-lookup"><span data-stu-id="01dbb-131">Scenario</span></span>|<span data-ttu-id="01dbb-132">Identidad de proceso</span><span class="sxs-lookup"><span data-stu-id="01dbb-132">Process identity</span></span>|  
        |--------------|----------------------|  
        |<span data-ttu-id="01dbb-133">Cliente (consola o aplicación WinForms).</span><span class="sxs-lookup"><span data-stu-id="01dbb-133">Client (console or WinForms application).</span></span>|<span data-ttu-id="01dbb-134">Usuario actualmente registrado.</span><span class="sxs-lookup"><span data-stu-id="01dbb-134">Currently logged in user.</span></span>|  
        |<span data-ttu-id="01dbb-135">Servicio que tiene host propio.</span><span class="sxs-lookup"><span data-stu-id="01dbb-135">Service that is self-hosted.</span></span>|<span data-ttu-id="01dbb-136">Usuario actualmente registrado.</span><span class="sxs-lookup"><span data-stu-id="01dbb-136">Currently logged in user.</span></span>|  
        |<span data-ttu-id="01dbb-137">Servicio hospedado en IIS 6,0 (Windows Server 2003) o IIS 7,0 (Windows Vista).</span><span class="sxs-lookup"><span data-stu-id="01dbb-137">Service that is hosted in IIS 6.0 (Windows Server 2003) or IIS 7.0 (Windows Vista).</span></span>|<span data-ttu-id="01dbb-138">NETWORK SERVICE</span><span class="sxs-lookup"><span data-stu-id="01dbb-138">NETWORK SERVICE</span></span>|  
        |<span data-ttu-id="01dbb-139">Servicio que se hospeda en IIS 5. X (Windows XP).</span><span class="sxs-lookup"><span data-stu-id="01dbb-139">Service that is hosted in IIS 5.X (Windows XP).</span></span>|<span data-ttu-id="01dbb-140">Controlado por el elemento `<processModel>` en el archivo Machine.config.</span><span class="sxs-lookup"><span data-stu-id="01dbb-140">Controlled by the `<processModel>` element in the Machine.config file.</span></span> <span data-ttu-id="01dbb-141">La cuenta predeterminada es ASPNET.</span><span class="sxs-lookup"><span data-stu-id="01dbb-141">The default account is ASPNET.</span></span>|  
  
    5. <span data-ttu-id="01dbb-142">Conceda acceso de lectura al archivo que contiene la clave privada a la cuenta con la que se está ejecutando WCF mediante una herramienta como icacls. exe.</span><span class="sxs-lookup"><span data-stu-id="01dbb-142">Grant read access to the file that contains the private key to the account that WCF is running under, using a tool such as icacls.exe.</span></span>  
  
         <span data-ttu-id="01dbb-143">En el ejemplo de código siguiente se edita la lista de control de acceso discrecional (DACL) del archivo especificado para conceder a la cuenta de servicio de red acceso de lectura (: R) al archivo.</span><span class="sxs-lookup"><span data-stu-id="01dbb-143">The following code example edits the discretionary access control list (DACL) for the specified file to grant the NETWORK SERVICE account read (:R) access to the file.</span></span>  
  
        ```console 
        icacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /grant "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="01dbb-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="01dbb-144">See also</span></span>

- [<span data-ttu-id="01dbb-145">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="01dbb-145">FindPrivateKey</span></span>](../../../../docs/framework/wcf/samples/findprivatekey.md)
- [<span data-ttu-id="01dbb-146">Recuperación de la huella digital de un certificado</span><span class="sxs-lookup"><span data-stu-id="01dbb-146">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
- [<span data-ttu-id="01dbb-147">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="01dbb-147">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
