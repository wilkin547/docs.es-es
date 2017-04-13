---
title: "C&#243;mo: Utilizar el proveedor de pertenencia de ASP.NET | Microsoft Docs"
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
  - "WCF y ASP.NET"
  - "WCF, autorización"
  - "WCF, seguridad"
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# C&#243;mo: Utilizar el proveedor de pertenencia de ASP.NET
El proveedor de pertenencia de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] es una característica que permite a los programadores de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] crear sitios web que permiten a los usuarios crear combinaciones únicas de nombre de usuario y contraseña.Con esta función, cualquier usuario puede establecer una cuenta en el sitio e iniciar sesión para obtener acceso exclusivo al sitio y a sus servicios.Esto contrasta con la seguridad de Windows, que exige a los usuarios que tengan cuentas en un dominio de Windows.En su lugar, cualquier usuario que proporcione sus credenciales \(la combinación de nombre de usuario\/contraseña\) puede utilizar el sitio y sus servicios.  
  
 Para obtener una aplicación de ejemplo, consulte [Proveedor de pertenencia y roles](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).Para obtener información acerca de cómo utilizar la característica del proveedor de funciones de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], vea [Cómo: Utilizar el proveedor de funciones ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).  
  
 La característica de pertenencia requiere el uso de una base de datos de SQL Server para almacenar la información de usuario.La característica también incluye métodos para realizar una pregunta a cualquier usuario que haya olvidado su contraseña.  
  
 Los programadores de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se pueden aprovechar de estas características con fines de aumento de la seguridad.Cuando se integran en una aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], los usuarios deben proporcionar una combinación de nombre de usuario y contraseña a la aplicación cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Para transferir los datos al servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], use un enlace que admita credenciales de nombre de usuario\/contraseña, como el <xref:System.ServiceModel.WSHttpBinding> \(en configuración, el [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)\) y establezca el tipo de credenciales en `UserName`.En el servicio, la seguridad [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] autentica al usuario en función del nombre de usuario y contraseña y también asigna la función especificada por la función [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
> [!NOTE]
>  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no proporciona métodos para rellenar la base de datos con combinaciones de nombre de usuario\/contraseña u otra información de usuario.  
  
### Para configurar el proveedor de pertenencia  
  
1.  En el archivo Web.config, bajo el elemento \<`system.web`\>, cree un elemento \<`membership`\>.  
  
2.  Bajo el elemento `<membership>`, cree un elemento `<providers>`.  
  
3.  Como elemento secundario del elemento \<`providers`\>, agregue un elemento `<clear />` para vaciar la colección de proveedores.  
  
4.  Bajo el elemento `<clear />`, cree un elemento \<`add`\> con los siguientes atributos establecidos en los valores adecuados: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer`, `requiresUniqueEmail`, y `passwordFormat`.El atributo `name` se utiliza más adelante como un valor en el archivo de configuración.El siguiente ejemplo lo define en `SqlMembershipProvider`.  
  
     En el ejemplo siguiente se muestra la sección de configuración.  
  
    ```xml  
    <!-- Configure the Sql Membership Provider -->  
    <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">  
      <providers>  
        <clear />  
          <add   
            name="SqlMembershipProvider"   
            type="System.Web.Security.SqlMembershipProvider"   
            connectionStringName="SqlConn"  
            applicationName="MembershipAndRoleProviderSample"  
            enablePasswordRetrieval="false"  
            enablePasswordReset="false"  
            requiresQuestionAndAnswer="false"  
            requiresUniqueEmail="true"  
            passwordFormat="Hashed" />  
      </providers>  
    </membership>  
    ```  
  
### Para configurar la seguridad de servicio para que acepte la combinación de nombre de usuario\/contraseña  
  
1.  En el archivo de configuración, en el elemento [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md), agregue un elemento [\<enlaces\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md).  
  
2.  Agregue un [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) a la sección de enlaces.Para [!INCLUDE[crabout](../../../../includes/crabout-md.md)] que crea un elemento de enlace [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vea [Cómo: Especificar un enlace de servicio en la configuración](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
3.  Establezca el atributo `mode` del elemento `<security>` en `Message`:  
  
4.  Establezca el atributo `clientCredentialType` del elemento \<`message`\> en `UserName`:Esto especifica que un par de nombre de usuario y contraseña se utilizará como credencial del cliente.  
  
     El siguiente ejemplo muestra el código de configuración para el enlace.  
  
    ```xml  
    <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
      <!-- Set up a binding that uses UserName as the client credential type -->  
        <binding name="MembershipBinding">  
          <security mode ="Message">  
            <message clientCredentialType ="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    </system.serviceModel>  
    ```  
  
### Para configurar un servicio para que utilice el proveedor de pertenencia  
  
1.  Agregue un elemento secundario al elemento `<system.serviceModel>`, agregue un elemento [\<comportamientos\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).  
  
2.  Agregue [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) al elemento \<`behaviors`\>.  
  
3.  Añada [\<comportamiento\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) y defina el atributo `name` en un valor adecuado.  
  
4.  Agregue [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) al elemento \<`behavior`\>.  
  
5.  Agregue [\<userNameAuthentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) al elemento `<serviceCredentials>`.  
  
6.  Defina el atributo `userNamePasswordValidationMode` a `MembershipProvider`.  
  
    > [!IMPORTANT]
    >  Si no se establece el valor `userNamePasswordValidationMode`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza la autenticación de Windows en lugar del proveedor de pertenencia de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
7.  Establezca el atributo `membershipProviderName` en el nombre del proveedor \(especificado al agregar el proveedor en el primer procedimiento de este tema\).El ejemplo siguiente muestra el fragmento `<serviceCredentials>` en este punto.  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
          <behavior name="MyServiceBehavior">  
             <serviceCredentials>  
                <userNameAuthentication   
                userNamePasswordValidationMode="MembershipProvider"  
                membershipProviderName="SqlMembershipProvider" />  
             </serviceCredentials>  
          </behavior>  
       </serviceBehaviors>  
    </behaviors>  
  
    ```  
  
## Ejemplo  
 El siguiente código muestra la configuración para un servicio que utiliza la característica de pertenencia de ASP.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="MyServiceBehavior" name="Microsoft.Samples.GettingStarted.CalculatorService">  
        <endpoint address="http://microsoft.com/WCFservices/Calculator"  
          binding="wsHttpBinding" bindingConfiguration="MembershipBinding"  
          name="ASPmemberUserName" contract="Microsoft.Samples.GettingStarted.ICalculator" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyServiceBehavior">  
          <serviceCredentials>  
            <userNameAuthentication   
              userNamePasswordValidationMode="MembershipProvider"  
              membershipProviderName="SqlMembershipProvider" />  
          </serviceCredentials>  
        </behavior>  
          </serviceBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MembershipBinding">  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
  
```  
  
## Vea también  
 [Cómo: Utilizar el proveedor de funciones ASP.NET con un servicio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)   
 [Proveedor de pertenencia y roles](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)