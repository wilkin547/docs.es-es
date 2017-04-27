---
title: "Informaci&#243;n general de la seguridad del transporte | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 00959326-aa9d-44d0-af61-54933d4adc7f
caps.latest.revision: 23
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 23
---
# Informaci&#243;n general de la seguridad del transporte
Los mecanismos de seguridad del transporte en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] dependen del enlace y el transporte que se estén usando. Por ejemplo, al usar el <xref:System.ServiceModel.WSHttpBinding> (clase), el transporte es HTTP y el mecanismo principal para proteger el transporte es capa de Sockets seguros (SSL) sobre HTTP, normalmente denominado HTTPS. En este tema se tratan los mecanismos de seguridad en el transporte principales utilizados en los enlaces proporcionados por el sistema [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
> [!NOTE]
>  Cuando se usa la seguridad SSL con .NET Framework 3.5 y versiones posteriores, un cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa los certificados intermedios de su almacén de certificados y los certificados intermedios recibidos durante la negociación SSL para realizar la validación de la cadena de certificados en el certificado del servicio. .NET Framework 3.0 solo usa los certificados intermedios instalados en el almacén de certificados local.  
  
> [!WARNING]
>  Cuando se utiliza la seguridad de transporte, el <xref:System.Treading.Thread.CurrentPrincipal%2A> propiedad puede sobrescribirse. Para evitar que esto ocurra, establezca la <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermission%2A> en None. <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> es un comportamiento de servicio que se puede establecer en la descripción del servicio.  
  
## <a name="basichttpbinding"></a>BasicHttpBinding  
 De forma predeterminada, el <xref:System.ServiceModel.BasicHttpBinding> clase no proporciona seguridad. Este enlace está diseñado para la interoperabilidad con proveedores de servicios Web que no implementan seguridad. Sin embargo, puede activar la seguridad estableciendo la <xref:System.ServiceModel.BasicHttpSecurity.Mode%2A> propiedad en cualquier valor excepto <xref:System.ServiceModel.BasicHttpSecurityMode>. Para habilitar la seguridad de transporte, establezca la propiedad en <xref:System.ServiceModel.BasicHttpSecurityMode>.  
  
### <a name="interoperation-with-iis"></a>Interoperación con IIS  
 El <xref:System.ServiceModel.BasicHttpBinding> clase se utiliza principalmente para interoperar con servicios Web existentes y muchos de esos servicios se hospedan los servicios de Internet Information Server (IIS). Por consiguiente, la seguridad en el transporte para este enlace está diseñada para la interoperación perfecta con sitios de IIS. Esto se hace estableciendo el modo de seguridad <xref:System.ServiceModel.BasicHttpSecurityMode> y estableciendo el tipo de credencial del cliente. Los valores del tipo de la credencial se corresponden con los mecanismos de seguridad del directorio de IIS. El código siguiente muestra el modo que se ha establecido y el tipo de credencial definido en Windows. Puede utilizar esta configuración cuando el cliente y el servidor están en el mismo dominio de Windows.  
  
 [!code-csharp[c_ProgrammingSecurity#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#10)]
 <!-- TODO: review snippet reference [!code-vb[c_ProgrammingSecurity#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#10)]  -->  
  
 O bien, en la configuración:  
  
```xml  
<bindings>  
  <basicHttpBinding>  
    <binding name="SecurityByTransport">  
      <security mode="Transport">  
        <transport clientCredentialType="Windows" />  
       </security>  
     </binding>  
  </basicHttpBinding>  
</bindings>  
```  
  
 Las secciones siguientes tratan otros tipos de credenciales de clientes.  
  
#### <a name="basic"></a>Basic  
 Se corresponde con el método de autenticación básico de IIS. Cuando se utiliza este modo, el servidor IIS debe configurarse con cuentas de usuario de Windows y permisos de sistema de archivos NTFS adecuados. [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iis601](../../../../includes/iis601-md.md)], consulte [habilitar la autenticación básica y configurar el nombre de dominio Kerberos](http://go.microsoft.com/fwlink/?LinkId=88592). [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iisver](../../../../includes/iisver-md.md)], consulte [IIS 7.0 Beta: configurar la autenticación básica](http://go.microsoft.com/fwlink/?LinkId=88593).  
  
#### <a name="certificate"></a>Certificado  
 IIS tiene una opción para exigir a los clientes que inicien sesión con un certificado. La característica también le permite a IIS asignar un certificado de cliente a una cuenta de Windows. [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iis601](../../../../includes/iis601-md.md)], consulte [Enabling Client Certificates in IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88594). [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iisver](../../../../includes/iisver-md.md)], consulte [IIS 7.0 Beta: configurar certificados de servidor en IIS 7.0](http://go.microsoft.com/fwlink/?LinkId=88595).  
  
#### <a name="digest"></a>Resumen  
 La autenticación implícita es similar a la autenticación básica, pero proporciona la ventaja de enviar las credenciales como un hash, en lugar de como texto no cifrado. [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iis601](../../../../includes/iis601-md.md)], consulte [la autenticación implícita en IIS 6.0](http://go.microsoft.com/fwlink/?LinkID=88443). [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iisver](../../../../includes/iisver-md.md)], consulte [IIS 7.0 Beta: configurar la autenticación implícita](http://go.microsoft.com/fwlink/?LinkId=88596).  
  
#### <a name="windows"></a>Windows  
 Esto se corresponde a la autenticación integrada de Windows en IIS. Cuando se establece en este valor, también se espera que el servidor exista en un dominio de Windows que utiliza el protocolo Kerberos como su controlador de dominio. Si el servidor no está en un dominio respaldado por Kerberos, o si se producen errores en el sistema Kerberos, puede utilizar el valor de NT LAN Manager (NTLM) descrito en la sección siguiente. [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iis601](../../../../includes/iis601-md.md)], consulte [la autenticación integrada de Windows en IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88597). [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iisver](../../../../includes/iisver-md.md)], consulte [IIS 7.0 Beta: configurar certificados de servidor en IIS 7.0](http://go.microsoft.com/fwlink/?LinkId=88595).  
  
#### <a name="ntlm"></a>NTLM  
 Esto permite al servidor usar NTLM para la autenticación si se produce un error en el protocolo Kerberos. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]configuración de IIS en [!INCLUDE[iis601](../../../../includes/iis601-md.md)], consulte [forzar la autenticación NTLM](http://go.microsoft.com/fwlink/?LinkId=88598). Para [!INCLUDE[iisver](../../../../includes/iisver-md.md)], la autenticación de Windows incluye la autenticación NTLM. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][IIS 7.0 Beta: configurar certificados de servidor en IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=88595).  
  
## <a name="wshttpbinding"></a>WsHttpBinding  
 El <xref:System.ServiceModel.WSHttpBinding> clase está diseñada para la interoperación con servicios que implementan WS-* especificaciones. La seguridad de transporte para este enlace es Capa de sockets seguros (SSL) sobre HTTP o HTTPS. Para crear una aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que utiliza SSL, utilice IIS para hospedar la aplicación. Alternativamente, si está creando una aplicación autohospedada, utilice la herramienta HttpCfg.exe para enlazar un certificado X.509 con un puerto concreto en un equipo. El número de puerto se especifica como parte de la aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] como una dirección del extremo. Al utilizar el modo de transporte, la dirección del punto de conexión debe incluir el protocolo HTTPS o se producirá una excepción en el tiempo de ejecución. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Seguridad de transporte HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
 Para la autenticación de cliente, establecer el <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> propiedad de la <xref:System.ServiceModel.HttpTransportSecurity> clase a uno de los <xref:System.ServiceModel.HttpClientCredentialType> valores de enumeración. Los valores de enumeración son idénticos a los tipos de credencial de cliente para <xref:System.ServiceModel.BasicHttpBinding> y están diseñados para que se hospeden con servicios IIS.  
  
 El ejemplo siguiente muestra el enlace que se va a usar con un tipo de credencial de cliente de Windows.  
  
 [!code-csharp[c_ProgrammingSecurity#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#11)]
 [!code-vb[c_ProgrammingSecurity#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#11)]  
  
## <a name="wsdualhttpbinding"></a>WSDualHttpBinding  
 Este enlace solo proporciona seguridad en el nivel de mensaje pero no seguridad en el nivel de transporte.  
  
## <a name="nettcpbinding"></a>NetTcpBinding  
 El <xref:System.ServiceModel.NetTcpBinding> clase usa TCP para el transporte de mensajes. Se proporciona seguridad para el modo de transporte al implementar Seguridad de la capa de transporte (TLS) sobre TCP. El sistema operativo proporciona la implementación de TLS.  
  
 También puede especificar el tipo de credencial del cliente estableciendo el <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> propiedad de la <xref:System.ServiceModel.TcpTransportSecurity> clase a uno de los <xref:System.ServiceModel.TcpClientCredentialType> valores, como se muestra en el código siguiente.  
  
 [!code-csharp[c_ProgrammingSecurity#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#12)]
 [!code-vb[c_ProgrammingSecurity#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#12)]  
  
#### <a name="client"></a>Cliente  
 En el cliente, debe especificar un certificado mediante el <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> método de la <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> clase.  
  
> [!NOTE]
>  Si está utilizando la seguridad de Windows, no se requiere un certificado.  
  
 El código siguiente usa la huella digital del certificado, que lo identifica de forma única. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]certificados, consulte [trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
 [!code-csharp[c_ProgrammingSecurity#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#13)]
 [!code-vb[c_ProgrammingSecurity#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#13)]  
  
 Como alternativa, especifique el certificado en la configuración del cliente mediante un [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento de la sección de comportamientos.  
  
```xml  
<behaviors>  
  <behavior>  
   <clientCredentials>  
     <clientCertificate findValue= "101010101010101010101010101010000000000"   
      storeLocation="LocalMachine" storeName="My"   
      X509FindType="FindByThumbPrint"/>  
     </clientCertificate>  
   </clientCredentials>  
 </behavior>  
</behaviors>    
```  
  
## <a name="netnamedpipebinding"></a>NetNamedPipeBinding  
 El <xref:System.ServiceModel.NetNamedPipeBinding> clase está diseñada para una comunicación eficaz dentro de la máquina; es decir, para los procesos se ejecutan en el mismo equipo, aunque los canales de canalización con nombre puede crearse entre dos equipos en la misma red. Este enlace solo proporciona la seguridad de nivel de transporte. Al crear aplicaciones mediante este enlace, las direcciones del extremo deben incluir "net.pipe" como protocolo de la dirección del extremo.  
  
## <a name="wsfederationhttpbinding"></a>WSFederationHttpBinding  
 Cuando se utiliza la seguridad de transporte, este enlace usa SSL sobre HTTP, conocido como HTTPS con un token emitido (<xref:System.ServiceModel.WSFederationHttpSecurityMode>). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]aplicaciones de federación, consulte [federación y Tokens emitidos](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
## <a name="netpeertcpbinding"></a>NetPeerTcpBinding  
 El <xref:System.ServiceModel.NetPeerTcpBinding> clase es un transporte seguro que está diseñado para la comunicación eficaz utilizando la característica de redes punto a punto. Tal y como indica el nombre de la clase y el enlace, TCP es el protocolo. Cuando el modo de seguridad se establece en Transporte, el enlace implementa TLS sobre TCP. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]la característica punto a punto, consulte [Peer-to-Peer Networking](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="msmqintegrationbinding-and-netmsmqbinding"></a>MsmqIntegrationBinding y NetMsmqBinding  
 Para obtener más información sobre el transporte de seguridad con Message Queue Server (anteriormente denominado MSMQ), consulte [protección de mensajes utilizando seguridad de transporte](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md).  
  
## <a name="see-also"></a>Vea también  
 [Programar la seguridad WCF](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)