---
description: 'Más información sobre: <message> de <netMsmqBinding>'
title: <message> de <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 0e8cf641ef8ba5361318f7b658d5d60beef6ce56
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749589"
---
# <a name="message-of-netmsmqbinding"></a>\<message> de \<netMsmqBinding>

Define la configuración de seguridad del mensaje SOAP en este enlace `netMsmqBinding`.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  

## <a name="syntax"></a>Sintaxis

```xml
<netMsmqBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
    </security>
  </binding>
</netMsmqBinding>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|algorithmSuite|Establece el cifrado de mensajes y algoritmos de ajuste de clave que se utilizan para lograr la seguridad basada en mensaje para los mensajes enviados sobre transporte de MSMQ.<br /><br /> El valor predeterminado es `Aes256`. Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.|
|clientCredentialType|Especifica el tipo de credencial que se va a utilizar al realizar la autenticación del cliente para los mensajes enviados sobre el transporte de MSMQ. Los valores válidos incluyen los siguientes:<br /><br /> -None: Esto permite al servicio interactuar con clientes anónimos. Ni el servicio ni el cliente requieren una credencial.<br />-Windows: permite que los intercambios de SOAP estén en el contexto autenticado de una credencial de Windows. Esto siempre realiza una autenticación basada en Kerberos.<br />-UserName: permite al servicio exigir que el cliente se autentique con una credencial de nombre de usuario. La credencial en este caso debe especificarse con el `clientCredentials` comportamiento **precaución:**  Windows Communication Foundation (WCF) no admite el envío de un resumen de contraseña ni la derivación de claves mediante contraseña y el uso de tales claves para la seguridad de los mensajes. Por lo tanto, WCF impone que el intercambio esté protegido cuando se usen las credenciales UserName. Este modo requiere que el certificado del servicio se especifique en el lado del cliente mediante el comportamiento de `clientCredential` y `serviceCertificate`. <br /><br /> -Certificate: permite que el servicio requiera que el cliente se autentique mediante un certificado. Las credenciales del cliente en este caso tienen que especificarse mediante el comportamiento `clientCredentials`. La credencial del servicio en este caso necesita ser especificada utilizando el comportamiento `clientCredentials` especificando `serviceCertificate`.<br />-CardSpace: permite que el servicio requiera que el cliente se autentique mediante un CardSpace. Se debe proporcionar `serviceCertificate` en el comportamiento `clientCredential`.<br /><br /> El valor predeterminado es `Windows`. Este atributo es del tipo <xref:System.ServiceModel.MessageCredentialType>.|

### <a name="child-elements"></a>Elementos secundarios

None

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|[\<security>](security-of-netmsmqbinding.md)|Define la configuración de seguridad de un enlace.|

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [Colas en WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
