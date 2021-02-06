---
description: 'Más información acerca de: Tutorial: crear credenciales de cliente y servicio personalizadas'
title: 'Tutorial: Crear credenciales de cliente y servicio personalizadas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b5ba5c3-0c6c-48e9-9e46-54acaec443ba
ms.openlocfilehash: 75313defafaf0d0d558c100f1e86df9e2415d993
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643961"
---
# <a name="walkthrough-creating-custom-client-and-service-credentials"></a>Tutorial: Crear credenciales de cliente y servicio personalizadas

En este tema se muestra cómo implementar credenciales de cliente y servicio personalizadas y cómo utilizar las credenciales personalizadas desde el código de la aplicación.

## <a name="credentials-extensibility-classes"></a>Clases de extensibilidad de credenciales

Las <xref:System.ServiceModel.Description.ClientCredentials> <xref:System.ServiceModel.Description.ServiceCredentials> clases y son los puntos de entrada principales a la extensibilidad de seguridad de Windows Communication Foundation (WCF). Estas clases de credenciales proporcionan las API que permiten al código de la aplicación establecer información de las credenciales y convertir los tipos de credenciales en tokens de seguridad. (Los *tokens de seguridad* son la forma que se usa para transmitir información de credenciales dentro de los mensajes SOAP). Las responsabilidades de estas clases de credenciales pueden dividirse en dos áreas:

- Proporcione las API para que las aplicaciones establezcan la información de las credenciales.

- Haga las funciones de un generador para las implementaciones de <xref:System.IdentityModel.Selectors.SecurityTokenManager>.

Las implementaciones predeterminadas proporcionadas en WCF admiten los tipos de credenciales proporcionadas por el sistema y crean un administrador de tokens de seguridad que es capaz de administrar esos tipos de credenciales.

## <a name="reasons-to-customize"></a>Razones para personalizar

Hay varias razones para personalizar las clases de credenciales de cliente o servicio. Lo más importante es el requisito de cambiar el comportamiento de seguridad de WCF predeterminado con respecto a la administración de los tipos de credenciales proporcionados por el sistema, especialmente por los siguientes motivos:

- Cambios que no son posibles mediante otros puntos de extensibilidad.

- Agregar nuevos tipos de credenciales.

- Agregar nuevos tipos de tokens de seguridad personalizados.

En este tema se describe cómo implementar credenciales de cliente y servicio personalizadas y cómo utilizarlas desde el código de la aplicación.

## <a name="first-in-a-series"></a>Primero en una serie

La creación de una clase de credenciales personalizadas es solo el primer paso, ya que la razón para la personalización de credenciales es cambiar el comportamiento de WCF con respecto al aprovisionamiento de credenciales, la serialización de tokens de seguridad o la autenticación. Otros temas en esta sección describen cómo crear serializadores y autenticadores personalizados. En este aspecto, crear la clase de credenciales personalizada es el primer tema de la serie. Las acciones subsiguientes (crear serializadores y autenticadores personalizados) sólo se pueden hacer después de crear las credenciales personalizadas. Entre los temas adicionales que se generan a partir de este tema se incluyen:

- [Procedimiento para crear un proveedor de tokens de seguridad personalizado](how-to-create-a-custom-security-token-provider.md)

- [Procedimiento para crear un autenticador de tokens de seguridad personalizado](how-to-create-a-custom-security-token-authenticator.md)

- [Cómo: crear un token personalizado](how-to-create-a-custom-token.md).

## <a name="procedures"></a>Procedimientos

#### <a name="to-implement-custom-client-credentials"></a>Para implementar credenciales de cliente personalizadas

1. Defina una clase nueva derivada de la clase <xref:System.ServiceModel.Description.ClientCredentials>.

2. Opcional. Agregue nuevos métodos o propiedades para los nuevos tipos de credenciales. Si no agrega nuevos tipos de credencial, no realice este paso. En el ejemplo siguiente se agrega una propiedad `CreditCardNumber`.

3. Invalide el método <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> . La infraestructura de seguridad de WCF llama automáticamente a este método cuando se usa la credencial de cliente personalizada. Este método es responsable de crear y devolver una instancia de una implementación de la clase <xref:System.IdentityModel.Selectors.SecurityTokenManager>.

    > [!IMPORTANT]
    > Es importante tener en cuenta que el método <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> se invalida para crear un administrador de tokens de seguridad personalizado. El administrador de tokens de seguridad, derivado de <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>, debe devolver un proveedor de tokens de seguridad personalizado, derivado de <xref:System.IdentityModel.Selectors.SecurityTokenProvider>, para crear el token de seguridad propiamente dicho. Si no sigue este patrón para crear los tokens de seguridad, la aplicación puede tener un funcionamiento incorrecto al almacenar los objetos <xref:System.ServiceModel.ChannelFactory> en la memoria caché (que es el comportamiento predeterminado para los servidores proxy de cliente de WCF), lo que puede producir un ataque de elevación de privilegios. El objeto de credencial personalizado se almacena en memoria caché como parte de la clase <xref:System.ServiceModel.ChannelFactory>. Sin embargo, la clase <xref:System.IdentityModel.Selectors.SecurityTokenManager> personalizada se crea en cada invocación, lo que mitiga la amenaza de seguridad siempre que la lógica de creación de tokens se sitúe en la clase <xref:System.IdentityModel.Selectors.SecurityTokenManager>.

4. Invalide el método <xref:System.ServiceModel.Description.ClientCredentials.CloneCore%2A> .

    [!code-csharp[c_CustomCredentials#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#1)]
    [!code-vb[c_CustomCredentials#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#1)]

#### <a name="to-implement-a-custom-client-security-token-manager"></a>Para implementar un administrador de tokens de seguridad de cliente personalizados

1. Defina una clase nueva derivada a partir de <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>.

2. Opcional. Invalide el método <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> si se debe crear una implementación de <xref:System.IdentityModel.Selectors.SecurityTokenProvider> personalizada. Para obtener más información acerca de los proveedores de tokens de seguridad personalizados, consulte [Cómo: crear un proveedor de tokens de seguridad personalizado](how-to-create-a-custom-security-token-provider.md).

3. Opcional. Invalide el método <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%28System.IdentityModel.Selectors.SecurityTokenRequirement%2CSystem.IdentityModel.Selectors.SecurityTokenResolver%40%29> si se debe crear una implementación de <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> personalizada. Para obtener más información sobre los autenticadores de tokens de seguridad personalizados, consulte [Cómo: crear un autenticador de tokens de seguridad personalizado](how-to-create-a-custom-security-token-authenticator.md).

4. Opcional. Invalide el método <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%2A> si se debe crear un <xref:System.IdentityModel.Selectors.SecurityTokenSerializer> personalizado. Para obtener más información sobre los tokens de seguridad personalizados y los serializadores de tokens de seguridad personalizados, consulte [Cómo: crear un token personalizado](how-to-create-a-custom-token.md).

    [!code-csharp[c_CustomCredentials#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#2)]
    [!code-vb[c_CustomCredentials#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#2)]

#### <a name="to-use-a-custom-client-credentials-from-application-code"></a>Para usar credenciales de cliente personalizadas a partir del código de la aplicación

1. Cree una instancia del cliente generado que representa la interfaz de servicio, o cree una instancia del <xref:System.ServiceModel.ChannelFactory> que señale a un servicio con el que desee comunicarse.

2. Elimine el comportamiento de credenciales de cliente proporcionadas por el sistema de la colección <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>, a la que se puede tener acceso mediante la propiedad <xref:System.ServiceModel.ChannelFactory.Endpoint%2A>.

3. Cree una nueva instancia de una clase de credenciales de cliente personalizada y agréguela a la colección <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>, a la que se puede tener acceso mediante la propiedad <xref:System.ServiceModel.ChannelFactory.Endpoint%2A>.

    [!code-csharp[c_CustomCredentials#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#3)]
    [!code-vb[c_CustomCredentials#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#3)]

El procedimiento anterior muestra cómo usar las credenciales de cliente del código de aplicación. Las credenciales de WCF también se pueden configurar mediante el archivo de configuración de la aplicación. A menudo, es preferible utilizar la configuración de la aplicación en lugar de emplear codificación de forma rígida, porque permite modificar los parámetros de la aplicación sin tener que modificar la fuente, recompilar y reimplementar.

El siguiente procedimiento describe cómo proporcionar compatibilidad para la configuración de credenciales personalizadas.

#### <a name="creating-a-configuration-handler-for-custom-client-credentials"></a>Creación de un controlador de configuración para las credenciales de cliente personalizadas

1. Defina una clase nueva derivada a partir de <xref:System.ServiceModel.Configuration.ClientCredentialsElement>.

2. Opcional. Agregue propiedades para todos los parámetros de configuración adicionales que desee exponer a través de la configuración de la aplicación. El siguiente ejemplo agrega una propiedad denominada `CreditCardNumber`.

3. Invalide la propiedad <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.BehaviorType%2A> para devolver el tipo de la clase de credenciales de cliente personalizadas creado con el elemento de configuración.

4. Invalide el método <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.CreateBehavior%2A> . El método es responsable de crear y devolver una instancia de la clase de credenciales personalizadas basándose en los ajustes cargados desde el archivo de configuración. Llame al método <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ApplyConfiguration%28System.ServiceModel.Description.ClientCredentials%29> base desde este método para recuperar los ajustes de credenciales proporcionados por el sistema cargados en su instancia de credenciales de cliente personalizadas.

5. Opcional. Si agregó propiedades adicionales en el paso 2, ha de invalidar la propiedad <xref:System.Configuration.ConfigurationElement.Properties%2A> para registrar su configuración adicional para que el marco de configuración las reconozca. Combine sus propiedades con las propiedades de clase base para permitir que los ajustes proporcionados por el sistema se configuren a través de este elemento de configuración de credenciales de cliente personalizadas.

    [!code-csharp[c_CustomCredentials#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#7)]
    [!code-vb[c_CustomCredentials#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#7)]

Una vez que tenga la clase de controlador de configuración, se puede integrar en el marco de configuración de WCF. Eso permite que las credenciales de cliente personalizadas se usen en los elementos de comportamiento de extremo de cliente, tal y como se muestra en el siguiente procedimiento.

#### <a name="to-register-and-use-a-custom-client-credentials-configuration-handler-in-the-application-configuration"></a>Para registrar y usar un controlador de configuración de credenciales de cliente personalizadas en la configuración de la aplicación

1. Agregue un `extensions` elemento de> de <y un elemento de> de <`behaviorExtensions` al archivo de configuración.

2. Agregue un `add` elemento <> al elemento <`behaviorExtensions`> y establezca el `name` atributo en un valor adecuado.

3. Establezca el atributo `type` en el nombre de tipo completo. Incluya también el nombre de ensamblado y otros atributos de ensamblado.

    ```xml
    <system.serviceModel>
      <extensions>
        <behaviorExtensions>
          <add name="myClientCredentials" type="Microsoft.ServiceModel.Samples.MyClientCredentialsConfigHandler, CustomCredentials, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
        </behaviorExtensions>
      </extensions>
    </system.serviceModel>
    ```

4. Después de registrar el controlador de configuración, el elemento de credenciales personalizadas puede usarse dentro del mismo archivo de configuración en lugar del elemento de> <proporcionado por el sistema `clientCredentials` . Puede utilizar las propiedades proporcionadas por el sistema y cualquier propiedad nueva que haya agregado a su implementación del controlador de configuración. El siguiente ejemplo establece el valor de una propiedad personalizada mediante el atributo `creditCardNumber`.

    ```xml
    <behaviors>
      <endpointBehaviors>
        <behavior name="myClientCredentialsBehavior">
          <myClientCredentials creditCardNumber="123-123-123"/>
        </behavior>
      </endpointBehaviors>
    </behaviors>
    ```

#### <a name="to-implement-custom-service-credentials"></a>Para implementar credenciales de servicio personalizadas

1. Defina una clase nueva derivada a partir de <xref:System.ServiceModel.Description.ServiceCredentials>.

2. Opcional. Agregue nuevas propiedades para proporcionar API para los nuevos valores de credenciales que se están agregando. Si no agrega nuevos valores de credenciales, no realice este paso. En el siguiente ejemplo se agrega una propiedad `AdditionalCertificate`.

3. Invalide el método <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> . La infraestructura de WCF llama automáticamente a este método cuando se usa la credencial de cliente personalizada. El método es responsable de crear y devolver una instancia de una implementación de la clase <xref:System.IdentityModel.Selectors.SecurityTokenManager>(descrita en el siguiente procedimiento).

4. Opcional. Invalide el método <xref:System.ServiceModel.Description.ServiceCredentials.CloneCore%2A> . Esto sólo se requiere si se agregan nuevas propiedades o campos internos a la implementación de credenciales de cliente personalizadas.

    [!code-csharp[c_CustomCredentials#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#4)]
    [!code-vb[c_CustomCredentials#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#4)]

#### <a name="to-implement-a-custom-service-security-token-manager"></a>Para implementar un administrador de tokens de seguridad de servicio personalizados

1. Defina una clase nueva derivada de la clase <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>.

2. Opcional. Invalide el método <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%2A> si se debe crear una implementación de <xref:System.IdentityModel.Selectors.SecurityTokenProvider> personalizada. Para obtener más información acerca de los proveedores de tokens de seguridad personalizados, consulte [Cómo: crear un proveedor de tokens de seguridad personalizado](how-to-create-a-custom-security-token-provider.md).

3. Opcional. Invalide el método <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A> si se debe crear una implementación de <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> personalizada. Para obtener más información acerca de los autenticadores de tokens de seguridad personalizados, consulte [Cómo: crear un autenticador de tokens de seguridad personalizado](how-to-create-a-custom-security-token-authenticator.md) .

4. Opcional. Invalide el método <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%28System.IdentityModel.Selectors.SecurityTokenVersion%29> si se debe crear un <xref:System.IdentityModel.Selectors.SecurityTokenSerializer> personalizado. Para obtener más información sobre los tokens de seguridad personalizados y los serializadores de tokens de seguridad personalizados, consulte [Cómo: crear un token personalizado](how-to-create-a-custom-token.md).

    [!code-csharp[c_CustomCredentials#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#5)]
    [!code-vb[c_CustomCredentials#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#5)]

#### <a name="to-use-custom-service-credentials-from-application-code"></a>Para usar credenciales de servicio personalizadas a partir del código de la aplicación

1. Creación de una instancia de <xref:System.ServiceModel.ServiceHost>.

2. Elimine el comportamiento de las credenciales de servicio proporcionadas por el sistema desde la colección <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>.

3. Cree una nueva instancia de la clase de credenciales de servicio personalizadas y agréguela a la colección <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>.

    [!code-csharp[c_CustomCredentials#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#6)]
    [!code-vb[c_CustomCredentials#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#6)]

Agregue compatibilidad para la configuración mediante los pasos descritos anteriormente en los procedimientos " `To create a configuration handler for custom client credentials` " y "" `To register and use a custom client credentials configuration handler in the application configuration` . La única diferencia es usar la <xref:System.ServiceModel.Configuration.ServiceCredentialsElement> clase en lugar de la <xref:System.ServiceModel.Configuration.ClientCredentialsElement> clase como una clase base para el controlador de configuración. El elemento de credencial de servicio personalizado puede utilizarse después dondequiera que se utilice el elemento `<serviceCredentials>` proporcionado por el sistema.

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- <xref:System.ServiceModel.Security.SecurityCredentialsManager>
- <xref:System.IdentityModel.Selectors.SecurityTokenManager>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- [Procedimiento para crear un proveedor de tokens de seguridad personalizado](how-to-create-a-custom-security-token-provider.md)
- [Procedimiento para crear un autenticador de tokens de seguridad personalizado](how-to-create-a-custom-security-token-authenticator.md)
- [Procedimiento para crear un token personalizado](how-to-create-a-custom-token.md)
