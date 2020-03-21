---
title: 'Cómo: Utilizar el proveedor de funciones ASP.NET con un servicio'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: ddfedeb2491998f64ab241ceba303d50d0714351
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184769"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>Cómo: Utilizar el proveedor de funciones ASP.NET con un servicio

El proveedor de roles ASP.NET (junto con el proveedor de pertenencia ASP.NET) es una característica que permite a los desarrolladores de ASP.NET crear sitios Web que permiten a los usuarios crear una cuenta con un sitio y asignar roles con fines de autorización. Con esta característica, cualquier usuario puede establecer una cuenta con el sitio e iniciar sesión para el acceso exclusivo al sitio y sus servicios. Esto contrasta con la seguridad de Windows, que exige a los usuarios que tengan cuentas en un dominio de Windows. En su lugar, cualquier usuario que proporciona sus credenciales (la combinación de nombre de usuario y contraseña) puede usar el sitio y sus servicios.  
  
Para obtener una aplicación de ejemplo, vea Proveedor de [pertenencia y rol](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Para obtener más información acerca de la característica de proveedor de pertenencia ASP.NET, vea [Cómo: usar el ASP.NET proveedor](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)de pertenencia .  
  
La característica de proveedor de roles usa una base de datos de SQL Server para almacenar información sobre el usuario. Los desarrolladores de Windows Communication Foundation (WCF) pueden aprovechar estas características por motivos de seguridad. Cuando se integra en una aplicación WCF, los usuarios deben proporcionar una combinación de nombre de usuario y contraseña a la aplicación cliente WCF. Para permitir que WCF use la base de <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> datos, <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> debe <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>crear una instancia de la clase, <xref:System.ServiceModel.ServiceHost> establecer su propiedad en y agregar la instancia a la colección de comportamientos a la que hospeda el servicio.  
  
## <a name="configure-the-role-provider"></a>Configurar el proveedor de roles  
  
1. En el archivo Web.config, `system.web` en el elemento `roleManager`> <, `enabled` agregue `true`un elemento> <y establezca su atributo en .  
  
2. Defina el atributo `defaultProvider` a `SqlRoleProvider`.  
  
3. Como elemento secundario `roleManager` del elemento <`providers`>, agregue un elemento> <.  
  
4. Como elemento secundario `providers` del elemento> `add` <, agregue un elemento> `name`de `type` `connectionStringName`<`applicationName`con los siguientes atributos establecidos en los valores adecuados: , , , , , , como se muestra en el ejemplo siguiente.  
  
    ```xml  
    <!-- Configure the Sql Role Provider. -->  
    <roleManager enabled ="true"
     defaultProvider ="SqlRoleProvider" >  
       <providers>  
         <add name ="SqlRoleProvider"
           type="System.Web.Security.SqlRoleProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipAndRoleProviderSample"/>  
       </providers>  
    </roleManager>  
    ```  
  
## <a name="configure-the-service-to-use-the-role-provider"></a>Configure el servicio para que use el proveedor de roles  
  
1. En el archivo Web.config, agregue un [ \<elemento>system.serviceModel.](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
2. Agregue un [ \<elemento>comportamientos](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) al elemento> <. `system.ServiceModel`  
  
3. Agregue un [ \<>serviceBehaviors](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) al elemento <`behaviors`>.  
  
4. Agregue [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) un comportamiento>`name` elemento y establezca el atributo en un valor adecuado.  
  
5. Agregue un [ \<>serviceAuthorization](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) al elemento <`behavior`>.  
  
6. Defina el atributo `principalPermissionMode` a `UseAspNetRoles`.  
  
7. Defina el atributo `roleProviderName` a `SqlRoleProvider`. En el ejemplo siguiente se muestra un fragmento de la configuración.  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="see-also"></a>Consulte también

- [Proveedor de pertenencia y roles](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [Uso del proveedor de pertenencia de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
