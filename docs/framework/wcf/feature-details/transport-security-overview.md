---
title: Información general de la seguridad del transporte
description: Obtenga información sobre los principales mecanismos de seguridad de transporte en los enlaces proporcionados por el sistema WCF. Estos mecanismos de seguridad dependen del enlace y el transporte utilizados.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 00959326-aa9d-44d0-af61-54933d4adc7f
ms.openlocfilehash: 8780b9c0fc06a49ddaf42166c292a41e9124f6e1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556803"
---
# <a name="transport-security-overview"></a>Información general de la seguridad del transporte
Los mecanismos de seguridad de transporte en Windows Communication Foundation (WCF) dependen del enlace y el transporte que se utiliza. Por ejemplo, al utilizar la clase <xref:System.ServiceModel.WSHttpBinding>, el transporte es HTTP y el mecanismo principal para garantizar el transporte es Capa de sockets seguros (SSL) sobre HTTP, normalmente denominado HTTPS. En este tema se describen los principales mecanismos de seguridad de transporte utilizados en los enlaces proporcionados por el sistema WCF.  
  
> [!NOTE]
> Cuando se usa la seguridad SSL con .NET Framework 3,5 y versiones posteriores, un cliente WCF usa ambos certificados intermedios en su almacén de certificados y los certificados intermedios recibidos durante la negociación SSL para realizar la validación de la cadena de certificados en el certificado del servicio. .NET Framework 3.0 solo usa los certificados intermedios instalados en el almacén de certificados local.  
  
> [!WARNING]
> Cuando se utiliza la seguridad de transporte, puede sobrescribirse la propiedad <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType>. Para evitar que esto suceda, establezca <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.Description.PrincipalPermissionMode.None?displayProperty=nameWithType> . <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> es un comportamiento de servicio que se puede establecer en la descripción del servicio.  
  
## <a name="basichttpbinding"></a>BasicHttpBinding  
 De manera predeterminada, la clase <xref:System.ServiceModel.BasicHttpBinding> no proporciona seguridad. Este enlace está diseñado para la interoperabilidad con proveedores de servicios Web que no implementan seguridad. Sin embargo, puede activar la seguridad definiendo la propiedad <xref:System.ServiceModel.BasicHttpSecurity.Mode%2A> en cualquier valor excepto <xref:System.ServiceModel.BasicHttpSecurityMode.None>. Para habilitar la seguridad del transporte, defina la propiedad en <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.  
  
### <a name="interoperation-with-iis"></a>Interoperación con IIS  
 La clase <xref:System.ServiceModel.BasicHttpBinding> se utiliza principalmente para interoperar con los servicios Web existentes e Internet Information Services (IIS) hospeda muchos de esos servicios. Por consiguiente, la seguridad en el transporte para este enlace está diseñada para la interoperación perfecta con sitios de IIS. Esto se realiza definiendo el modo de seguridad en <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> y estableciendo a continuación el tipo de credencial del cliente. Los valores del tipo de la credencial se corresponden con los mecanismos de seguridad del directorio de IIS. El código siguiente muestra el modo que se ha establecido y el tipo de credencial definido en Windows. Puede utilizar esta configuración cuando el cliente y el servidor están en el mismo dominio de Windows.  
  
 [!code-csharp[c_ProgrammingSecurity#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#10)]
 [!code-vb[c_ProgrammingSecurity#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#10)]  
  
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
  
#### <a name="basic"></a>Básico  
 Se corresponde con el método de autenticación básico de IIS. Cuando se utiliza este modo, el servidor IIS debe configurarse con cuentas de usuario de Windows y permisos de sistema de archivos NTFS adecuados. Para obtener más información acerca de IIS 6,0, vea [Habilitar la autenticación básica y configurar el nombre de dominio Kerberos](/previous-versions/windows/it-pro/windows-server-2003/cc785293(v=ws.10)). Para obtener más información acerca de IIS 7,0, consulte [configurar la autenticación básica (IIS 7)](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772009(v=ws.10)).  
  
#### <a name="certificate"></a>Certificado  
 IIS tiene una opción para exigir a los clientes que inicien sesión con un certificado. La característica también le permite a IIS asignar un certificado de cliente a una cuenta de Windows. Para obtener más información acerca de IIS 6,0, vea [Habilitar certificados de cliente en iis 6,0](/previous-versions/windows/it-pro/windows-server-2003/cc727994(v=ws.10)). Para obtener más información acerca de IIS 7,0, vea [configurar certificados de servidor en IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732230(v=ws.10)).  
  
#### <a name="digest"></a>Digest  
 La autenticación implícita es similar a la autenticación básica, pero proporciona la ventaja de enviar las credenciales como un hash, en lugar de como texto no cifrado. Para obtener más información acerca de IIS 6,0, vea [autenticación implícita en iis 6,0](/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)). Para obtener más información acerca de IIS 7,0, vea [configurar la autenticación implícita (IIS 7)](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc754104(v=ws.10)).  
  
#### <a name="windows"></a>Windows  
 Esto se corresponde a la autenticación integrada de Windows en IIS. Cuando se establece en este valor, también se espera que el servidor exista en un dominio de Windows que utiliza el protocolo Kerberos como su controlador de dominio. Si el servidor no está en un dominio respaldado por Kerberos, o si se producen errores en el sistema Kerberos, puede utilizar el valor de NT LAN Manager (NTLM) descrito en la sección siguiente. Para obtener más información acerca de IIS 6,0, vea [autenticación integrada de Windows en iis 6,0](/previous-versions/windows/it-pro/windows-server-2003/cc738016(v=ws.10)). Para obtener más información acerca de IIS 7,0, vea [configurar certificados de servidor en IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732230(v=ws.10)).
  
#### <a name="ntlm"></a>NTLM  
 Esto permite al servidor usar NTLM para la autenticación si se produce un error en el protocolo Kerberos. Para obtener más información sobre la configuración de IIS en IIS 6,0, vea [forzar la autenticación NTLM](/previous-versions/windows/it-pro/windows-server-2003/cc786486(v=ws.10)). Para IIS 7,0, la autenticación de Windows incluye la autenticación NTLM. Para obtener más información, vea [Configurar certificados de servidor en IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732230(v=ws.10)).
  
## <a name="wshttpbinding"></a>WsHttpBinding  
 La clase <xref:System.ServiceModel.WSHttpBinding> está diseñada para la interoperación con servicios que implementan las especificaciones de WS-*. La seguridad de transporte para este enlace es Capa de sockets seguros (SSL) sobre HTTP o HTTPS. Para crear una aplicación WCF que utilice SSL, use IIS para hospedar la aplicación. Alternativamente, si está creando una aplicación autohospedada, utilice la herramienta HttpCfg.exe para enlazar un certificado X.509 con un puerto concreto en un equipo. El número de puerto se especifica como parte de la aplicación WCF como una dirección de extremo. Al utilizar el modo de transporte, la dirección del extremo debe incluir el protocolo HTTPS o se producirá una excepción en el tiempo de ejecución. Para obtener más información, vea [seguridad de transporte http](http-transport-security.md).  
  
 En el caso de la autenticación del cliente, defina la propiedad <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> de la clase <xref:System.ServiceModel.HttpTransportSecurity> en uno de los valores de enumeración de <xref:System.ServiceModel.HttpClientCredentialType>. Los valores de enumeración son idénticos a los tipos de credencial de cliente para <xref:System.ServiceModel.BasicHttpBinding> y están diseñados para que se hospeden con servicios de IIS.  
  
 El ejemplo siguiente muestra el enlace que se va a usar con un tipo de credencial de cliente de Windows.  
  
 [!code-csharp[c_ProgrammingSecurity#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#11)]
 [!code-vb[c_ProgrammingSecurity#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#11)]  
  
## <a name="wsdualhttpbinding"></a>WSDualHttpBinding  
 Este enlace solo proporciona seguridad en el nivel de mensaje pero no seguridad en el nivel de transporte.  
  
## <a name="nettcpbinding"></a>NetTcpBinding  
 La clase <xref:System.ServiceModel.NetTcpBinding> usa TCP para el transporte del mensaje. Se proporciona seguridad para el modo de transporte al implementar Seguridad de la capa de transporte (TLS) sobre TCP. El sistema operativo proporciona la implementación de TLS.  
  
 También puede especificar el tipo de credencial del cliente estableciendo la propiedad <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> de la clase <xref:System.ServiceModel.TcpTransportSecurity> en uno de los valores de la enumeración <xref:System.ServiceModel.TcpClientCredentialType>, tal y como se muestra en el código siguiente.  
  
 [!code-csharp[c_ProgrammingSecurity#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#12)]
 [!code-vb[c_ProgrammingSecurity#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#12)]  
  
#### <a name="client"></a>Cliente  
 En el cliente, debe especificar un certificado mediante el método <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> de la clase <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.  
  
> [!NOTE]
> Si está utilizando la seguridad de Windows, no se requiere un certificado.  
  
 El código siguiente usa la huella digital del certificado, que lo identifica de forma única. Para más información, consulte [Trabajar con certificados](working-with-certificates.md).  
  
 [!code-csharp[c_ProgrammingSecurity#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#13)]
 [!code-vb[c_ProgrammingSecurity#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#13)]  
  
 Como alternativa, especifique el certificado en la configuración del cliente mediante un [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) elemento en la sección de comportamientos.  
  
```xml  
<behaviors>  
  <behavior>  
   <clientCredentials>  
     <clientCertificate findValue= "101010101010101010101010101010000000000"
      storeLocation="LocalMachine" storeName="My"
      X509FindType="FindByThumbPrint">  
     </clientCertificate>  
   </clientCredentials>  
 </behavior>  
</behaviors>
```  
  
## <a name="netnamedpipebinding"></a>NetNamedPipeBinding  
 La clase <xref:System.ServiceModel.NetNamedPipeBinding> está diseñada para la comunicación eficaz dentro de la máquina. Es decir, para los procesos que se ejecuten en el mismo equipo, aunque los canales de canalización con nombre se puedan crear entre dos equipos de la misma red. Este enlace solo proporciona la seguridad de nivel de transporte. Al crear aplicaciones mediante este enlace, las direcciones del punto de conexión deben incluir "net.pipe" como protocolo de la dirección del punto de conexión.  
  
## <a name="wsfederationhttpbinding"></a>WSFederationHttpBinding  
 Cuando se usa seguridad de transporte, este enlace usa SSL sobre HTTP, lo que se conoce como HTTPS con un token emitido (<xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential>). Para obtener más información sobre las aplicaciones de Federación, vea [Federación y tokens emitidos](federation-and-issued-tokens.md).  
  
## <a name="netpeertcpbinding"></a>NetPeerTcpBinding  
 La clase <xref:System.ServiceModel.NetPeerTcpBinding> es un transporte seguro que está diseñado para la comunicación eficaz utilizando la característica de conexión de red de punto a punto. Tal y como indica el nombre de la clase y el enlace, TCP es el protocolo. Cuando el modo de seguridad se establece en Transporte, el enlace implementa TLS sobre TCP. Para obtener más información sobre la característica punto a punto, vea [redes punto a punto](peer-to-peer-networking.md).  
  
## <a name="msmqintegrationbinding-and-netmsmqbinding"></a>MsmqIntegrationBinding y NetMsmqBinding  
 Para obtener información completa sobre la seguridad de transporte con Message Queue Server (anteriormente denominado MSMQ), consulte [protección de mensajes mediante la seguridad de transporte](securing-messages-using-transport-security.md).  
  
## <a name="see-also"></a>Vea también

- [Programación de la seguridad de WCF](programming-wcf-security.md)
