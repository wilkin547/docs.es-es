---
title: "Ejemplo de seguridad de mensaje | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 82444166-6288-493a-85d4-85f43f134d19
caps.latest.revision: 33
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 33
---
# Ejemplo de seguridad de mensaje
Este ejemplo muestra cómo implementar una aplicación que utiliza `basicHttpBinding` y seguridad de mensaje.Este ejemplo se basa en [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El modo de seguridad de `basicHttpBinding` puede establecerse en los valores siguientes: `Message`, `Transport`, `TransportWithMessageCredential`, `TransportCredentialOnly` y `None`.En el siguiente archivo App.config del servicio del ejemplo, la definición de extremo especifica `basicHttpBinding` y hace referencia una configuración de enlace denominada `Binding1`, como se muestra en la configuración del ejemplo siguiente:  
  
```  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
     <!-- This endpoint is exposed at the base address provided by -->  
     <!-- host: http://localhost:8000/ServiceModelSamples/service.-->  
     <endpoint address=""  
               binding="basicHttpBinding"  
               bindingConfiguration="Binding1"   
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>   …  
</system.serviceModel>  
```  
  
 La configuración de enlace establece el atributo `mode` de [\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) como `Message`y establece el atributo `clientCredentialType` de [\<message\>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md) como `Certificate` tal y como se muestra en la siguiente configuración de ejemplo:  
  
```  
<bindings>  
  <basicHttpBinding>  
    <!--   
        This configuration defines the SecurityMode as Message and   
        the clientCredentialType as Certificate.  
        -->  
    <binding name="Binding1" >  
      <security mode = "Message">  
        <message clientCredentialType="Certificate"/>  
      </security>  
    </binding>  
  </basicHttpBinding>  
</bindings>  
```  
  
 El certificado que el servicio utiliza para autenticarse al cliente se establece en la sección de comportamientos del archivo de configuración bajo el elemento `serviceCredentials`.El modo de la validación que se aplica al certificado que el cliente utiliza para autenticarse al servicio también se establece en la sección de comportamientos bajo el elemento `clientCertificate`.  
  
```  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
      <!--The serviceCredentials behavior allows one to define a -->  
      <!--service certificate. A service certificate is used by a -->  
      <!--client to authenticate the service and provide message -->  
      <!-- protection. This configuration references the "localhost"-->  
      <!--certificate installed during the setup instructions. -->  
      <serviceCredentials>  
        <serviceCertificate findValue="localhost"  
               storeLocation="LocalMachine"   
               storeName="My" x509FindType="FindBySubjectName" />  
        <clientCertificate>  
          <!-- Setting the certificateValidationMode to -->  
          <!-- PeerOrChainTrust means that if the certificate -->  
          <!--is in the user's Trusted People store, then it is -->  
          <!-- trusted without performing a validation of the -->  
          <!-- certificate's issuer chain. This setting is used -->  
          <!-- here for convenience so that the sample can be run -->  
          <!-- without having to have certificates issued by a -->  
          <!-- certification authority (CA). -->  
          <!-- This setting is less secure than the default, -->  
          <!-- ChainTrust. The security implications of this -->  
          <!-- setting should be carefully considered before using -->  
          <!-- PeerOrChainTrust in production code. -->  
          <authentication   
                       certificateValidationMode="PeerOrChainTrust" />  
        </clientCertificate>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 El mismo enlace y detalles de seguridad se especifican en el archivo de configuración del cliente.  
  
 La identidad del llamador se muestra en la ventana de la consola del servicio utilizando el código siguiente:  
  
```  
Console.WriteLine("Called by {0}", ServiceSecurityContext.Current.PrimaryIdentity.Name);  
```  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
### Para configurar y compilar el ejemplo  
  
1.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
### Para ejecutar el ejemplo en el mismo equipo  
  
1.  Ejecute Setup.bat desde la carpeta de instalación del ejemplo.Esto instala todos los certificados requeridos para ejecutar el ejemplo.  
  
    > [!NOTE]
    >  El archivo por lotes Setup.bat está diseñado para ejecutarse desde el símbolo del sistema de Windows SDK.Requiere que la variable de entorno de MSSDK se dirija al directorio donde está instalado el SDK.Esta variable de entorno se establece automáticamente dentro de un símbolo del sistema de Windows SDK.  
  
2.  Ejecute la aplicación de servicio desde \\service\\bin.  
  
3.  Ejecute la aplicación cliente desde \\client\\bin.La actividad del cliente se muestra en la aplicación de consola del cliente.  
  
4.  Si el cliente y el servicio no se pueden comunicar, vea [Troubleshooting Tips](http://msdn.microsoft.com/es-es/8787c877-5e96-42da-8214-fa737a38f10b).  
  
5.  Quite los certificados ejecutando Cleanup.bat cuando haya finalizado con el ejemplo.Otros ejemplos de seguridad usan los mismos certificados.  
  
### Para ejecutar el ejemplo en varios equipos  
  
1.  Cree un directorio en el equipo del servicio para los binarios del servicio.  
  
2.  Copie los archivos del programa de servicio en el directorio de servicio situado en el servidor.Copie también los archivos Setup.bat, Cleanup.bat e ImportClientCert.bat en el servidor.  
  
3.  Cree un directorio en el equipo cliente para los archivos binarios del cliente.  
  
4.  Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente.Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.  
  
5.  En el servidor, ejecute `setup.bat service`.Al ejecutar `setup.bat`  con el argumento `service` se crea un certificado del servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service.cer.  
  
6.  Edite el archivo service.exe.config para reflejar el nuevo nombre del certificado \(en el atributo `findValue` en el elemento [\<serviceCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)\), que es igual que el nombre de dominio completo del equipo.También cambie el valor de la dirección base para especificar un nombre de equipo completo en lugar de `.` del host local  
  
7.  Copie el archivo Service.cer del directorio de servicio del directorio del cliente al equipo cliente.  
  
8.  En el cliente, ejecute `setup.bat client`.Ejecutar `setup.bat` con el argumento `client` crea un certificado de cliente denominado client.com y exporta el certificado de cliente a un archivo denominado Client.cer.  
  
9. En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del extremo para que coincida con la nueva dirección de su servicio.Para hacerlo, reemplace el host local con el nombre de dominio completo del servidor.También cambie el atributo `findValue` de [\<defaultCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md) al nuevo nombre de certificado de servicio que es el nombre de dominio completo del servidor.  
  
10. Copie el archivo Client.cer del directorio del cliente en el directorio del servicio en el servidor.  
  
11. En el cliente, ejecute ImportServiceCert.bat.Esto importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser \- TrustedPeople.  
  
12. En el servidor, ejecute ImportClientCert.bat. Esto importa el certificado de cliente del archivo Client.cer en el almacén LocalMachine \- TrustedPeople.  
  
13. En el equipo del servicio, ejecute Service.exe desde el símbolo del sistema.  
  
14. En el equipo cliente, inicie Client.exe desde la ventana de símbolo del sistema.  
  
    1.  Si el cliente y el servicio no se pueden comunicar, vea [Troubleshooting Tips](http://msdn.microsoft.com/es-es/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### Para limpiar después del ejemplo  
  
-   Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.  
  
    > [!NOTE]
    >  Este script no quita los certificados del servicio en un cliente cuando se ejecuta este ejemplo en los equipos.Si ha ejecutado los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] que usan certificados en los equipos, asegúrese de borrar los certificados de servicio que se hayan instalado en el almacén CurrentUser \- TrustedPeople.Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Binding\Basic\MessageSecurity`  
  
## Vea también