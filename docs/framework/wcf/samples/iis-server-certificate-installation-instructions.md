---
title: "Instrucciones de instalación del certificado de servidor de Internet Information Services (IIS)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11281490-d2ac-4324-8f33-e7714611a34b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0d035e703b79eb184bf06e3e75255e2f987c170
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="internet-information-services-iis-server-certificate-installation-instructions"></a><span data-ttu-id="6a2c9-102">Instrucciones de instalación del certificado de servidor de Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="6a2c9-102">Internet Information Services (IIS) Server Certificate Installation Instructions</span></span>
<span data-ttu-id="6a2c9-103">Para ejecutar los ejemplos que se comunican de forma segura con Internet Information Services (IIS), debe crear e instalar un certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-103">To run the samples that securely communicate with Internet Information Services (IIS), you must create and install a server certificate.</span></span>  
  
## <a name="step-1-creating-certificates"></a><span data-ttu-id="6a2c9-104">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-104">Step 1.</span></span> <span data-ttu-id="6a2c9-105">Crear certificados</span><span class="sxs-lookup"><span data-stu-id="6a2c9-105">Creating Certificates</span></span>  
 <span data-ttu-id="6a2c9-106">Para crear un certificado para su equipo, abra un símbolo del sistema de Visual Studio con privilegios de administrador y ejecute el archivo Setup.bat que se incluye en cada uno de los ejemplos que utilizan la comunicación segura con IIS.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-106">To create a certificate for your computer, open a Visual Studio command prompt with administrator privileges and run the Setup.bat that is included in each of the samples that use secure communication with IIS.</span></span> <span data-ttu-id="6a2c9-107">Asegúrese de que la ruta de acceso incluye la carpeta que contiene makecert.exe antes de ejecutar este archivo por lotes.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-107">Ensure that the path includes the folder that contains Makecert.exe before you run this batch file.</span></span> <span data-ttu-id="6a2c9-108">El siguiente comando se utiliza para crear el certificado en Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-108">The following command is used to create the certificate in Setup.bat.</span></span>  
  
```  
makecert -sr LocalMachine -ss My -n CN=ServiceModelSamples-HTTPS-Server -sky exchange -sk ServiceModelSamples-HTTPS-Key  
```  
  
## <a name="step-2-installing-certificates"></a><span data-ttu-id="6a2c9-109">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-109">Step 2.</span></span> <span data-ttu-id="6a2c9-110">Instalar certificados</span><span class="sxs-lookup"><span data-stu-id="6a2c9-110">Installing Certificates</span></span>  
 <span data-ttu-id="6a2c9-111">Los pasos requeridos para instalar los certificados que acaba de crear dependen de la versión de IIS que está utilizando.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-111">The steps required to install the certificates you just created depend on which version of IIS you are using.</span></span>  
  
#### <a name="to-install-iis-on-iis-51-windows-xp-and-iis-60-windows-server-2003"></a><span data-ttu-id="6a2c9-112">Para instalar IIS en IIS 5.1 (Windows XP) e IIS 6.0 (Windows Server 2003)</span><span class="sxs-lookup"><span data-stu-id="6a2c9-112">To install IIS on IIS 5.1 (Windows XP) and IIS 6.0 (Windows Server 2003)</span></span>  
  
1.  <span data-ttu-id="6a2c9-113">Abra el complemento MMC del administrador de Internet Information Services.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-113">Open the Internet Information Services Manager MMC Snap-In.</span></span>  
  
2.  <span data-ttu-id="6a2c9-114">Haga clic en el sitio Web predeterminado y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-114">Right-click the default Web site and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="6a2c9-115">Seleccione el **seguridad de directorios** ficha.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-115">Select the **Directory Security** tab.</span></span>  
  
4.  <span data-ttu-id="6a2c9-116">Haga clic en el **certificado de servidor** botón.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-116">Click the **Server Certificate** button.</span></span> <span data-ttu-id="6a2c9-117">Se inicia el Asistente para certificados de servidor web.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-117">The Web Server Certificate Wizard starts.</span></span>  
  
5.  <span data-ttu-id="6a2c9-118">Complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-118">Complete the wizard.</span></span> <span data-ttu-id="6a2c9-119">Seleccione la opción para asignar un certificado.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-119">Select the option to assign a certificate.</span></span> <span data-ttu-id="6a2c9-120">Seleccione el certificado ServiceModelSamples-HTTPS-Server de la lista de certificados que se muestran.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-120">Select the ServiceModelSamples-HTTPS-Server certificate from the list of certificates that are displayed.</span></span>  
  
     <span data-ttu-id="6a2c9-121">![Asistente para certificados IIS](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span><span class="sxs-lookup"><span data-stu-id="6a2c9-121">![IIS Certificate Wizard](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span></span>  
  
6.  <span data-ttu-id="6a2c9-122">Pruebe el acceso al servicio en un explorador utilizando la dirección HTTPS https://localhost/servicemodelsamples/service.svc.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-122">Test access to the service in a browser by using the HTTPS address https://localhost/servicemodelsamples/service.svc.</span></span>  
  
#### <a name="if-ssl-was-previously-configured-by-using-httpcfgexe"></a><span data-ttu-id="6a2c9-123">Si SSL se configuró previamente utilizando httpcfg.exe</span><span class="sxs-lookup"><span data-stu-id="6a2c9-123">If SSL was previously configured by using Httpcfg.exe</span></span>  
  
1.  <span data-ttu-id="6a2c9-124">Utilice makecert.exe (o ejecute setup.bat) para crear el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-124">Use Makecert.exe (or run Setup.bat) to create the server certificate.</span></span>  
  
2.  <span data-ttu-id="6a2c9-125">Ejecute el Administrador de IIS e instale el certificado según los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-125">Run the IIS manager and install the certificate according to the previous steps.</span></span>  
  
3.  <span data-ttu-id="6a2c9-126">Agregue la línea siguiente de código al programa cliente:</span><span class="sxs-lookup"><span data-stu-id="6a2c9-126">Add the following line of code to the client program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6a2c9-127">Este código solo se requiere para los certificados de prueba como los creados por makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-127">This code is only required for test certificates such as those created by Makecert.exe.</span></span> <span data-ttu-id="6a2c9-128">No se recomienda para el código de producción.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-128">It is not recommended for production code.</span></span>  
  
```  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
#### <a name="to-install-iis-on-iis-70-windows-vista-and-windows-server-2008"></a><span data-ttu-id="6a2c9-129">Para instalar IIS en IIS 7.0 (Windows Vista y Windows Server 2008)</span><span class="sxs-lookup"><span data-stu-id="6a2c9-129">To install IIS on IIS 7.0 (Windows Vista and Windows Server 2008)</span></span>  
  
1.  <span data-ttu-id="6a2c9-130">Desde el **iniciar** menú, haga clic en **ejecutar**, a continuación, escriba **inetmgr** para abrir el complemento MMC de servicios de Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="6a2c9-130">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2.  <span data-ttu-id="6a2c9-131">Haga clic en el **sitio Web predeterminado** y seleccione **modificar enlaces...**</span><span class="sxs-lookup"><span data-stu-id="6a2c9-131">Right-click the **Default Web Site** and select **Edit Bindings…**</span></span>  
  
3.  <span data-ttu-id="6a2c9-132">Haga clic en el **agregar** botón de la **enlaces de sitios** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-132">Click the **Add** button of the **Site Bindings** dialog box.</span></span>  
  
4.  <span data-ttu-id="6a2c9-133">Seleccione **HTTPS** desde el **tipo** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-133">Select **HTTPS** from the **Type** drop-down list.</span></span>  
  
5.  <span data-ttu-id="6a2c9-134">Seleccione el **ServiceModelSamples-HTTPS-Server** desde el **certificado SSL** lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-134">Select the **ServiceModelSamples-HTTPS-Server** from the **SSL certificate** drop-down list and click **OK**.</span></span>  
  
6.  <span data-ttu-id="6a2c9-135">Pruebe el acceso al servicio en un explorador utilizando la dirección HTTPS https://localhost/servicemodelsamples/service.svc.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-135">Test access to the service in a browser by using the HTTPS address https://localhost/servicemodelsamples/service.svc.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a2c9-136">Dado que el certificado de prueba que acaba de instalar no es un certificado de confianza, puede encontrar advertencias de seguridad de Internet Explorer adicionales al ir a las direcciones web locales protegidas con este certificado.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-136">Because the test certificate you have just installed is not a trusted certificate, you may encounter additional Internet Explorer security warnings when browsing to local Web addresses secured with this certificate.</span></span>  
  
## <a name="removing-certificates"></a><span data-ttu-id="6a2c9-137">Quitar Certificados</span><span class="sxs-lookup"><span data-stu-id="6a2c9-137">Removing Certificates</span></span>  
  
-   <span data-ttu-id="6a2c9-138">Utilice el Administrador de Internet Information Services según las instrucciones anteriores, pero quite el certificado o enlace en lugar de agregarlo.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-138">Use the Internet Information Services Manager as previously directed, but remove the certificate or binding instead of adding it.</span></span>  
  
-   <span data-ttu-id="6a2c9-139">Quite el certificado de equipo utilizando el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="6a2c9-139">Remove the computer certificate by using the following command.</span></span>  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:443  
    ```
