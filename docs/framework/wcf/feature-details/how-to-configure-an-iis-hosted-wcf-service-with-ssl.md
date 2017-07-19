---
title: "Configurar un servicio WCF hospedado en IIS con SSL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Configurar un servicio WCF hospedado en IIS con SSL
En este tema se describe cómo configurar un servicio de WCF hospedado en IIS para usar la seguridad de transporte HTTP.  La seguridad de transporte HTTP necesita registrar un certificado SSL con IIS.  Si no tiene un certificado SSL puede usar IIS para generar un certificado de prueba.  Después debe agregar un enlace SSL al sitio web y configurar las propiedades de autenticación del sitio web.  Finalmente se debe configurar el servicio de WCF para usar HTTPS.  
  
### Crear un certificado autofirmado  
  
1.  Abra el Administrador de Internet Information Services \(inetmgr.exe\) y seleccione el nombre de equipo en la vista de árbol izquierda.  En la parte derecha de la pantalla, seleccione Certificados de servidor  
  
     ![Pantalla principal del Administrador de IIS](../../../../docs/framework/wcf/feature-details/media/mg-inetmgrhome.jpg "mg\_INetMgrHome")  
  
2.  En la ventana Certificados de servidor, haga clic en **Crear certificado autofirmado….** Vínculo.  
  
     ![Crear un certificado autofirmado con IIS](../../../../docs/framework/wcf/feature-details/media/mg-createselfsignedcert.jpg "mg\_CreateSelfSignedCert")  
  
3.  Escriba un nombre descriptivo para el certificado autofirmado y haga clic en **Aceptar**.  
  
     ![Cuadro de diálogo Crear certificado autofirmado](../../../../docs/framework/wcf/feature-details/media/mg-mycert.jpg "mg\_MyCert")  
  
     Los detalles del certificado autofirmado recién creado se muestran ahora en la ventana **Certificados de servidor**.  
  
     ![Ventana de certificado de servidor](../../../../docs/framework/wcf/feature-details/media/mg-servercertificatewindow.jpg "mg\_ServerCertificateWindow")  
  
     El certificado generado se instala en el almacén de entidades de certificación raíz de confianza.  
  
### Agregar enlace SSL  
  
1.  En el Administrador de Internet Information Services, expanda la carpeta **Sitios** y después la carpeta **Sitio Web predeterminado** en la vista de árbol en el lado izquierdo de la pantalla.  
  
2.  Haga clic en **Enlaces….** Haga clic en el vínculo de la sección **Acciones** en la parte superior derecha de la ventana.  
  
     ![Agregar un enlace SSL](../../../../docs/framework/wcf/feature-details/media/mg-addsslbinding.jpg "mg\_AddSSLBinding")  
  
3.  En la ventana Enlaces de sitio, haga clic en el botón **Agregar**.  
  
     ![Cuadro de diálogo Enlaces de sitios](../../../../docs/framework/wcf/feature-details/media/mg-sitebindingsdialog.jpg "mg\_SiteBindingsDialog")  
  
4.  En el cuadro de diálogo **Agregar enlace de sitio**, seleccione https para el tipo y el nombre descriptivo del certificado autofirmado que acaba de crear.  
  
     ![Ejemplo de enlace de sitio](../../../../docs/framework/wcf/feature-details/media/mg-mycertbinding.jpg "mg\_MyCertBinding")  
  
### Configurar el directorio virtual para SSL  
  
1.  En el Administrador de Internet Information Services, seleccione el directorio virtual que contiene el servicio seguro de WCF.  
  
2.  En el panel central de la ventana, seleccione **Configuración de SSL** en la sección IIS.  
  
     ![Configuración de SSL para el directorio virtual](../../../../docs/framework/wcf/feature-details/media/mg-sslsettingsforvdir.jpg "mg\_SSLSettingsForVDir")  
  
3.  En el panel Configuración de SSL, active la casilla **Requerir SSL** y haga clic en el vínculo **Aplicar** en la sección **Acciones** en el lado derecho de la pantalla.  
  
     ![Configuración de SSL del directorio virtual](../../../../docs/framework/wcf/feature-details/media/mg-vdirsslsettings.JPG "mg\_VDirSSLSettings")  
  
### Configurar el servicio WCF para la seguridad de transporte HTTP  
  
1.  En el archivo web.config del servicio de WCF, configure el enlace HTTP para usar seguridad de transporte como se muestra en el siguiente código XML.  
  
    ```  
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
  
2.  Especifique el servicio y el extremo del servicio tal y como se muestra en el siguiente código XML.  
  
    ```  
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
  
## Ejemplo  
 A continuación se muestra un ejemplo completo de un archivo web.config para un servicio de WCF mediante la seguridad de transporte HTTP  
  
```  
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
  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
## Vea también  
 [Hospedaje en Internet Information Services](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)   
 [Instrucciones de hospedaje Internet Information Services](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)   
 [Procedimientos recomendados de hospedaje de Internet Information Services](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)   
 [Hospedaje de IIS utilizando código en línea](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)