---
title: "C&#243;mo: Utilizar el proveedor de funciones ASP.NET con un servicio | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# C&#243;mo: Utilizar el proveedor de funciones ASP.NET con un servicio
El proveedor de funciones [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] \(junto con el proveedor de pertenencia [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] \) es una característica que permite a los programadores [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] crear sitios Web que permitan a los usuarios crear una cuenta con un sitio y asignar funciones para los propósitos de la autorización.Con esta característica, cualquier usuario puede establecer una cuenta con el sitio e iniciar sesión para el acceso exclusivo al sitio y sus servicios.Esto contrasta con la seguridad de Windows, que exige a los usuarios que tengan cuentas en un dominio de Windows.En su lugar, cualquier usuario que proporcione sus credenciales \(la combinación de nombre de usuario\/contraseña\) puede utilizar el sitio y sus servicios.  
  
 Para obtener una aplicación de ejemplo, vea [Proveedor de pertenencia y roles](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] la característica de proveedor de pertenencia de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], vea [Cómo: Utilizar el proveedor de pertenencia de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).  
  
 La característica de proveedor de roles usa una base de datos de SQL Server para almacenar información sobre el usuario.Los programadores de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se pueden aprovechar de estas características con fines de aumento de la seguridad.Cuando se integra en una aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], los usuarios deben proporcionar una combinación de nombre de usuario\/contraseña a la aplicación cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Para permitir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizar la base de datos, debe crear una instancia de la clase <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>, establecer su propiedad <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> en <xref:System.ServiceModel.Description.PrincipalPermissionMode>y agregar la instancia a la colección de comportamientos de <xref:System.ServiceModel.ServiceHost> que hospeda el servicio.  
  
### Para configurar el proveedor de funciones  
  
1.  En el archivo Web.config file, en el elemento \<`system.web`\> agregue un elemento \<`roleManager`\> y establezca su atributo `enabled` en `true`.  
  
2.  Defina el atributo `defaultProvider` a `SqlRoleProvider`.  
  
3.  Agregue un elemento secundario al elemento \<`roleManager`\>, agregue un elemento \<`providers`\>.  
  
4.  Como un elemento secundario del elemento \<`providers`\>, agregue un elemento \<`add`\> con los atributos siguientes establecidos en los valores adecuados: `name`, `type`, `connectionStringName`y `applicationName`, como se muestra en el ejemplo siguiente.  
  
    ```  
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
  
### Para configurar el servicio para utilizar el proveedor de funciones  
  
1.  En el archivo Web.config, agregue un elemento [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md).  
  
2.  Agregue un elemento [\<comportamientos\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)\< `al elemento system.ServiceModel`\>.  
  
3.  Agregue [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) al elemento \<`behaviors`\>.  
  
4.  Agregue un elemento [\<comportamiento\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) y defina el atributo `name` en un valor adecuado.  
  
5.  Agregue [\<serviceAuthorization\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)\<`behavior al elemento` \>.  
  
6.  Defina el atributo `principalPermissionMode` a `UseAspNetRoles`.  
  
7.  Defina el atributo `roleProviderName` a `SqlRoleProvider`.En el ejemplo siguiente se muestra un fragmento de la configuración.  
  
    ```  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## Vea también  
 [Proveedor de pertenencia y roles](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)   
 [Cómo: Utilizar el proveedor de pertenencia de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)