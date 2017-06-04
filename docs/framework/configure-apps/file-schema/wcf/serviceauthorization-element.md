---
title: "&lt;serviceAuthorization&gt; (elemento) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
caps.latest.revision: 26
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 26
---
# &lt;serviceAuthorization&gt; (elemento)
Especifica valores que autorizan que el acceso repare las operaciones  
  
## Sintaxis  
  
```  
  
<serviceAuthorization  
     impersonateCallerForAllOperations="Boolean"  
      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"  
      roleProviderName="String"  
      serviceAuthorizationManagerType="String" />  
      <authorizationPolicies>  
         <add policyType="String" />  
      </authorizationPolicies>  
</serviceAuthorization>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|impersonateCallerForAllOperations|Un valor booleano que especifica si todas las operaciones en el servicio suplantan al autor de la llamada.  De manera predeterminada, es `false`.<br /><br /> Cuando una operación de servicio concreta suplanta al llamador, el contexto del subproceso se intercambia al contexto del llamador antes de ejecutar el servicio especificado.|  
|principalPermissionMode|Establece la entidad de seguridad usada para llevar a cabo las operaciones en el servidor.  Los valores son los siguientes:<br /><br /> -   Ninguna<br />-   UseWindowsGroups<br />-   UseAspNetRoles<br />-   Personalizado<br /><br /> El valor predeterminado es UseWindowsGroups.  El valor es del tipo <xref:System.ServiceModel.Description.PrincipalPermissionMode>.  Para obtener más información sobre cómo usar este atributo, vea [Cómo restringir el acceso con la clase PrincipalPermissionAttribute](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).|  
|roleProviderName|Una cadena que especifica el nombre del proveedor de roles, que proporciona información de rol para una aplicación Windows Communication Foundation \(WCF\).  El valor predeterminado es una cadena vacía.|  
|ServiceAuthorizationManagerType|Una cadena que contiene el tipo de administrador de autorización de servicio.  Para obtener más información, consulta <xref:System.ServiceModel.ServiceAuthorizationManager>.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|authorizationPolicies|Contiene una colección de tipos de directiva de autorización, que se pueden agregar utilizando la palabra clave `add`.  Cada directiva de autorización contiene un atributo `policyType` necesario único que es una cadena.  El atributo especifica una directiva de autorización que permite la transformación de un conjunto de demandas de entrada en otro conjunto de demandas.  Se puede permitir o denegar el acceso en base a eso.  Para obtener más información, consulta <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Contiene una colección de valores para el comportamiento de un servicio.|  
  
## Comentarios  
 Esta sección contiene elementos que afectan a la autorización, a los proveedores de roles personalizados y a la suplantación.  
  
 El atributo `principalPermissionMode` especifica los grupos de usuarios que se han de utilizar al autorizar el uso de un método protegido.  El valor predeterminado es `UseWindowsGroups` y especifica que en los grupos de Windows, como "Administradores" o "Usuarios", se busca una identidad que intente obtener acceso a un recurso.  También puede especificar `UseAspNetRoles` para utilizar un proveedor de roles personalizados que se configura en el elemento \<system.web\>, como se muestra en el código siguiente.  
  
```  
<system.web>  
  <membership defaultProvider="SqlProvider"   
   userIsOnlineTimeWindow="15">  
     <providers>  
       <clear />  
       <add   
          name="SqlProvider"   
          type="System.Web.Security.SqlMembershipProvider"   
          connectionStringName="SqlConn"  
          applicationName="MembershipProvider"  
          enablePasswordRetrieval="false"  
          enablePasswordReset="false"  
          requiresQuestionAndAnswer="false"  
          requiresUniqueEmail="true"  
          passwordFormat="Hashed" />  
     </providers>  
   </membership>  
  <!-- Other configuration code not shown.-->  
</system.web>  
```  
  
 El ejemplo de código siguiente muestra el `roleProviderName` utilizado con el atributo `principalPermissionMode`.  
  
```  
<behaviors>  
   <behavior name="ServiceBehaviour">  
     <serviceAuthorization principalPermissionMode ="UseAspNetRoles"   
                           roleProviderName ="SqlProvider" />  
   </behavior>   
<!-- Other configuration code not shown. -->  
</behaviors>  
```  
  
 Para obtener un ejemplo detallado de utilizar este elemento de configuración, vea [Autorización de acceso a operaciones de servicio](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) y [Directiva de autorización](../../../../../docs/framework/wcf/samples/authorization-policy.md).  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>   
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>   
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Autorización de acceso a operaciones de servicio](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)   
 [Cómo crear un administrador de autorización personalizado para un servicio](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)   
 [Cómo restringir el acceso con la clase PrincipalPermissionAttribute](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)   
 [Directiva de autorización](../../../../../docs/framework/wcf/samples/authorization-policy.md)