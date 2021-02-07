---
description: 'Más información acerca de cómo: usar el proveedor de roles ASP.NET con un servicio'
title: Procedimiento para usar el proveedor de roles ASP.NET con un servicio
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: 24bf9ad72d3634baf1d7120e4e60ccde5a4078a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734118"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>Procedimiento para usar el proveedor de roles ASP.NET con un servicio

El proveedor de roles ASP.NET (junto con el proveedor de pertenencia a ASP.NET) es una característica que permite a los desarrolladores de ASP.NET crear sitios web que permiten a los usuarios crear una cuenta con un sitio y asignarles roles para fines de autorización. Con esta característica, cualquier usuario puede establecer una cuenta con el sitio e iniciar sesión para el acceso exclusivo al sitio y sus servicios. Esto contrasta con la seguridad de Windows, que exige a los usuarios que tengan cuentas en un dominio de Windows. En su lugar, cualquier usuario que proporcione sus credenciales (la combinación de nombre de usuario y contraseña) puede utilizar el sitio y sus servicios.  
  
Para obtener una aplicación de ejemplo, vea [pertenencia y proveedor de roles](../samples/membership-and-role-provider.md). Para obtener más información acerca de la característica de proveedor de pertenencia de ASP.NET, consulte [Cómo: usar el proveedor de pertenencia a ASP.net](how-to-use-the-aspnet-membership-provider.md).  
  
La característica de proveedor de roles usa una base de datos de SQL Server para almacenar información sobre el usuario. Los desarrolladores de Windows Communication Foundation (WCF) pueden aprovechar las ventajas de estas características por motivos de seguridad. Cuando se integra en una aplicación WCF, los usuarios deben proporcionar una combinación de nombre de usuario/contraseña para la aplicación cliente de WCF. Para permitir que WCF use la base de datos, debe crear una instancia de la <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> clase, establecer su <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> propiedad en <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> y agregar la instancia de a la colección de comportamientos al <xref:System.ServiceModel.ServiceHost> que hospeda el servicio.  
  
## <a name="configure-the-role-provider"></a>Configurar el proveedor de roles  
  
1. En el archivo de Web.config, en el <`system.web`> elemento, agregue un `roleManager` elemento <> y establezca su `enabled` atributo en `true` .  
  
2. Defina el atributo `defaultProvider` a `SqlRoleProvider`.  
  
3. Como elemento secundario del elemento <`roleManager`>, agregue un elemento <`providers`>.  
  
4. Como elemento secundario del elemento <`providers`>, agregue un elemento <`add`> con los siguientes atributos establecidos en los valores adecuados: `name` , `type` , `connectionStringName` y `applicationName` , tal y como se muestra en el ejemplo siguiente.  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a>Configurar el servicio para usar el proveedor de roles  
  
1. En el archivo de Web.config, agregue un [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elemento.  
  
2. Agregue un [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elemento al elemento <`system.ServiceModel`>.  
  
3. Agregue un [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) al elemento <`behaviors`>.  
  
4. Agregue un [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento y establezca el `name` atributo en un valor adecuado.  
  
5. Agregue un [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) al elemento <`behavior`>.  
  
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
  
## <a name="see-also"></a>Vea también

- [Proveedor de pertenencia y roles](../samples/membership-and-role-provider.md)
- [Procedimiento para usar el proveedor de pertenencia de ASP.NET](how-to-use-the-aspnet-membership-provider.md)
