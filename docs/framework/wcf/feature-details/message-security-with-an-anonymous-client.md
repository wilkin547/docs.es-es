---
title: Seguridad de mensajes con clientes anónimos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cad53e1a-b7c9-4064-bc87-508c3d1dce49
ms.openlocfilehash: aed56be359f094db483ab1d012bd77a1096433b6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553771"
---
# <a name="message-security-with-an-anonymous-client"></a>Seguridad de mensajes con clientes anónimos

En el siguiente escenario se muestra un cliente y un servicio protegidos por la seguridad de mensajes de Windows Communication Foundation (WCF). Un objetivo del diseño es usar la seguridad del mensaje en lugar de la seguridad de transporte, para que en el futuro pueda admitir un modelo basado en notificaciones más completo. Para obtener más información sobre el uso de notificaciones enriquecidas para la autorización, consulte [Administración de notificaciones y autorización con el modelo de identidad](managing-claims-and-authorization-with-the-identity-model.md).

Para obtener una aplicación de ejemplo, vea [seguridad de mensajes anónima](../samples/message-security-anonymous.md).

![Seguridad de mensajes con un cliente anónimo](media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")

|Característica|Descripción|
|--------------------|-----------------|
|Modo de seguridad|Mensaje|
|Interoperabilidad|Solo WCF|
|Autenticación (servidor)|La negociación inicial requiere la autenticación del servidor, pero no la autenticación del cliente|
|Autenticación (cliente)|None|
|Integridad|Sí, mediante el contexto de seguridad compartido|
|Confidencialidad|Sí, mediante el contexto de seguridad compartido|
|Transporte|HTTP|

## <a name="service"></a>Servicio

El código y la configuración siguientes están diseñados para ejecutarse de forma independiente. Realice una de las siguientes acciones:

- Cree un servicio independiente mediante el código sin configuración.

- Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.

### <a name="code"></a>Código

El código siguiente muestra cómo crear un extremo de servicio que utiliza la seguridad del mensaje.

[!code-csharp[C_SecurityScenarios#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#8)]
[!code-vb[C_SecurityScenarios#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#8)]

### <a name="configuration"></a>Configuración

En lugar del código, se puede utilizar la siguiente configuración. El elemento de comportamiento del servicio se utiliza para especificar un certificado utilizado para autenticar el servicio al cliente. El elemento de servicio debe especificar el comportamiento mediante el atributo `behaviorConfiguration`. El elemento de enlace especifica que el tipo de credencial de cliente es `None`, de modo que permite a los clientes anónimos utilizar el servicio.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior name="ServiceCredentialsBehavior">
          <serviceCredentials>
            <serviceCertificate findValue="contoso.com"
                                storeLocation="LocalMachine"
                                storeName="My" />
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <services>
      <service behaviorConfiguration="ServiceCredentialsBehavior"
               name="ServiceModel.Calculator">
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="WSHttpBinding_ICalculator"
                  name="CalculatorService"
                  contract="ServiceModel.ICalculator" />
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Message">
            <message clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client />
  </system.serviceModel>
</configuration>
```

## <a name="client"></a>Cliente

El código y la configuración siguientes están diseñados para ejecutarse de forma independiente. Realice una de las siguientes acciones:

- Cree un cliente independiente mediante el código (y el código de cliente).

- Cree un cliente que no defina direcciones de punto de conexión. En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento. Por ejemplo:

    [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
    [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a>Código

En el ejemplo de código siguiente se crea una instancia de cliente. El enlace utiliza seguridad en modo de mensaje y el tipo de credencial de cliente está establecido como ninguno.

[!code-csharp[C_SecurityScenarios#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#15)]
[!code-vb[C_SecurityScenarios#15](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#15)]

### <a name="configuration"></a>Configuración

El siguiente código configura el cliente.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Message">
            <message clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client>
      <endpoint address="http://machineName/Calculator"
        binding="wsHttpBinding"
        bindingConfiguration="WSHttpBinding_ICalculator"
        contract="ICalculator"
        name="WSHttpBinding_ICalculator">
        <identity>
          <dns value="contoso.com" />
        </identity>
      </endpoint>
    </client>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a>Vea también

- [Información general sobre seguridad](security-overview.md)
- [Seguridad distribuida de aplicaciones](distributed-application-security.md)
- [Seguridad de mensaje anónima](../samples/message-security-anonymous.md)
- [Identidad del servicio y autenticación](service-identity-and-authentication.md)
- [Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))
