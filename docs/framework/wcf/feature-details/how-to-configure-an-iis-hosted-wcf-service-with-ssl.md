---
title: Procedimiento para configurar un servicio WCF hospedado en IIS con SSL
ms.date: 03/30/2017
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
ms.openlocfilehash: fb3e87021c3dce1172250f33fd302916920af74d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597233"
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a><span data-ttu-id="08769-102">Procedimiento para configurar un servicio WCF hospedado en IIS con SSL</span><span class="sxs-lookup"><span data-stu-id="08769-102">How to: Configure an IIS-hosted WCF service with SSL</span></span>
<span data-ttu-id="08769-103">En este tema se describe cómo configurar un servicio de WCF hospedado en IIS para usar la seguridad de transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="08769-103">This topic describes how to set up an IIS-hosted WCF service to use HTTP transport security.</span></span> <span data-ttu-id="08769-104">La seguridad de transporte HTTP necesita registrar un certificado SSL con IIS.</span><span class="sxs-lookup"><span data-stu-id="08769-104">HTTP transport security requires an SSL certificate to be registered with IIS.</span></span> <span data-ttu-id="08769-105">Si no tiene un certificado SSL puede usar IIS para generar un certificado de prueba.</span><span class="sxs-lookup"><span data-stu-id="08769-105">If you do not have an SSL certificate you can use IIS to generate a test certificate.</span></span> <span data-ttu-id="08769-106">Después debe agregar un enlace SSL al sitio web y configurar las propiedades de autenticación del sitio web.</span><span class="sxs-lookup"><span data-stu-id="08769-106">Next you must add an SSL binding to the web site and configure the web site’s authentication properties.</span></span> <span data-ttu-id="08769-107">Finalmente se debe configurar el servicio de WCF para usar HTTPS.</span><span class="sxs-lookup"><span data-stu-id="08769-107">Finally you need to configure the WCF service to use HTTPS.</span></span>  
  
### <a name="creating-a-self-signed-certificate"></a><span data-ttu-id="08769-108">Crear un certificado autofirmado</span><span class="sxs-lookup"><span data-stu-id="08769-108">Creating a Self-Signed Certificate</span></span>  
  
1. <span data-ttu-id="08769-109">Abra el Administrador de Internet Information Services (inetmgr.exe) y seleccione el nombre de equipo en la vista de árbol izquierda.</span><span class="sxs-lookup"><span data-stu-id="08769-109">Open Internet Information Services Manager (inetmgr.exe), and select your computer name in the left-hand tree view.</span></span> <span data-ttu-id="08769-110">En la parte derecha de la pantalla, seleccione Certificados de servidor</span><span class="sxs-lookup"><span data-stu-id="08769-110">On the right-hand side of the screen select Server Certificates</span></span>  
  
     <span data-ttu-id="08769-111">![Pantalla principal del Administrador de IIS](media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span><span class="sxs-lookup"><span data-stu-id="08769-111">![IIS Manager Home Screen](media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span></span>  
  
2. <span data-ttu-id="08769-112">En la ventana certificados de servidor, haga clic en el vínculo **crear certificado autofirmado....**</span><span class="sxs-lookup"><span data-stu-id="08769-112">In the Server Certificates window click the **Create Self-Signed Certificate….**</span></span> <span data-ttu-id="08769-113">Vínculo.</span><span class="sxs-lookup"><span data-stu-id="08769-113">Link.</span></span>  
  
     <span data-ttu-id="08769-114">![Creación de un certificado auto&#45;firmado con IIS](media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span><span class="sxs-lookup"><span data-stu-id="08769-114">![Creating a self&#45;signed certificate with IIS](media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span></span>  
  
3. <span data-ttu-id="08769-115">Escriba un nombre descriptivo para el certificado autofirmado y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="08769-115">Enter a friendly name for the self-signed certificate and click **OK**.</span></span>  
  
     <span data-ttu-id="08769-116">![Cuadro de diálogo Crear certificado auto&#45;firmado](media/mg-mycert.jpg "mg_MyCert")</span><span class="sxs-lookup"><span data-stu-id="08769-116">![Create Self&#45;Signed Certificate Dialog](media/mg-mycert.jpg "mg_MyCert")</span></span>  
  
     <span data-ttu-id="08769-117">Los detalles del certificado autofirmado recién creado se muestran ahora en la ventana **certificados de servidor** .</span><span class="sxs-lookup"><span data-stu-id="08769-117">The newly created self-signed certificate details are now shown in the **Server Certificates** window.</span></span>  
  
     <span data-ttu-id="08769-118">![Ventana de certificado de servidor](media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span><span class="sxs-lookup"><span data-stu-id="08769-118">![Server Certificate Window](media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span></span>  
  
     <span data-ttu-id="08769-119">El certificado generado se instala en el almacén de entidades de certificación raíz de confianza.</span><span class="sxs-lookup"><span data-stu-id="08769-119">The generated certificate is installed in the Trusted Root Certification Authorities store.</span></span>  
  
### <a name="add-ssl-binding"></a><span data-ttu-id="08769-120">Agregar enlace SSL</span><span class="sxs-lookup"><span data-stu-id="08769-120">Add SSL Binding</span></span>  
  
1. <span data-ttu-id="08769-121">En el administrador de Internet Information Services, expanda la carpeta **sitios** y, a continuación, la carpeta **sitio web predeterminado** en la vista de árbol del lado izquierdo de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="08769-121">Still in Internet Information Services Manager, expand the **Sites** folder and then the **Default Web Site** folder in the tree view on the left-hand side of the screen.</span></span>  
  
2. <span data-ttu-id="08769-122">Haga clic en los **enlaces....**</span><span class="sxs-lookup"><span data-stu-id="08769-122">Click the **Bindings….**</span></span> <span data-ttu-id="08769-123">En la sección **acciones** de la parte superior derecha de la ventana.</span><span class="sxs-lookup"><span data-stu-id="08769-123">Link in the **Actions** section in the upper right hand portion of the window.</span></span>  
  
     <span data-ttu-id="08769-124">![Agregar un enlace SSL](media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span><span class="sxs-lookup"><span data-stu-id="08769-124">![Adding an SSL binding](media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span></span>  
  
3. <span data-ttu-id="08769-125">En la ventana enlaces de sitios, haga clic en el botón **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="08769-125">In the Site Bindings window click the **Add** button.</span></span>  
  
     <span data-ttu-id="08769-126">![Cuadro de diálogo Enlaces de sitios](media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span><span class="sxs-lookup"><span data-stu-id="08769-126">![Site Bindings Dialog](media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span></span>  
  
4. <span data-ttu-id="08769-127">En el cuadro de diálogo **Agregar enlace de sitio** , seleccione https como el tipo y el nombre descriptivo del certificado autofirmado que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="08769-127">In the **Add Site Binding** dialog, select https for the type and the friendly name of the self-signed certificate you just created.</span></span>  
  
     <span data-ttu-id="08769-128">![Ejemplo de enlace de sitio](media/mg-mycertbinding.jpg "mg_MyCertBinding")</span><span class="sxs-lookup"><span data-stu-id="08769-128">![Site binding example](media/mg-mycertbinding.jpg "mg_MyCertBinding")</span></span>  
  
### <a name="configure-virtual-directory-for-ssl"></a><span data-ttu-id="08769-129">Configurar el directorio virtual para SSL</span><span class="sxs-lookup"><span data-stu-id="08769-129">Configure Virtual Directory for SSL</span></span>  
  
1. <span data-ttu-id="08769-130">En el Administrador de Internet Information Services, seleccione el directorio virtual que contiene el servicio seguro de WCF.</span><span class="sxs-lookup"><span data-stu-id="08769-130">Still in Internet Information Services Manager, select the virtual directory that contains your WCF secure service.</span></span>  
  
2. <span data-ttu-id="08769-131">En el panel central de la ventana, seleccione **configuración de SSL** en la sección IIS.</span><span class="sxs-lookup"><span data-stu-id="08769-131">In the center pane of the window, select **SSL Settings** in the IIS section.</span></span>  
  
     <span data-ttu-id="08769-132">![Configuración de SSL para el directorio virtual](media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span><span class="sxs-lookup"><span data-stu-id="08769-132">![SSL Settings for virtual directory](media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span></span>  
  
3. <span data-ttu-id="08769-133">En el panel Configuración de SSL, active la casilla **requerir SSL** y haga clic en el vínculo **aplicar** en la sección **acciones** en la parte derecha de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="08769-133">In the SSL Settings pane, select the **Require SSL** checkbox and click the **Apply** link in the **Actions** section on the right hand side of the screen.</span></span>  
  
     <span data-ttu-id="08769-134">![Configuración de SSL del directorio virtual](media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span><span class="sxs-lookup"><span data-stu-id="08769-134">![Virtual directory SSL settings](media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span></span>  
  
### <a name="configure-wcf-service-for-http-transport-security"></a><span data-ttu-id="08769-135">Configurar el servicio WCF para la seguridad de transporte HTTP</span><span class="sxs-lookup"><span data-stu-id="08769-135">Configure WCF Service for HTTP Transport Security</span></span>  
  
1. <span data-ttu-id="08769-136">En el archivo web.config del servicio de WCF, configure el enlace HTTP para usar seguridad de transporte como se muestra en el siguiente código XML.</span><span class="sxs-lookup"><span data-stu-id="08769-136">In the WCF service’s web.config configure the HTTP binding to use transport security as shown in the following XML.</span></span>  
  
    ```xml  
    <bindings>  
          <basicHttpBinding>  
            <binding name="secureHttpBinding">  
              <security mode="Transport">  
                <transport clientCredentialType="None"/>  
              </security>  
            </binding>  
          </basicHttpBinding>  
    </bindings>  
    ```  
  
2. <span data-ttu-id="08769-137">Especifique el servicio y el punto de conexión del servicio tal y como se muestra en el siguiente código XML.</span><span class="sxs-lookup"><span data-stu-id="08769-137">Specify your service and service endpoint as shown in the following XML.</span></span>  
  
    ```xml  
    <services>  
          <service name="MySecureWCFService.Service1">  
            <endpoint address=""  
                      binding="basicHttpBinding"  
                      bindingConfiguration="secureHttpBinding"  
                      contract="MySecureWCFService.IService1"/>  
  
            <endpoint address="mex"  
                      binding="mexHttpsBinding"  
                      contract="IMetadataExchange" />  
          </service>  
    </services>  
    ```  
  
## <a name="example"></a><span data-ttu-id="08769-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="08769-138">Example</span></span>  
 <span data-ttu-id="08769-139">A continuación se muestra un ejemplo completo de un archivo web.config para un servicio de WCF mediante la seguridad de transporte HTTP</span><span class="sxs-lookup"><span data-stu-id="08769-139">The following is a complete example of a web.config file for a WCF service using HTTP transport security</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <services>  
      <service name="MySecureWCFService.Service1">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  bindingConfiguration="secureHttpBinding"  
                  contract="MySecureWCFService.IService1"/>  
  
        <endpoint address="mex"  
                  binding="mexHttpsBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="secureHttpBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <!-- To avoid disclosing metadata information, set the value below to false and remove the metadata endpoint above before deployment -->  
          <serviceMetadata httpsGetEnabled="true"/>  
          <!-- To receive exception details in faults for debugging purposes, set the value below to true.  Set to false before deployment to avoid disclosing exception information -->  
          <serviceDebug includeExceptionDetailInFaults="false"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
  </system.serviceModel>  
  <system.webServer>  
    <modules runAllManagedModulesForAllRequests="true"/>  
  </system.webServer>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="08769-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="08769-140">See also</span></span>

- [<span data-ttu-id="08769-141">Hospedaje en Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="08769-141">Hosting in Internet Information Services</span></span>](hosting-in-internet-information-services.md)
- [<span data-ttu-id="08769-142">Instrucciones de hospedaje Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="08769-142">Internet Information Service Hosting Instructions</span></span>](../samples/internet-information-service-hosting-instructions.md)
- [<span data-ttu-id="08769-143">Procedimientos recomendados de hospedaje de Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="08769-143">Internet Information Services Hosting Best Practices</span></span>](internet-information-services-hosting-best-practices.md)
- [<span data-ttu-id="08769-144">Hospedaje de IIS utilizando código en línea</span><span class="sxs-lookup"><span data-stu-id="08769-144">IIS Hosting Using Inline Code</span></span>](../samples/iis-hosting-using-inline-code.md)
