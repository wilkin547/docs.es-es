---
title: Programación de la seguridad de WCF
description: Obtenga información sobre cómo crear una aplicación WCF segura, incluida la autenticación, la confidencialidad y la integridad.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message security [WCF], programming overview
ms.assetid: 739ec222-4eda-4cc9-a470-67e64a7a3f10
ms.openlocfilehash: 4ffbf6a05abd3ed9ebcea4b2e85f0dc305a4f2db
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244774"
---
# <a name="programming-wcf-security"></a>Programación de la seguridad de WCF

En este tema se describen las tareas de programación fundamentales que se usan para crear una aplicación Secure Windows Communication Foundation (WCF). En este tema solo se trata la autenticación, la confidencialidad y la integridad, que se conocen colectivamente como *seguridad de transferencia*. En este tema no se trata la autorización (el control de acceso a los recursos o servicios). para obtener información sobre la autorización, vea [autorización](authorization-in-wcf.md).  
  
> [!NOTE]
> Para obtener una introducción valiosa a los conceptos de seguridad, especialmente en relación con WCF, vea el conjunto de tutoriales de patrones y prácticas de MSDN en [escenarios, patrones e instrucciones de implementación para Web Services Enhancements (WSE) 3,0](/previous-versions/msp-n-p/ff648183(v=pandp.10)).  
  
 La programación de la seguridad de WCF se basa en tres pasos que establecen lo siguiente: el modo de seguridad, un tipo de credencial de cliente y los valores de credenciales. Puede realizar estos pasos mediante código o configuración.  
  
## <a name="setting-the-security-mode"></a>Establecimiento del modo de seguridad  

 A continuación se explican los pasos generales para programar con el modo de seguridad en WCF:  
  
1. Seleccione uno de los enlaces predefinidos adecuado a sus requisitos de aplicación. Para obtener una lista de las opciones de enlace, vea [enlaces proporcionados](../system-provided-bindings.md)por el sistema. De forma predeterminada, prácticamente todos los enlaces tienen la seguridad habilitada. La única excepción es la <xref:System.ServiceModel.BasicHttpBinding> clase (mediante la configuración, [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) ).  
  
     El enlace que seleccione determina el transporte. Por ejemplo, <xref:System.ServiceModel.WSHttpBinding> utiliza HTTP como el transporte; <xref:System.ServiceModel.NetTcpBinding> utiliza TCP.  
  
2. Seleccione uno de los modos de seguridad para el enlace. Tenga en cuenta que el enlace que seleccione determinará las opciones de modo disponibles. Por ejemplo, <xref:System.ServiceModel.WSDualHttpBinding> no permite la seguridad de transporte (no es una opción). De igual forma, ni <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> ni <xref:System.ServiceModel.NetNamedPipeBinding> permiten el modo de seguridad.  
  
     Dispone de tres opciones:  
  
    1. `Transport`  
  
         La seguridad de transporte depende del mecanismo que use el enlace que ha seleccionado. Por ejemplo, si utiliza `WSHttpBinding`, el mecanismo de seguridad es Secure Sockets Layer (SSL) (también es el mecanismo para el protocolo HTTPS). Generalmente hablando, la principal ventaja de la seguridad de transporte es que proporciona un buen rendimiento independientemente del transporte que esté utilizando. No obstante, tiene dos limitaciones: la primera es que el mecanismo de transporte dicta el tipo de credencial utilizado para autenticar a un usuario. Ésta es una desventaja solo si un servicio necesita interoperar con otros servicios que exigen tipos diferentes de credenciales. La segunda es que, puesto que la seguridad no se aplica en el nivel de mensaje, la seguridad se implementa salto por salto en lugar de de extremo a extremo. Esta última limitación es un problema solo si la ruta de mensajes entre el cliente y el servicio incluye intermediarios. Para obtener más información acerca del transporte que se va a usar, consulte [elección de un transporte](choosing-a-transport.md). Para obtener más información sobre el uso de la seguridad de transporte, vea [información general](transport-security-overview.md)sobre la seguridad de transporte.  
  
    2. `Message`  
  
         El modo de seguridad significa que cada mensaje incluye los encabezados y datos necesarios para mantener el mensaje protegido. Dado que la composición de los encabezados varía, puede incluir cualquier número de credenciales. Este es un factor a tener en cuenta si está interoperando con otros servicios que exigen un tipo de credencial concreto que un mecanismo de transporte no puede proporcionar o si el mensaje se debe utilizar con más de un servicio, donde cada servicio exige un tipo de credencial diferente.  
  
         Para obtener más información, vea [seguridad de mensajes](message-security-in-wcf.md).  
  
    3. `TransportWithMessageCredential`  
  
         Esta opción utiliza el nivel de transporte para proteger la transferencia del mensaje, mientras que cada mensaje incluye las credenciales enriquecidas que otros servicios necesitan. Esto combina la ventaja de rendimiento de la seguridad de transporte con la ventaja de las credenciales enriquecidas de la seguridad de mensaje. Esto está disponible con los siguientes enlaces: <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSFederationHttpBinding>, <xref:System.ServiceModel.NetPeerTcpBinding> y <xref:System.ServiceModel.WSHttpBinding>.  
  
3. Si decide utilizar la seguridad de transporte para HTTP (en otras palabras, HTTPS), debe configurar también el host con un certificado SSL y habilitar SSL en un puerto. Para obtener más información, vea [seguridad de transporte http](http-transport-security.md).  
  
4. Si está utilizando el <xref:System.ServiceModel.WSHttpBinding> y no necesita establecer una sesión segura, establezca la propiedad <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> en `false`.  
  
     Una sesión segura se produce cuando un cliente y servicio crean un canal mediante una clave simétrica (tanto el cliente como el servidor usan la misma clave durante la duración de una conversación, hasta que se cierre el diálogo).  
  
## <a name="setting-the-client-credential-type"></a>Establecimiento del tipo de credencial de cliente  

 Seleccione según corresponda un tipo de credencial de cliente. Para obtener más información, consulte [seleccionar un tipo de credencial](selecting-a-credential-type.md). Los siguientes tipos de credencial de cliente están disponibles:  
  
- `Windows`  
  
- `Certificate`  
  
- `Digest`  
  
- `Basic`  
  
- `UserName`  
  
- `NTLM`  
  
- `IssuedToken`  
  
 Dependiendo de cómo establezca el modo, deberá establecer el tipo de credencial. Por ejemplo, si ha seleccionado el `wsHttpBinding`, y ha establecido el modo en "Mensaje", también puede establecer el atributo `clientCredentialType` del elemento Message en uno de los valores siguientes: `None`, `Windows`, `UserName`, `Certificate` y `IssuedToken`, como se muestra en el ejemplo de configuración siguiente.  
  
```xml  
<system.serviceModel>  
<bindings>  
  <wsHttpBinding>  
    <binding name="myBinding">  
      <security mode="Message"/>  
      <message clientCredentialType="Windows"/>  
    </binding>
  </wsHttpBinding>
</bindings>  
</system.serviceModel>  
```  
  
 O bien, en el código:  
  
 [!code-csharp[c_WsHttpService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#1)]
 [!code-vb[c_WsHttpService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#1)]  
  
## <a name="setting-service-credential-values"></a>Establecimiento de valores de credenciales de servicio  

 Cuando selecciona un tipo de credencial de cliente, debe establecer las credenciales reales que el servicio y el cliente han de utilizar. En el servicio, las credenciales se establecen utilizando la clase <xref:System.ServiceModel.Description.ServiceCredentials> y se devuelven mediante la propiedad <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> de la clase <xref:System.ServiceModel.ServiceHostBase>. El enlace en uso implica el tipo de credencial de servicio, el modo de seguridad elegido y el tipo de la credencial de cliente. El código siguiente establece un certificado para una credencial de servicio.  
  
 [!code-csharp[c_tcpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#3)]
 [!code-vb[c_tcpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#3)]  
  
## <a name="setting-client-credential-values"></a>Establecimiento de los valores de credencial de cliente  

 En el cliente, establezca valores de credencial de cliente mediante la clase <xref:System.ServiceModel.Description.ClientCredentials> y devueltos por la propiedad <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> de la clase <xref:System.ServiceModel.ClientBase%601>. El código siguiente establece un certificado como una credencial en un cliente utilizando el protocolo TCP.  
  
 [!code-csharp[c_TcpClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpclient/cs/source.cs#1)]
 [!code-vb[c_TcpClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpclient/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Programación básica de WCF](../basic-wcf-programming.md)
- [Escenarios de seguridad comunes](common-security-scenarios.md)
