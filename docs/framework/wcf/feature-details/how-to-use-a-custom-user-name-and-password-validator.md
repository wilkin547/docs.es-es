---
title: "C&#243;mo utilizar un nombre de usuario personalizado y un validador de contrase&#241;as | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF, nombre de usuario y contraseña"
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# C&#243;mo utilizar un nombre de usuario personalizado y un validador de contrase&#241;as
De forma predeterminada, cuando un nombre de usuario y la contraseña se utilizan para la autenticación, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utiliza Windows para validar el nombre de usuario y la contraseña.Sin embargo, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] permite esquemas personalizados de autenticación de nombre de usuario y contraseña, también conocidos como *validadores*.Para incorporar un nombre de usuario personalizado y un validador de contraseña, cree una clase que derive de <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> y, a continuación, configúrela.  
  
 Para obtener una aplicación de ejemplo, consulte [Validador de contraseña de nombre de usuario](../../../../docs/framework/wcf/samples/user-name-password-validator.md).  
  
### Para crear un nombre de usuario personalizado y un validador de contraseñas  
  
1.  Cree una clase que derive de <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]  
  
2.  Implemente el esquema personalizado de autenticación invalidando el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
     No utilice el código en el ejemplo siguiente que invalida el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> en un entorno de producción.Reemplace el código con su nombre de usuario personalizado y esquema de validación de contraseña, que podrían implicar la recuperación de los pares de nombre de usuario y contraseña de una base de datos.  
  
     Para devolver errores de autenticación al cliente, inicie una <xref:System.ServiceModel.FaultException> en el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]  
  
### Para configurar un servicio con el fin de utilizar un nombre de usuario personalizado y un validador de contraseñas  
  
1.  Configure un enlace que utilice la seguridad de mensaje sobre cualquier transporte o la seguridad del nivel de transporte sobre HTTP\(S\).  
  
     Si utiliza la seguridad de mensaje, agregue uno de los enlaces proporcionados por el sistema, como [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) o [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md), que admita la seguridad de mensaje y el tipo de credencial `UserName`.  
  
     Cuando use la seguridad del nivel de transporte sobre HTTP\(S\), agregue el elemento [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) o [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), un elemento [\<netTcpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) o [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) que use HTTP\(S\) y el esquema de autenticación  `Basic`.  
  
    > [!NOTE]
    >  Si se utiliza [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] o una versión posterior, puede usarse un validador de nombre de usuario y de contraseña personalizado con la seguridad de mensaje y de transporte.Con [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], solo puede utilizarse un validador de nombre de usuario y de contraseña con la seguridad de mensaje.  
  
    > [!TIP]
    >  Para obtener más información sobre el uso de \<netTcpBinding\> en este contexto, vea [\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)  
  
    1.  En el archivo de configuración, en el elemento [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md), agregue un elemento [\<enlaces\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md).  
  
    2.  Agregue un [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) o un elemento [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) a la sección de enlaces.Para [!INCLUDE[crabout](../../../../includes/crabout-md.md)] que crea un elemento de enlace [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vea [Cómo: Especificar un enlace de servicio en la configuración](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
    3.  Establezca el atributo `mode` de [\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) o [\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)`Message``Transport` como `or`, `TransportWithMessageCredential`,  .  
  
    4.  Establezca el atributo `clientCredentialType` de [\<message\>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) o [\<transporte\>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).  
  
         Si utiliza la seguridad de mensaje, establezca el atributo `clientCredentialType` de [\<message\>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) como `UserName`.  
  
         Si utiliza la seguridad de nivel de transporte sobre HTTP\(S\), establezca el atributo `clientCredentialType` de [\<transporte\>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)[\<transporte\>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)`Basic` o  como .  
  
        > [!NOTE]
        >  Cuando un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se hospeda en Internet Information Services \(IIS\) mediante la seguridad del nivel de transporte, y se establece la propiedad <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> como <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>, el esquema de autenticación personalizado utiliza un subconjunto de autenticación de Windows.Esto se debe a que en este escenario, IIS realiza la autenticación de Windows antes de que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invoque al autenticador personalizado.  
  
     Para [!INCLUDE[crabout](../../../../includes/crabout-md.md)] que crea un elemento de enlace [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vea [Cómo: Especificar un enlace de servicio en la configuración](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
     El siguiente ejemplo muestra el código de configuración para el enlace.  
  
    ```  
    <system.serviceModel>   
      <bindings>  
      <wsHttpBinding>  
          <binding name="Binding1">  
            <security mode="Message">  
              <message clientCredentialType="UserName" />  
            </security>  
          </binding>          
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
2.  Configure un comportamiento que especifique que un nombre de usuario personalizado y el validador de contraseñas se utilizan para validar los pares de nombre de usuario y para los tokens de seguridad <xref:System.IdentityModel.Tokens.UserNameSecurityToken> entrantes.  
  
    1.  Agregue un elemento secundario al elemento [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)[\<comportamientos\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).  
  
    2.  Agregue [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) al elemento [\<comportamientos\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).  
  
    3.  Agregue un elemento [\<comportamiento\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)`name y establezca el atributo`  en un valor adecuado.  
  
    4.  Agregue [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)[\<comportamiento\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) al elemento .  
  
    5.  Agregue [\<userNameAuthentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) a [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).  
  
    6.  Establezca `userNamePasswordValidationMode` en `Custom`.  
  
        > [!IMPORTANT]
        >  Si no se establece el valor `userNamePasswordValidationMode`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza la autenticación de Windows en lugar del nombre de usuario personalizado y validador de la contraseña.  
  
    7.  Establezca `customUserNamePasswordValidatorType` en el tipo que representa su nombre de usuario personalizado y el validador de la contraseña.  
  
     El ejemplo siguiente muestra el fragmento `<serviceCredentials>` en este punto.  
  
    ```  
    <serviceCredentials>  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />  
    </serviceCredentials>  
    ```  
  
## Ejemplo  
 El ejemplo de código siguiente muestra cómo crear un nombre de usuario personalizado y el validador de la contraseña.No utilice el código que invalida el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> en un entorno de producción.Reemplace el código con su nombre de usuario personalizado y esquema de validación de contraseña, que podrían implicar la recuperación de los pares de nombre de usuario y contraseña de una base de datos.  
  
 [!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
 [!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]  
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]  
  
## Vea también  
 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>   
 [Cómo: Utilizar el proveedor de pertenencia de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)   
 [Autenticación](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)