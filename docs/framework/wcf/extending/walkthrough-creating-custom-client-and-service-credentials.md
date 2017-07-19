---
title: "Tutorial: Crear credenciales de cliente y servicio personalizadas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2b5ba5c3-0c6c-48e9-9e46-54acaec443ba
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Tutorial: Crear credenciales de cliente y servicio personalizadas
En este tema se muestra cómo implementar credenciales de cliente y servicio personalizadas y cómo utilizar las credenciales personalizadas desde el código de la aplicación.  
  
## Clases de extensibilidad de credenciales  
 Las clases <xref:System.ServiceModel.Description.ClientCredentials> y <xref:System.ServiceModel.Description.ServiceCredentials> son los puntos de entrada principales a la extensibilidad de seguridad de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Estas clases de credenciales proporcionan las API que permiten al código de la aplicación establecer información de las credenciales y convertir los tipos de credenciales en tokens de seguridad.\(Los *tokens de seguridad* son la forma usada para transmitir información de credenciales dentro de los mensajes SOAP.\) Las responsabilidades de estas clases de credenciales pueden dividirse en dos áreas:  
  
-   Proporcione las API para que las aplicaciones establezcan la información de las credenciales.  
  
-   Haga las funciones de un generador para las implementaciones de <xref:System.IdentityModel.Selectors.SecurityTokenManager>.  
  
 Las clases <xref:System.ServiceModel.Description.ClientCredentials> y <xref:System.ServiceModel.Description.ServiceCredentials> heredan de la clase <xref:System.ServiceModel.Security.SecurityCredentialsManager> abstracta que define el contrato para la devolución del <xref:System.IdentityModel.Selectors.SecurityTokenManager>.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] las clases de credenciales y cuál es su papel en la arquitectura de seguridad de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vea [Security Architecture](http://msdn.microsoft.com/es-es/16593476-d36a-408d-808c-ae6fd483e28f).  
  
 Las implementaciones predeterminadas proporcionadas en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admiten los tipos de credenciales proporcionados por el sistema y crean un administrador de tokens de seguridad que es capaz de administrar esos tipos de credenciales.  
  
## Razones para personalizar  
 Hay varias razones para personalizar las clases de credenciales de cliente o servicio.En primer lugar está la necesidad de cambiar el comportamiento de seguridad predeterminado de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con respecto a la administración de los tipos de credenciales proporcionados por el sistema, sobre todo por las razones siguientes:  
  
-   Cambios que no son posibles mediante otros puntos de extensibilidad.  
  
-   Agregar nuevos tipos de credenciales.  
  
-   Agregar nuevos tipos de tokens de seguridad personalizados.  
  
 En este tema se describe cómo implementar credenciales de cliente y servicio personalizadas y cómo utilizarlas desde el código de la aplicación.  
  
## Primero en una serie  
 Crear una clase de credenciales personalizadas sólo es el primer paso, porque la razón para personalizar las credenciales es cambiar el comportamiento de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con respecto al suministro de credenciales, serialización de tokens de seguridad o autenticación.Otros temas en esta sección describen cómo crear serializadores y autenticadores personalizados.En este aspecto, crear la clase de credenciales personalizada es el primer tema de la serie.Las acciones subsiguientes \(crear serializadores y autenticadores personalizados\) sólo se pueden hacer después de crear las credenciales personalizadas.Entre los temas adicionales que se generan a partir de este tema se incluyen:  
  
-   [Cómo crear un proveedor de tokens de seguridad personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
  
-   [Cómo: Crear un autenticador de tokens de seguridad personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
  
-   [Cómo: Crear un token personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
## Procedures  
  
#### Para implementar credenciales de cliente personalizadas  
  
1.  Defina una clase nueva derivada de la clase <xref:System.ServiceModel.Description.ClientCredentials>.  
  
2.  Parámetro opcional.Agregue nuevos métodos o propiedades para los nuevos tipos de credenciales.Si no agrega nuevos tipos de credencial, no realice este paso.En el ejemplo siguiente se agrega una propiedad `CreditCardNumber`.  
  
3.  Invalide el método <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A>.La infraestructura de seguridad de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] llama automáticamente a este método cuando se usa la credencial de cliente personalizada.Este método es responsable de crear y devolver una instancia de una implementación de la clase <xref:System.IdentityModel.Selectors.SecurityTokenManager>.  
  
    > [!IMPORTANT]
    >  Es importante tener en cuenta que el método <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> se invalida para crear un administrador de tokens de seguridad personalizado.El administrador de tokens de seguridad, derivado de <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>, debe devolver un proveedor de tokens de seguridad personalizado, derivado de <xref:System.IdentityModel.Selectors.SecurityTokenProvider>, para crear el token de seguridad propiamente dicho.Si no sigue este modelo para crear los tokens de seguridad, la aplicación puede tener un funcionamiento incorrecto al almacenar los objetos <xref:System.ServiceModel.ChannelFactory> en la memoria caché \(que es el comportamiento predeterminado para los servidores proxy de cliente de WCF\), lo que puede producir un ataque de elevación de privilegios.El objeto de credencial personalizado se almacena en memoria caché como parte de la clase <xref:System.ServiceModel.ChannelFactory>.Sin embargo, la clase <xref:System.IdentityModel.Selectors.SecurityTokenManager> personalizada se crea en cada invocación, lo que mitiga la amenaza de seguridad siempre que la lógica de creación de tokens se sitúe en la clase <xref:System.IdentityModel.Selectors.SecurityTokenManager>.  
  
4.  Invalide el método <xref:System.ServiceModel.Description.ClientCredentials.CloneCore%2A>.  
  
     [!code-csharp[c_CustomCredentials#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#1)]
     [!code-vb[c_CustomCredentials#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#1)]  
  
#### Para implementar un administrador de tokens de seguridad de cliente personalizados  
  
1.  Defina una clase nueva derivada a partir de <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>.  
  
2.  Parámetro opcional.Invalide el método <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> si se debe crear una implementación de <xref:System.IdentityModel.Selectors.SecurityTokenProvider> personalizada.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] los proveedores de tokens de seguridad personalizados, vea [Cómo crear un proveedor de tokens de seguridad personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md).  
  
3.  Parámetro opcional.Invalide el método <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%28System.IdentityModel.Selectors.SecurityTokenRequirement%2CSystem.IdentityModel.Selectors.SecurityTokenResolver%40%29> si se debe crear una implementación de <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> personalizada.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] los autenticadores de tokens de seguridad personalizados, vea [Cómo: Crear un autenticador de tokens de seguridad personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md).  
  
4.  Parámetro opcional.Invalide el método <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%2A> si se debe crear un <xref:System.IdentityModel.Selectors.SecurityTokenSerializer> personalizado.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] los tokens de seguridad personalizados y los serializadores de tokens de seguridad personalizados, vea [Cómo: Crear un token personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
     [!code-csharp[c_CustomCredentials#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#2)]
     [!code-vb[c_CustomCredentials#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#2)]  
  
#### Para usar credenciales de cliente personalizadas a partir del código de la aplicación  
  
1.  Cree una instancia del cliente generado que representa la interfaz de servicio, o cree una instancia del <xref:System.ServiceModel.ChannelFactory> que señale a un servicio con el que desee comunicarse.  
  
2.  Elimine el comportamiento de credenciales de cliente proporcionadas por el sistema de la colección <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>, a la que se puede tener acceso mediante la propiedad <xref:System.ServiceModel.ChannelFactory.Endpoint%2A>.  
  
3.  Cree una nueva instancia de una clase de credenciales de cliente personalizada y agréguela a la colección <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>, a la que se puede tener acceso mediante la propiedad <xref:System.ServiceModel.ChannelFactory.Endpoint%2A>.  
  
     [!code-csharp[c_CustomCredentials#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#3)]
     [!code-vb[c_CustomCredentials#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#3)]  
  
 El procedimiento anterior muestra cómo usar las credenciales de cliente del código de aplicación.También se pueden configurar credenciales de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usando el archivo de configuración de la aplicación.A menudo, es preferible utilizar la configuración de la aplicación en lugar de emplear codificación de forma rígida, porque permite modificar los parámetros de la aplicación sin tener que modificar la fuente, recompilar y reimplementar.  
  
 El siguiente procedimiento describe cómo proporcionar compatibilidad para la configuración de credenciales personalizadas.  
  
#### Creación de un controlador de configuración para las credenciales de cliente personalizadas  
  
1.  Defina una clase nueva derivada a partir de <xref:System.ServiceModel.Configuration.ClientCredentialsElement>.  
  
2.  Parámetro opcional.Agregue propiedades para todos los parámetros de configuración adicionales que desee exponer a través de la configuración de la aplicación.El siguiente ejemplo agrega una propiedad denominada `CreditCardNumber`.  
  
3.  Invalide la propiedad <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.BehaviorType%2A> para devolver el tipo de la clase de credenciales de cliente personalizadas creado con el elemento de configuración.  
  
4.  Invalide el método <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.CreateBehavior%2A>.El método es responsable de crear y devolver una instancia de la clase de credenciales personalizadas basándose en los ajustes cargados desde el archivo de configuración.Llame al método <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ApplyConfiguration%28System.ServiceModel.Description.ClientCredentials%29> base desde este método para recuperar los ajustes de credenciales proporcionados por el sistema cargados en su instancia de credenciales de cliente personalizadas.  
  
5.  Parámetro opcional.Si agregó propiedades adicionales en el paso 2, ha de invalidar la propiedad <xref:System.Configuration.ConfigurationElement.Properties%2A> para registrar su configuración adicional para que el marco de configuración las reconozca.Combine sus propiedades con las propiedades de clase base para permitir que los ajustes proporcionados por el sistema se configuren a través de este elemento de configuración de credenciales de cliente personalizadas.  
  
     [!code-csharp[c_CustomCredentials#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#7)]
     [!code-vb[c_CustomCredentials#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#7)]  
  
 Una vez que tenga tiene la clase del controlador de configuración, puede integrarse en el marco de configuración de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Eso permite que las credenciales de cliente personalizadas se usen en los elementos de comportamiento de extremo de cliente, tal y como se muestra en el siguiente procedimiento.  
  
#### Para registrar y usar un controlador de configuración de credenciales de cliente personalizadas en la configuración de la aplicación  
  
1.  Agregue un elemento \<`extensions`\> y un elemento \<`behaviorExtensions`\> al archivo de configuración.  
  
2.  Agregue un elemento \<`add`\> al elemento \<`behaviorExtensions`\> y establezca el atributo `name` en un valor apropiado.  
  
3.  Establezca el atributo `type` en el nombre de tipo completo.Incluya también el nombre de ensamblado y otros atributos de ensamblado.  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <behaviorExtensions>  
          <add name="myClientCredentials" type="Microsoft.ServiceModel.Samples.MyClientCredentialsConfigHandler, CustomCredentials, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </behaviorExtensions>  
      </extensions>  
    <system.serviceModel>  
    ```  
  
4.  Después de registrar su controlador de configuración, el elemento de credenciales personalizadas se puede usar dentro del mismo archivo de configuración en lugar del elemento \<`clientCredentials`\> proporcionado por el sistema.Puede utilizar las propiedades proporcionadas por el sistema y cualquier propiedad nueva que haya agregado a su implementación del controlador de configuración.El siguiente ejemplo establece el valor de una propiedad personalizada mediante el atributo `creditCardNumber`.  
  
    ```  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="myClientCredentialsBehavior">  
          <myClientCredentials creditCardNumber="123-123-123"/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    ```  
  
#### Para implementar credenciales de servicio personalizadas  
  
1.  Defina una clase nueva derivada a partir de <xref:System.ServiceModel.Description.ServiceCredentials>.  
  
2.  Parámetro opcional.Agregue nuevas propiedades para proporcionar API para los nuevos valores de credenciales que se están agregando.Si no agrega nuevos valores de credenciales, no realice este paso.En el siguiente ejemplo se agrega una propiedad `AdditionalCertificate`.  
  
3.  Invalide el método <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A>.La infraestructura de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] llama automáticamente a este método cuando se utiliza la credencial de cliente personalizada.El método es responsable de crear y devolver una instancia de una implementación de la clase <xref:System.IdentityModel.Selectors.SecurityTokenManager>\(descrita en el siguiente procedimiento\).  
  
4.  Parámetro opcional.Invalide el método <xref:System.ServiceModel.Description.ServiceCredentials.CloneCore%2A>.Esto sólo se requiere si se agregan nuevas propiedades o campos internos a la implementación de credenciales de cliente personalizadas.  
  
     [!code-csharp[c_CustomCredentials#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#4)]
     [!code-vb[c_CustomCredentials#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#4)]  
  
#### Para implementar un administrador de tokens de seguridad de servicio personalizados  
  
1.  Defina una clase nueva derivada de la clase <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>.  
  
2.  Parámetro opcional.Invalide el método <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%2A> si se debe crear una implementación de <xref:System.IdentityModel.Selectors.SecurityTokenProvider> personalizada.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] los proveedores de tokens de seguridad personalizados, vea [Cómo crear un proveedor de tokens de seguridad personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md).  
  
3.  Parámetro opcional.Invalide el método <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A> si se debe crear una implementación de <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> personalizada.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] los autenticadores de token de seguridad personalizados, vea el tema [Cómo: Crear un autenticador de tokens de seguridad personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md).  
  
4.  Parámetro opcional.Invalide el método <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%28System.IdentityModel.Selectors.SecurityTokenVersion%29> si se debe crear un <xref:System.IdentityModel.Selectors.SecurityTokenSerializer> personalizado.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] los tokens de seguridad personalizados y los serializadores personalizados de token de seguridad, vea [Cómo: Crear un token personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
     [!code-csharp[c_CustomCredentials#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#5)]
     [!code-vb[c_CustomCredentials#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#5)]  
  
#### Para usar credenciales de servicio personalizadas a partir del código de la aplicación  
  
1.  Cree una instancia de <xref:System.ServiceModel.ServiceHost>.  
  
2.  Elimine el comportamiento de las credenciales de servicio proporcionadas por el sistema desde la colección <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>.  
  
3.  Cree una nueva instancia de la clase de credenciales de servicio personalizadas y agréguela a la colección <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>.  
  
     [!code-csharp[c_CustomCredentials#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#6)]
     [!code-vb[c_CustomCredentials#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#6)]  
  
 Agregue compatibilidad para la configuración mediante los pasos descritos previamente en los procedimientos "`To create a configuration handler for custom client credentials`" y "`To register and use a custom client credentials configuration handler in the application configuration`". La única diferencia es que se ha de utilizar la clase <xref:System.ServiceModel.Configuration.ServiceCredentialsElement> en lugar de la clase <xref:System.ServiceModel.Configuration.ClientCredentialsElement> como una clase base para el controlador de configuración.El elemento de credencial de servicio personalizado puede utilizarse después dondequiera que se utilice el elemento `<serviceCredentials>` proporcionado por el sistema.  
  
## Vea también  
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Description.ServiceCredentials>   
 <xref:System.ServiceModel.Security.SecurityCredentialsManager>   
 <xref:System.IdentityModel.Selectors.SecurityTokenManager>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>   
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>   
 [Cómo crear un proveedor de tokens de seguridad personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)   
 [Cómo: Crear un autenticador de tokens de seguridad personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)   
 [Cómo: Crear un token personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)