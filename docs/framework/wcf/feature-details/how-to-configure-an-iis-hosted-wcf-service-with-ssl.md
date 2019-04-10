---
title: Filtrar para configurar un servicio WCF hospedado en IIS con SSL
ms.date: 03/30/2017
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
ms.openlocfilehash: 336c3800fc033cc12bd9c3fe168ae219b72cab91
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214123"
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a><span data-ttu-id="975ef-102">Filtrar para configurar un servicio WCF hospedado en IIS con SSL</span><span class="sxs-lookup"><span data-stu-id="975ef-102">How to: Configure an IIS-hosted WCF service with SSL</span></span>
<span data-ttu-id="975ef-103">En este tema se describe cómo configurar un servicio de WCF hospedado en IIS para usar la seguridad de transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="975ef-103">This topic describes how to set up an IIS-hosted WCF service to use HTTP transport security.</span></span> <span data-ttu-id="975ef-104">La seguridad de transporte HTTP necesita registrar un certificado SSL con IIS.</span><span class="sxs-lookup"><span data-stu-id="975ef-104">HTTP transport security requires an SSL certificate to be registered with IIS.</span></span> <span data-ttu-id="975ef-105">Si no tiene un certificado SSL puede usar IIS para generar un certificado de prueba.</span><span class="sxs-lookup"><span data-stu-id="975ef-105">If you do not have an SSL certificate you can use IIS to generate a test certificate.</span></span> <span data-ttu-id="975ef-106">Después debe agregar un enlace SSL al sitio web y configurar las propiedades de autenticación del sitio web.</span><span class="sxs-lookup"><span data-stu-id="975ef-106">Next you must add an SSL binding to the web site and configure the web site’s authentication properties.</span></span> <span data-ttu-id="975ef-107">Finalmente se debe configurar el servicio de WCF para usar HTTPS.</span><span class="sxs-lookup"><span data-stu-id="975ef-107">Finally you need to configure the WCF service to use HTTPS.</span></span>  
  
### <a name="creating-a-self-signed-certificate"></a><span data-ttu-id="975ef-108">Crear un certificado autofirmado</span><span class="sxs-lookup"><span data-stu-id="975ef-108">Creating a Self-Signed Certificate</span></span>  
  
1.  <span data-ttu-id="975ef-109">Abra el Administrador de Internet Information Services (inetmgr.exe) y seleccione el nombre de equipo en la vista de árbol izquierda.</span><span class="sxs-lookup"><span data-stu-id="975ef-109">Open Internet Information Services Manager (inetmgr.exe), and select your computer name in the left-hand tree view.</span></span> <span data-ttu-id="975ef-110">En la parte derecha de la pantalla, seleccione Certificados de servidor</span><span class="sxs-lookup"><span data-stu-id="975ef-110">On the right-hand side of the screen select Server Certificates</span></span>  
  
     <span data-ttu-id="975ef-111">![Pantalla de inicio del Administrador de IIS](../../../../docs/framework/wcf/feature-details/media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span><span class="sxs-lookup"><span data-stu-id="975ef-111">![IIS Manager Home Screen](../../../../docs/framework/wcf/feature-details/media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span></span>  
  
2.  <span data-ttu-id="975ef-112">En la ventana de certificados de servidor, haga clic en el **crear certificado autofirmado...**</span><span class="sxs-lookup"><span data-stu-id="975ef-112">In the Server Certificates window click the **Create Self-Signed Certificate….**</span></span> <span data-ttu-id="975ef-113">Vínculo.</span><span class="sxs-lookup"><span data-stu-id="975ef-113">Link.</span></span>  
  
     <span data-ttu-id="975ef-114">![Creación de un autoservicio&#45;firmó el certificado con IIS](../../../../docs/framework/wcf/feature-details/media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span><span class="sxs-lookup"><span data-stu-id="975ef-114">![Creating a self&#45;signed certificate with IIS](../../../../docs/framework/wcf/feature-details/media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span></span>  
  
3.  <span data-ttu-id="975ef-115">Escriba un nombre descriptivo para el certificado autofirmado y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="975ef-115">Enter a friendly name for the self-signed certificate and click **OK**.</span></span>  
  
     <span data-ttu-id="975ef-116">![Crear propio&#45;cuadro de diálogo de certificado firmado](../../../../docs/framework/wcf/feature-details/media/mg-mycert.jpg "mg_MyCert")</span><span class="sxs-lookup"><span data-stu-id="975ef-116">![Create Self&#45;Signed Certificate Dialog](../../../../docs/framework/wcf/feature-details/media/mg-mycert.jpg "mg_MyCert")</span></span>  
  
     <span data-ttu-id="975ef-117">Ahora se muestran los detalles del certificado autofirmado recién creado en el **certificados de servidor** ventana.</span><span class="sxs-lookup"><span data-stu-id="975ef-117">The newly created self-signed certificate details are now shown in the **Server Certificates** window.</span></span>  
  
     <span data-ttu-id="975ef-118">![Ventana de certificado de servidor](../../../../docs/framework/wcf/feature-details/media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span><span class="sxs-lookup"><span data-stu-id="975ef-118">![Server Certificate Window](../../../../docs/framework/wcf/feature-details/media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span></span>  
  
     <span data-ttu-id="975ef-119">El certificado generado se instala en el almacén de entidades de certificación raíz de confianza.</span><span class="sxs-lookup"><span data-stu-id="975ef-119">The generated certificate is installed in the Trusted Root Certification Authorities store.</span></span>  
  
### <a name="add-ssl-binding"></a><span data-ttu-id="975ef-120">Agregar enlace SSL</span><span class="sxs-lookup"><span data-stu-id="975ef-120">Add SSL Binding</span></span>  
  
1.  <span data-ttu-id="975ef-121">Todavía en el Administrador de Internet Information Services, expanda el **sitios** carpeta y, a continuación, el **sitio Web predeterminado** carpeta en la vista de árbol en el lado izquierdo de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="975ef-121">Still in Internet Information Services Manager, expand the **Sites** folder and then the **Default Web Site** folder in the tree view on the left-hand side of the screen.</span></span>  
  
2.  <span data-ttu-id="975ef-122">Haga clic en el **enlaces...**</span><span class="sxs-lookup"><span data-stu-id="975ef-122">Click the **Bindings….**</span></span> <span data-ttu-id="975ef-123">Vínculo de la **acciones** sección en la parte superior derecha de la ventana.</span><span class="sxs-lookup"><span data-stu-id="975ef-123">Link in the **Actions** section in the upper right hand portion of the window.</span></span>  
  
     <span data-ttu-id="975ef-124">![Agregar un enlace SSL](../../../../docs/framework/wcf/feature-details/media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span><span class="sxs-lookup"><span data-stu-id="975ef-124">![Adding an SSL binding](../../../../docs/framework/wcf/feature-details/media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span></span>  
  
3.  <span data-ttu-id="975ef-125">En la ventana de enlaces de sitios, haga clic en el **agregar** botón.</span><span class="sxs-lookup"><span data-stu-id="975ef-125">In the Site Bindings window click the **Add** button.</span></span>  
  
     <span data-ttu-id="975ef-126">![Cuadro de diálogo enlaces de sitio](../../../../docs/framework/wcf/feature-details/media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span><span class="sxs-lookup"><span data-stu-id="975ef-126">![Site Bindings Dialog](../../../../docs/framework/wcf/feature-details/media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span></span>  
  
4.  <span data-ttu-id="975ef-127">En el **Agregar enlace de sitio** cuadro de diálogo, seleccione https para el tipo y el nombre descriptivo del certificado autofirmado recién creado.</span><span class="sxs-lookup"><span data-stu-id="975ef-127">In the **Add Site Binding** dialog, select https for the type and the friendly name of the self-signed certificate you just created.</span></span>  
  
     <span data-ttu-id="975ef-128">![Ejemplo de enlace de sitio](../../../../docs/framework/wcf/feature-details/media/mg-mycertbinding.jpg "mg_MyCertBinding")</span><span class="sxs-lookup"><span data-stu-id="975ef-128">![Site binding example](../../../../docs/framework/wcf/feature-details/media/mg-mycertbinding.jpg "mg_MyCertBinding")</span></span>  
  
### <a name="configure-virtual-directory-for-ssl"></a><span data-ttu-id="975ef-129">Configurar el directorio virtual para SSL</span><span class="sxs-lookup"><span data-stu-id="975ef-129">Configure Virtual Directory for SSL</span></span>  
  
1.  <span data-ttu-id="975ef-130">En el Administrador de Internet Information Services, seleccione el directorio virtual que contiene el servicio seguro de WCF.</span><span class="sxs-lookup"><span data-stu-id="975ef-130">Still in Internet Information Services Manager, select the virtual directory that contains your WCF secure service.</span></span>  
  
2.  <span data-ttu-id="975ef-131">En el panel central de la ventana, seleccione **configuración SSL** en la sección IIS.</span><span class="sxs-lookup"><span data-stu-id="975ef-131">In the center pane of the window, select **SSL Settings** in the IIS section.</span></span>  
  
     <span data-ttu-id="975ef-132">![Configuración de SSL para el directorio virtual](../../../../docs/framework/wcf/feature-details/media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span><span class="sxs-lookup"><span data-stu-id="975ef-132">![SSL Settings for virtual directory](../../../../docs/framework/wcf/feature-details/media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span></span>  
  
3.  <span data-ttu-id="975ef-133">En el panel de configuración de SSL, seleccione el **requerir SSL** casilla y haga clic en el **aplicar** vincular en el **acciones** sección en el lado derecho de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="975ef-133">In the SSL Settings pane, select the **Require SSL** checkbox and click the **Apply** link in the **Actions** section on the right hand side of the screen.</span></span>  
  
     <span data-ttu-id="975ef-134">![Configuración de SSL del directorio virtual](../../../../docs/framework/wcf/feature-details/media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span><span class="sxs-lookup"><span data-stu-id="975ef-134">![Virtual directory SSL settings](../../../../docs/framework/wcf/feature-details/media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span></span>  
  
### <a name="configure-wcf-service-for-http-transport-security"></a><span data-ttu-id="975ef-135">Configurar el servicio WCF para la seguridad de transporte HTTP</span><span class="sxs-lookup"><span data-stu-id="975ef-135">Configure WCF Service for HTTP Transport Security</span></span>  
  
1.  <span data-ttu-id="975ef-136">En el archivo web.config del servicio de WCF, configure el enlace HTTP para usar seguridad de transporte como se muestra en el siguiente código XML.</span><span class="sxs-lookup"><span data-stu-id="975ef-136">In the WCF service’s web.config configure the HTTP binding to use transport security as shown in the following XML.</span></span>  
  
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
  
2.  <span data-ttu-id="975ef-137">Especifique el servicio y el punto de conexión del servicio tal y como se muestra en el siguiente código XML.</span><span class="sxs-lookup"><span data-stu-id="975ef-137">Specify your service and service endpoint as shown in the following XML.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="975ef-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="975ef-138">Example</span></span>  
 <span data-ttu-id="975ef-139">A continuación se muestra un ejemplo completo de un archivo web.config para un servicio de WCF mediante la seguridad de transporte HTTP</span><span class="sxs-lookup"><span data-stu-id="975ef-139">The following is a complete example of a web.config file for a WCF service using HTTP transport security</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="975ef-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="975ef-140">See also</span></span>

- [<span data-ttu-id="975ef-141">Hospedaje en Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="975ef-141">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)
- [<span data-ttu-id="975ef-142">Instrucciones de hospedaje Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="975ef-142">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
- [<span data-ttu-id="975ef-143">Procedimientos recomendados de hospedaje de Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="975ef-143">Internet Information Services Hosting Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
- [<span data-ttu-id="975ef-144">Hospedaje de IIS utilizando código en línea</span><span class="sxs-lookup"><span data-stu-id="975ef-144">IIS Hosting Using Inline Code</span></span>](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)
