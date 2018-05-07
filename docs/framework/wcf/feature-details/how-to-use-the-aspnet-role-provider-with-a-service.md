---
title: 'Cómo: Utilizar el proveedor de funciones ASP.NET con un servicio'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: 846caf59816ee23166fb382a0c36ac0fed9df151
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>Cómo: Utilizar el proveedor de funciones ASP.NET con un servicio
El proveedor de funciones [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] (junto con el proveedor de pertenencia [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ) es una característica que permite a los programadores [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] crear sitios Web que permitan a los usuarios crear una cuenta con un sitio y asignar funciones para los propósitos de la autorización. Con esta característica, cualquier usuario puede establecer una cuenta con el sitio e iniciar sesión para el acceso exclusivo al sitio y sus servicios. Esto contrasta con la seguridad de Windows, que exige a los usuarios que tengan cuentas en un dominio de Windows. En su lugar, cualquier usuario que proporcione sus credenciales (la combinación de nombre de usuario/contraseña) puede utilizar el sitio y sus servicios.  
  
 Para una aplicación de ejemplo, vea [proveedor de pertenencia y rol](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Para obtener más información sobre la [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] característica de proveedor de pertenencia, vea [Cómo: usar el proveedor de pertenencia a ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).  
  
 La característica de proveedor de roles usa una base de datos de SQL Server para almacenar información sobre el usuario. Los desarrolladores de Windows Communication Foundation (WCF) pueden aprovechar las ventajas de estas características por motivos de seguridad. Cuando se integra en una aplicación de WCF, los usuarios deben proporcionar una combinación de nombre y contraseña de usuario a la aplicación de cliente WCF. Para habilitar WCF usar la base de datos, debe crear una instancia de la <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> clase, establezca su <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> propiedad <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>y agregar la instancia a la colección de comportamientos de la <xref:System.ServiceModel.ServiceHost> que hospeda el servicio.  
  
### <a name="to-configure-the-role-provider"></a>Para configurar el proveedor de funciones  
  
1.  En el archivo Web.config, en el <`system.web`> elemento, agregar un <`roleManager`> y establezca su `enabled` atribuir a `true`.  
  
2.  Defina el atributo `defaultProvider` a `SqlRoleProvider`.  
  
3.  Como elemento secundario de la <`roleManager`> elemento, agregar un <`providers`> elemento.  
  
4.  Como elemento secundario de la <`providers`> elemento, agregar un <`add`> elemento con los siguientes atributos se establece en valores adecuados: `name`, `type`, `connectionStringName`, y `applicationName`, tal y como se muestra en el ejemplo siguiente.  
  
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
  
### <a name="to-configure-the-service-to-use-the-role-provider"></a>Para configurar el servicio para utilizar el proveedor de funciones  
  
1.  En el archivo Web.config, agregue un [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento.  
  
2.  Agregar un [ \<comportamientos >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento a la <`system.ServiceModel`> elemento.  
  
3.  Agregar un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) a la <`behaviors`> elemento.  
  
4.  Agregar un [ \<comportamiento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) y establezca el `name` de atributo en un valor adecuado.  
  
5.  Agregar un [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) a la <`behavior`> elemento.  
  
6.  Defina el atributo `principalPermissionMode` a `UseAspNetRoles`.  
  
7.  Defina el atributo `roleProviderName` a `SqlRoleProvider`. En el ejemplo siguiente se muestra un fragmento de la configuración.  
  
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
 [Proveedor de pertenencia y roles](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 [Uso del proveedor de pertenencia de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
