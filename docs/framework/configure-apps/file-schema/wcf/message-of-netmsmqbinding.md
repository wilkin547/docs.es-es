---
title: <message> de <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: b163dcb08e9656e3bde9c7fbb71fa1c92c9957ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931515"
---
# <a name="message-of-netmsmqbinding"></a>\<> de mensajes \<de netMsmqBinding >

Define la configuración de seguridad del mensaje SOAP en este enlace `netMsmqBinding`.

```xml
<system.ServiceModel>
  <bindings>
    <netMsmqBinding>
      <binding>
        <security>
          <message>
```

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

|Atributo|DESCRIPCIÓN|
|---------------|-----------------|
|algorithmSuite|Establece el cifrado de mensajes y algoritmos de ajuste de clave que se utilizan para lograr la seguridad basada en mensaje para los mensajes enviados sobre transporte de MSMQ.<br /><br /> El valor predeterminado es `Aes256`. Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.|
|clientCredentialType|Especifica el tipo de credencial que se va a utilizar al realizar la autenticación del cliente para los mensajes enviados sobre el transporte de MSMQ. Los valores válidos son los siguientes:<br /><br /> Ninguna Esto permite al servicio interactuar con clientes anónimos. Ni el servicio ni el cliente requieren una credencial.<br />Windows Esto permite a los intercambios de SOAP estar bajo el contexto autenticado de una credencial de Windows. Esto siempre realiza una autenticación basada en Kerberos.<br />Nombre Esto permite que el servicio requiera que el cliente se autentique con una credencial de nombre de usuario. En este caso, la credencial debe especificarse con el `clientCredentials` comportamiento **PRECAUCIÓN:**  Windows Communication Foundation (WCF) no admite el envío de un resumen de contraseña ni la derivación de claves mediante contraseña y el uso de tales claves para la seguridad de los mensajes. Por lo tanto, WCF exige que el intercambio esté protegido al utilizar las credenciales de nombre de usuario. Este modo requiere que el certificado del servicio se especifique en el lado del cliente mediante el comportamiento de `clientCredential` y `serviceCertificate`. <br /><br /> Certificado Esto permite que el servicio requiera que el cliente se autentique mediante un certificado. Las credenciales del cliente en este caso tienen que especificarse mediante el comportamiento `clientCredentials`. La credencial del servicio en este caso necesita ser especificada utilizando el comportamiento `clientCredentials` especificando `serviceCertificate`.<br />CardSpace Esto permite que el servicio requiera que el cliente se autentique mediante un CardSpace. Se debe proporcionar `serviceCertificate` en el comportamiento `clientCredential`.<br /><br /> El valor predeterminado es `Windows`. Este atributo es del tipo <xref:System.ServiceModel.MessageCredentialType>.|

### <a name="child-elements"></a>Elementos secundarios

None

### <a name="parent-elements"></a>Elementos primarios

|Elemento|DESCRIPCIÓN|
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
- [\<binding>](../../../misc/binding.md)
