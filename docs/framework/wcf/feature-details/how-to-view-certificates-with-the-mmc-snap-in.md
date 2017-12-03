---
title: "Cómo: Ver certificados con el complemento de MMC"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5981e68ebe2870870fff5e92e87d7582ac2c42b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="a807e-102">Cómo: Ver certificados con el complemento de MMC</span><span class="sxs-lookup"><span data-stu-id="a807e-102">How to: View Certificates with the MMC Snap-in</span></span>
<span data-ttu-id="a807e-103">Un tipo común de credencial es el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="a807e-103">A common type of credential is the X.509 certificate.</span></span> <span data-ttu-id="a807e-104">Al crear servicios o clientes seguros, puede especificar que un certificado se utilice como la credencial del cliente o servicio utilizando métodos como el método <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>.</span><span class="sxs-lookup"><span data-stu-id="a807e-104">When creating secure services or clients, you can specify a certificate be used as the client or service credential by using methods such as the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method.</span></span> <span data-ttu-id="a807e-105">El método requiere varios parámetros, como el almacén donde se guarda el certificado y un valor que utilizar al buscar el certificado.</span><span class="sxs-lookup"><span data-stu-id="a807e-105">The method requires various parameters, such as the store where the certificate is stored and a value to use when searching for the certificate.</span></span> <span data-ttu-id="a807e-106">El siguiente procedimiento muestra cómo examinar los almacenes de un equipo para encontrar un certificado adecuado.</span><span class="sxs-lookup"><span data-stu-id="a807e-106">The following procedure demonstrates how to examine the stores on a computer to find an appropriate certificate.</span></span> <span data-ttu-id="a807e-107">Para obtener un ejemplo de encontrar la huella digital del certificado, consulte [Cómo: recuperar la huella digital de un certificado](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="a807e-107">For an example of finding the certificate thumbprint, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
### <a name="to-view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="a807e-108">Para ver los certificados en el complemento de MMC</span><span class="sxs-lookup"><span data-stu-id="a807e-108">To view certificates in the MMC snap-in</span></span>  
  
1.  <span data-ttu-id="a807e-109">Abra una ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a807e-109">Open a Command Prompt window.</span></span>  
  
2.  <span data-ttu-id="a807e-110">Tipo `mmc` y presione la tecla ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="a807e-110">Type `mmc` and press the ENTER key.</span></span> <span data-ttu-id="a807e-111">Tenga en cuenta que para ver los certificados en el almacén del equipo local, debe estar en la función del Administrador.</span><span class="sxs-lookup"><span data-stu-id="a807e-111">Note that to view certificates in the local machine store, you must be in the Administrator role.</span></span>  
  
3.  <span data-ttu-id="a807e-112">En el **archivo** menú, haga clic en **agregar/quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="a807e-112">On the **File** menu, click **Add/Remove Snap In**.</span></span>  
  
4.  <span data-ttu-id="a807e-113">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a807e-113">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="a807e-114">En el **Add Standalone Snap-in** cuadro de diálogo, seleccione **certificados**.</span><span class="sxs-lookup"><span data-stu-id="a807e-114">In the **Add Standalone Snap-in** dialog box, select **Certificates**.</span></span>  
  
6.  <span data-ttu-id="a807e-115">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a807e-115">Click **Add**.</span></span>  
  
7.  <span data-ttu-id="a807e-116">En el **complemento certificados** cuadro de diálogo, seleccione **cuenta de equipo** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a807e-116">In the **Certificates snap-in** dialog box, select **Computer account** and click **Next**.</span></span> <span data-ttu-id="a807e-117">Si lo desea, puede seleccionar **mi cuenta de usuario** o **cuenta de servicio**.</span><span class="sxs-lookup"><span data-stu-id="a807e-117">Optionally, you can select **My User account** or **Service account**.</span></span> <span data-ttu-id="a807e-118">Si no es ningún administrador del equipo, solo puede administrar los certificados para su cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="a807e-118">If you are not an administrator of the computer, you can manage certificates only for your user account.</span></span>  
  
8.  <span data-ttu-id="a807e-119">En el **Seleccionar equipo** cuadro de diálogo, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a807e-119">In the **Select Computer** dialog box, click **Finish**.</span></span>  
  
9. <span data-ttu-id="a807e-120">En el **Add Standalone Snap-in** cuadro de diálogo, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a807e-120">In the **Add Standalone Snap-in** dialog box, click **Close**.</span></span>  
  
10. <span data-ttu-id="a807e-121">En el **agregar o quitar complemento** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a807e-121">On the **Add/Remove Snap-in** dialog box, click **OK**.</span></span>  
  
11. <span data-ttu-id="a807e-122">En el **raíz de consola** ventana, haga clic en **certificados (equipo Local)** para ver el certificado se almacena en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a807e-122">In the **Console Root** window, click **Certificates (Local Computer)** to view the certificate stores for the computer.</span></span>  
  
12. <span data-ttu-id="a807e-123">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a807e-123">Optional.</span></span> <span data-ttu-id="a807e-124">Para ver los certificados para su cuenta, repita los pasos 3 a 6.</span><span class="sxs-lookup"><span data-stu-id="a807e-124">To view certificates for your account, repeat steps 3 to 6.</span></span> <span data-ttu-id="a807e-125">En el paso 7, en lugar de seleccionar **cuenta de equipo**, haga clic en **mi cuenta de usuario** y repita los pasos 8 a 10.</span><span class="sxs-lookup"><span data-stu-id="a807e-125">In step 7, instead of selecting **Computer account**, click **My User account** and repeat steps 8 to 10.</span></span>  
  
13. <span data-ttu-id="a807e-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a807e-126">Optional.</span></span> <span data-ttu-id="a807e-127">En el **archivo** menú, haga clic en **guardar** o **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="a807e-127">On the **File** menu, click **Save** or **Save As**.</span></span> <span data-ttu-id="a807e-128">Guarde el archivo de consola para utilizarlo más adelante.</span><span class="sxs-lookup"><span data-stu-id="a807e-128">Save the console file for later reuse.</span></span>  
  
## <a name="viewing-certificates-with-internet-explorer"></a><span data-ttu-id="a807e-129">Ver certificados con Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="a807e-129">Viewing Certificates with Internet Explorer</span></span>  
 <span data-ttu-id="a807e-130">También puede ver, exportar, importar y eliminar certificados utilizando Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="a807e-130">You can also view, export, import, and delete certificates by using Internet Explorer.</span></span>  
  
#### <a name="to-view-certificates-with-internet-explorer"></a><span data-ttu-id="a807e-131">Para ver certificados con Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="a807e-131">To view certificates with Internet Explorer</span></span>  
  
1.  <span data-ttu-id="a807e-132">En Internet Explorer, haga clic en **herramientas**, a continuación, haga clic en **opciones de Internet** para mostrar la **opciones de Internet** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a807e-132">In Internet Explorer, click **Tools**, then click **Internet Options** to display the **Internet Options** dialog box.</span></span>  
  
2.  <span data-ttu-id="a807e-133">Haga clic en el **contenido** ficha.</span><span class="sxs-lookup"><span data-stu-id="a807e-133">Click the **Content** tab.</span></span>  
  
3.  <span data-ttu-id="a807e-134">En **certificados**, haga clic en **certificados**.</span><span class="sxs-lookup"><span data-stu-id="a807e-134">Under **Certificates**, click **Certificates**.</span></span>  
  
4.  <span data-ttu-id="a807e-135">Para ver los detalles de un certificado, seleccione el certificado y haga clic en **vista**.</span><span class="sxs-lookup"><span data-stu-id="a807e-135">To view details of any certificate, select the certificate and click **View**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a807e-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="a807e-136">See Also</span></span>  
 [<span data-ttu-id="a807e-137">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="a807e-137">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="a807e-138">Cómo: crear certificados temporales para su uso durante el desarrollo</span><span class="sxs-lookup"><span data-stu-id="a807e-138">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)  
 [<span data-ttu-id="a807e-139">Cómo: recuperar la huella digital de un certificado</span><span class="sxs-lookup"><span data-stu-id="a807e-139">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
