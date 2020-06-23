---
title: Procedimiento para configurar un servicio WCF hospedado en IIS con SSL
description: Obtenga información acerca de cómo configurar un servicio WCF hospedado en IIS para utilizar la seguridad de transporte HTTP, que requiere un certificado que esté registrado en IIS.
ms.date: 03/30/2017
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
ms.openlocfilehash: 8dc4692863d93e407a122c0ba93ae38323b8b213
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245263"
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a>Procedimiento para configurar un servicio WCF hospedado en IIS con SSL
En este tema se describe cómo configurar un servicio de WCF hospedado en IIS para usar la seguridad de transporte HTTP. La seguridad de transporte HTTP necesita registrar un certificado SSL con IIS. Si no tiene un certificado SSL puede usar IIS para generar un certificado de prueba. Después debe agregar un enlace SSL al sitio web y configurar las propiedades de autenticación del sitio web. Finalmente se debe configurar el servicio de WCF para usar HTTPS.  
  
### <a name="creating-a-self-signed-certificate"></a>Crear un certificado autofirmado  
  
1. Abra el Administrador de Internet Information Services (inetmgr.exe) y seleccione el nombre de equipo en la vista de árbol izquierda. En la parte derecha de la pantalla, seleccione Certificados de servidor  
  
     ![Pantalla principal del Administrador de IIS](media/mg-inetmgrhome.jpg "mg_INetMgrHome")  
  
2. En la ventana certificados de servidor, haga clic en el vínculo **crear certificado autofirmado....** Vínculo.  
  
     ![Creación de un certificado auto&#45;firmado con IIS](media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")  
  
3. Escriba un nombre descriptivo para el certificado autofirmado y haga clic en **Aceptar**.  
  
     ![Cuadro de diálogo Crear certificado auto&#45;firmado](media/mg-mycert.jpg "mg_MyCert")  
  
     Los detalles del certificado autofirmado recién creado se muestran ahora en la ventana **certificados de servidor** .  
  
     ![Ventana de certificado de servidor](media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")  
  
     El certificado generado se instala en el almacén de entidades de certificación raíz de confianza.  
  
### <a name="add-ssl-binding"></a>Agregar enlace SSL  
  
1. En el administrador de Internet Information Services, expanda la carpeta **sitios** y, a continuación, la carpeta **sitio web predeterminado** en la vista de árbol del lado izquierdo de la pantalla.  
  
2. Haga clic en los **enlaces....** En la sección **acciones** de la parte superior derecha de la ventana.  
  
     ![Agregar un enlace SSL](media/mg-addsslbinding.jpg "mg_AddSSLBinding")  
  
3. En la ventana enlaces de sitios, haga clic en el botón **Agregar** .  
  
     ![Cuadro de diálogo Enlaces de sitios](media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")  
  
4. En el cuadro de diálogo **Agregar enlace de sitio** , seleccione https como el tipo y el nombre descriptivo del certificado autofirmado que acaba de crear.  
  
     ![Ejemplo de enlace de sitio](media/mg-mycertbinding.jpg "mg_MyCertBinding")  
  
### <a name="configure-virtual-directory-for-ssl"></a>Configurar el directorio virtual para SSL  
  
1. En el Administrador de Internet Information Services, seleccione el directorio virtual que contiene el servicio seguro de WCF.  
  
2. En el panel central de la ventana, seleccione **configuración de SSL** en la sección IIS.  
  
     ![Configuración de SSL para el directorio virtual](media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")  
  
3. En el panel Configuración de SSL, active la casilla **requerir SSL** y haga clic en el vínculo **aplicar** en la sección **acciones** en la parte derecha de la pantalla.  
  
     ![Configuración de SSL del directorio virtual](media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")  
  
### <a name="configure-wcf-service-for-http-transport-security"></a>Configurar el servicio WCF para la seguridad de transporte HTTP  
  
1. En el archivo web.config del servicio de WCF, configure el enlace HTTP para usar seguridad de transporte como se muestra en el siguiente código XML.  
  
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
  
2. Especifique el servicio y el punto de conexión del servicio tal y como se muestra en el siguiente código XML.  
  
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
  
## <a name="example"></a>Ejemplo  
 A continuación se muestra un ejemplo completo de un archivo web.config para un servicio de WCF mediante la seguridad de transporte HTTP  
  
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
  
## <a name="see-also"></a>Consulte también

- [Hospedaje en Internet Information Services](hosting-in-internet-information-services.md)
- [Instrucciones de hospedaje Internet Information Services](../samples/internet-information-service-hosting-instructions.md)
- [Procedimientos recomendados de hospedaje de Internet Information Services](internet-information-services-hosting-best-practices.md)
- [Hospedaje de IIS utilizando código en línea](../samples/iis-hosting-using-inline-code.md)
