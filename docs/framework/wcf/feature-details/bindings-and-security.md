---
title: Enlaces y seguridad
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], security
- WCF security
- Windows Communication Foundation, security
- bindings [WCF]
ms.assetid: 4de03dd3-968a-4e65-af43-516e903d7f95
ms.openlocfilehash: 63d3888df364d033b17972a5fd3ba3b851e00c42
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964437"
---
# <a name="bindings-and-security"></a>Enlaces y seguridad

Los enlaces proporcionados por el sistema que se incluyen con Windows Communication Foundation (WCF) ofrecen una forma rápida de programar aplicaciones WCF. Con una excepción, todos los enlaces tienen un esquema de seguridad predeterminado habilitó. Este tema le ayuda a seleccionar el enlace adecuado a sus necesidades de seguridad.

Para obtener información general sobre la seguridad de WCF, consulte [información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md). Para obtener más información acerca de la programación de WCF mediante enlaces, consulte [Programming WCF Security](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md).

Si ya ha seleccionado un enlace, puede encontrar más información sobre los comportamientos en tiempo de ejecución que están asociados a la seguridad en los [comportamientos de seguridad](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md).

Algunas funciones de seguridad no son programables mediante los enlaces proporcionados por el sistema. Para obtener más control sobre el uso de un enlace personalizado, vea [capacidades de seguridad con enlaces personalizados](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md).

## <a name="security-functions-of-bindings"></a>Funciones de seguridad de los enlaces

WCF incluye varios enlaces proporcionados por el sistema que satisfacen la mayoría de las necesidades. Si a un enlace determinado no le basta, también puede crear un enlace personalizado. Para obtener una lista de los enlaces proporcionados por el sistema, consulte [enlaces proporcionados por el sistema](../../../../docs/framework/wcf/system-provided-bindings.md). Para obtener más información sobre los enlaces personalizados, vea [enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md).

Cada enlace de WCF tiene dos formas: como una API y como un elemento XML que se usa en un archivo de configuración. Por ejemplo, el `WSHttpBinding` (API) tiene un homólogo en el [> de\<wsHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).

La siguiente sección hace una lista de ambas formas para cada enlace y resume las características de seguridad.

### <a name="basichttp"></a>BasicHttp

En el código, utilice la clase <xref:System.ServiceModel.BasicHttpBinding>; en configuración, use el [\<basicHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).

Este enlace está diseñado para su uso con un rango de tecnologías existentes, incluyendo las siguientes:

- Servicios Web ASP.NET (ASMX), versión 1.

- Aplicaciones de mejoras de servicios Web (WSE).

- Perfil básico tal y como se define en la especificación de interoperabilidad de servicios web (WS-I) (<https://go.microsoft.com/fwlink/?LinkId=38955>).

- Perfil de seguridad básico tal y como se define en WS-I.

De forma predeterminada, este enlace no es seguro. Está diseñado para interoperar con servicios ASMX. Cuando la seguridad está habilitada, el enlace está diseñado para ofrecer una interoperación perfecta con los mecanismos de seguridad de Internet Information Services (IIS), como la autenticación básica, el resumen y la seguridad integrada de Windows. Para obtener más información, vea [información general sobre la seguridad de transporte](../../../../docs/framework/wcf/feature-details/transport-security-overview.md). Este enlace admite lo siguiente:

- Seguridad de transporte de HTTPS.

- Autenticación básica HTTP

- WS-Security.

Para obtener más información, consulte <xref:System.ServiceModel.BasicHttpSecurity>, <xref:System.ServiceModel.BasicHttpMessageSecurity>, <xref:System.ServiceModel.BasicHttpMessageCredentialType> y <xref:System.ServiceModel.BasicHttpSecurityMode>.

### <a name="wshttpbinding"></a>WSHttpBinding

En el código, utilice la clase <xref:System.ServiceModel.WSHttpBinding>; en configuración, use el [\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).

De forma predeterminada, este enlace implementa la especificación WS-Security y proporciona interoperabilidad con servicios que implementan las especificaciones WS - *. Admite lo siguiente:

- Seguridad de transporte de HTTPS.

- WS-Security.

- Protección de transportes HTTPS con seguridad de credenciales de mensajes SOAP para autenticar al llamador.

Para obtener más información, vea <xref:System.ServiceModel.WSHttpSecurity>, <xref:System.ServiceModel.MessageSecurityOverHttp>, <xref:System.ServiceModel.MessageCredentialType>, <xref:System.ServiceModel.SecurityMode>, <xref:System.ServiceModel.HttpTransportSecurity>, <xref:System.ServiceModel.HttpClientCredentialType>y <xref:System.ServiceModel.HttpProxyCredentialType>.

### <a name="wsdualhttpbinding"></a>WSDualHttpBinding

En el código, utilice la clase <xref:System.ServiceModel.WSDualHttpBinding>; en configuración, use el [\<wsDualHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).

Este enlace está diseñado para habilitar las aplicaciones de servicio dúplex. Este enlace implementa la especificación WS-Security para la seguridad de transferencia basada en mensajes. La seguridad de transporte no está disponible. De forma predeterminada, proporciona las características siguientes:

- Implementa mensajería con WS-Reliable para proporcionar fiabilidad.

- Implementa WS-Security para la autenticación y la seguridad de la transferencia.

- Utiliza HTTP para la entrega de mensajes.

- Utiliza codificación de mensajes de texto/XML.

 Mediante el uso de WS-Security (seguridad de capa del mensaje), el enlace le permite configurar los parámetros siguientes:

- El conjunto de algoritmos de seguridad para determinar el algoritmo criptográfico.

- Opciones de enlaces para lo siguiente:

  - Proporcionar credenciales de servicio disponibles fuera de banda en el cliente.

  - Proporcionar credenciales de servicio negociadas desde el servicio como parte de la configuración del canal.

Para obtener más información, vea <xref:System.ServiceModel.WSDualHttpSecurity> y <xref:System.ServiceModel.WSDualHttpSecurityMode>.

### <a name="nettcpbinding"></a>NetTcpBinding

En el código, utilice la clase <xref:System.ServiceModel.NetTcpBinding>; en configuración, use el [\<netTcpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).

Este enlace se optimiza para la comunicación entre equipos. De manera predeterminada, tiene las siguientes características:

- Implementa la seguridad de nivel de transporte.

- Reutiliza la seguridad de Windows para la autenticación y seguridad de la transferencia.

- Utiliza TCP para el transporte.

- Implementa la codificación de mensajes binarios.

- Implementa mensajería WS-Reliable.

Las opciones incluyen:

- Capa de seguridad de mensajes (mediante WS-Security).

- Seguridad de transporte con credencial de mensaje; confidencialidad e integridad proporcionadas por la seguridad del nivel de transporte (TLS) sobre TCP, y credenciales para la autorización proporcionada por WS-Security.

Para obtener más información, vea <xref:System.ServiceModel.NetTcpSecurity>, <xref:System.ServiceModel.TcpTransportSecurity>, <xref:System.ServiceModel.TcpClientCredentialType>, <xref:System.ServiceModel.MessageSecurityOverTcp>y <xref:System.ServiceModel.MessageCredentialType>.

### <a name="netnamedpipebinding"></a>NetNamedPipeBinding

En el código, utilice la clase <xref:System.ServiceModel.NetNamedPipeBinding>; en configuración, use el [\<netNamedPipeBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).

Este enlace se optimiza para la comunicación entre procesos (normalmente en el mismo equipo). De forma predeterminada, este enlace tiene las características siguientes:

- Utiliza la seguridad de transporte para la transferencia y autenticación de mensajes.

- Utiliza canalizaciones con nombre para la entrega de mensajes.

- Implementa la codificación de mensajes binarios.

- Cifrado y firmado de mensajes.

Las opciones incluyen:

- Autenticación utilizando la seguridad de Windows.

Para obtener más información, vea <xref:System.ServiceModel.NetNamedPipeSecurity>, <xref:System.ServiceModel.NetNamedPipeSecurityMode> y <xref:System.ServiceModel.NamedPipeTransportSecurity>.

### <a name="msmqintegrationbinding"></a>MsmqIntegrationBinding

En el código, utilice la clase <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>; en configuración, use el [\<msmqIntegrationBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).

Este enlace está optimizado para crear clientes y servicios de WCF que interoperan con puntos de conexión de Microsoft Message Queuing (MSMQ) que no son de WCF.

De forma predeterminada, este enlace utiliza la seguridad de transporte y proporciona las siguientes características de seguridad:

- La seguridad se puede deshabilitar (Ninguno).

- Seguridad de transporte de MSMQ (Transporte).

Para obtener más información, vea <xref:System.ServiceModel.NetMsmqSecurity> y <xref:System.ServiceModel.NetMsmqSecurityMode>.

### <a name="netmsmqbinding"></a>NetMsmqBinding

En el código, utilice la clase <xref:System.ServiceModel.NetMsmqBinding>; en configuración, use el [\<netMsmqBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md).

Este enlace está diseñado para usarse al crear servicios WCF que requieren compatibilidad con mensajes en cola de MSMQ.

De forma predeterminada, este enlace utiliza la seguridad de transporte y proporciona las siguientes características de seguridad:

- La seguridad se puede deshabilitar (Ninguno).

- Seguridad de transporte de MSMQ (Transporte).

- Seguridad de mensajes basados en SOAP (Mensaje)

- Transporte y seguridad de mensajes simultáneos (Ambos).

- Tipos de credenciales de cliente admitidos: None (ninguno), Windows, UserName (nombre de usuario), Certificate (certificado), IssuedToken (token emitido).

Se admite la credencial <xref:System.ServiceModel.MessageCredentialType.Certificate> solo cuando el modo de seguridad está establecido en <xref:System.ServiceModel.NetMsmqSecurityMode.Both> o <xref:System.ServiceModel.NetMsmqSecurityMode.Message>.

Para obtener más información, vea <xref:System.ServiceModel.MessageSecurityOverMsmq> y <xref:System.ServiceModel.MsmqTransportSecurity>.

### <a name="wsfederationhttpbinding"></a>WSFederationHttpBinding

En el código, utilice la clase <xref:System.ServiceModel.WSFederationHttpBinding>; en configuración, use el [\<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).

De forma predeterminada, este enlace utiliza WS-Security (seguridad de nivel de mensaje).

Para obtener más información, vea [Federación](../../../../docs/framework/wcf/feature-details/federation.md), <xref:System.ServiceModel.WSFederationHttpSecurity>y <xref:System.ServiceModel.WSFederationHttpSecurityMode>.

## <a name="custom-bindings"></a>Enlaces personalizados

Si ninguno de los enlaces proporcionados por el sistema cumple sus requisitos, puede crear un enlace personalizado con un elemento de enlace de seguridad personalizado. Para obtener más información, consulte [capacidades de seguridad con enlaces personalizados](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md).

## <a name="binding-choices"></a>Opciones de enlaces

La tabla siguiente resume las características proporcionadas en la configuración del modo de seguridad, es decir, hace una lista de las características disponibles cuando el modo de seguridad se establece en `Transport`, `Message`o `TransportWithMessageCredential`. Utilice esta tabla para encontrar las características de seguridad que requiere su aplicación.

|Configuración de|Características|
|-------------|--------------|
|Transport|Autenticación del servidor<br /><br /> Autenticación de cliente<br /><br /> Seguridad de punto a punto<br /><br /> Interoperabilidad<br /><br /> Aceleración de hardware<br /><br /> Rendimiento alto<br /><br /> Firewall seguro<br /><br /> Aplicaciones de la latencia alta<br /><br /> Recifrado en múltiples saltos|
|Mensaje|Autenticación del servidor<br /><br /> Autenticación de cliente<br /><br /> Seguridad de extremo a extremo<br /><br /> Interoperabilidad<br /><br /> Demandas altas<br /><br /> Federación<br /><br /> Autenticación de multifactor<br /><br /> Tokens personalizados<br /><br /> Servicio de notario/marca de tiempo<br /><br /> Aplicaciones de la latencia alta<br /><br /> Persistencia de firmas del mensaje|
|TransportWithMessageCredential|Autenticación del servidor<br /><br /> Autenticación de cliente<br /><br /> Seguridad de punto a punto<br /><br /> Interoperabilidad<br /><br /> Aceleración de hardware<br /><br /> Rendimiento alto<br /><br /> Demandas altas de cliente<br /><br /> Federación<br /><br /> Autenticación de multifactor<br /><br /> Tokens personalizados<br /><br /> Firewall seguro<br /><br /> Aplicaciones de la latencia alta<br /><br /> Recifrado en múltiples saltos|

La tabla siguiente hace una lista de los enlaces que admiten los diversos ajustes de modos. Seleccione un enlace en la tabla que va a utilizar para crear su punto de conexión de servicio.

|Enlace|Compatibilidad del modo de transporte|Compatibilidad del modo de mensaje|Compatibilidad con TransportWithMessageCredential|
|-------------|----------------------------|--------------------------|--------------------------------------------|
|`BasicHttpBinding`|Sí|Sí|Sí|
|`WSHttpBinding`|Sí|Sí|Sí|
|`WSDualHttpBinding`|No|Sí|No|
|`NetTcpBinding`|Sí|Sí|Sí|
|`NetNamedPipeBinding`|Sí|No|No|
|`NetMsmqBinding`|Sí|Sí|No|
|`MsmqIntegrationBinding`|Sí|No|No|
|`wsFederationHttpBinding`|No|Sí|Sí|

## <a name="transport-credentials-in-bindings"></a>Credenciales de transporte en los enlaces

La tabla siguiente enumera los tipos de credenciales de cliente disponibles al utilizar `BasicHttpBinding` o `WSHttpBinding` en modo de seguridad de transporte.

|Tipo de|Descripción|
|----------|-----------------|
|Ninguno|Especifica que el cliente no necesita presentar ningún credencial. Realiza una conversión a un cliente anónimo.|
|Basic|Autenticación básica. Para obtener más información, vea RFC 2617: autenticación HTTP: autenticación básica e implícita, disponible en <https://go.microsoft.com/fwlink/?LinkId=84023>.|
|Digest|autenticación implícita. Para obtener más información, vea RFC 2617: autenticación HTTP: autenticación básica e implícita, disponible en <https://go.microsoft.com/fwlink/?LinkId=84023>.|
|NTLM|Autenticación NT LAN Manager (NTLM).|
|Portal|Autenticación de Windows.|
|Certificado|Autenticación realizada utilizando un certificado.|
|IssuedToken|Permite al servicio exigir que el cliente se autentique mediante un token emitido por un servicio de token de seguridad o por CardSpace. Para obtener más información, vea [Federación y tokens emitidos](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).|

### <a name="message-client-credentials-in-bindings"></a>Credenciales de cliente de mensaje en enlaces

La tabla siguiente enumera los tipos de credenciales de cliente disponibles al utilizar un enlace en el modo de seguridad de mensajes.

|Tipo de|Descripción|
|----------|-----------------|
|Ninguno|Permite al servicio interactuar con clientes anónimos.|
|Portal|Permite a los intercambios de mensajes SOAP realizarse bajo el contexto autenticado de una credencial de Windows.|
|UserName|Permite que el servicio requiera que el cliente se autentique con una credencial del nombre de usuario. Tenga en cuenta que cuando el modo de seguridad se establece en `TransportWithMessageCredential`, WCF no admite el envío de un resumen de contraseña ni la derivación de claves mediante la contraseña y el uso de estas claves para la seguridad del modo de mensaje. Como tal, WCF exige que el transporte esté protegido cuando se usen credenciales de nombre de usuario.|
|Certificado|Permite al servicio exigir la autenticación del cliente mediante un certificado.|
|IssuedToken|Permite al servicio utilizar un servicio de token de seguridad para proporcionar un token personalizado.|

## <a name="see-also"></a>Vea también

- [Información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Selección de tipos de credenciales](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [Funcionalidades de seguridad con enlaces personalizados](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [Comportamientos de seguridad](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Modelo de seguridad para Windows Server App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
