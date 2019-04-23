---
title: Elemento <serviceAuthorization>
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: 7099c5eca9cf28624153a705e4e16136628214a2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157352"
---
# <a name="serviceauthorization-element"></a>\<serviceAuthorization > elemento
Especifica valores que autorizan que el acceso repare las operaciones  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<serviceBehaviors>  
\<comportamiento >  
\<serviceAuthorization>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<serviceAuthorization impersonateCallerForAllOperations="Boolean"
                      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"
                      roleProviderName="String"
                      serviceAuthorizationManagerType="String">
  <authorizationPolicies>
    <add policyType="String" />
  </authorizationPolicies>
</serviceAuthorization>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|impersonateCallerForAllOperations|Un valor booleano que especifica si todas las operaciones en el servicio suplantan al autor de la llamada. De manera predeterminada, es `false`.<br /><br /> Cuando una operación de servicio concreta suplanta al llamador, el contexto del subproceso se intercambia al contexto del llamador antes de ejecutar el servicio especificado.|  
|principalPermissionMode|Establece la entidad de seguridad usada para llevar a cabo las operaciones en el servidor. Los valores son los siguientes:<br /><br /> -None<br />-   UseWindowsGroups<br />-   UseAspNetRoles<br />-Custom<br /><br /> El valor predeterminado es UseWindowsGroups. El valor es del tipo <xref:System.ServiceModel.Description.PrincipalPermissionMode>. Para obtener más información sobre el uso de este atributo, vea [Cómo: Restringir el acceso con la clase PrincipalPermissionAttribute](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).|  
|roleProviderName|Una cadena que especifica el nombre del proveedor de roles, que proporciona información de rol para una aplicación Windows Communication Foundation (WCF). El valor predeterminado es una cadena vacía.|  
|ServiceAuthorizationManagerType|Una cadena que contiene el tipo de administrador de autorización de servicio. Para obtener más información, consulta <xref:System.ServiceModel.ServiceAuthorizationManager>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|authorizationPolicies|Contiene una colección de tipos de directiva de autorización, que se pueden agregar utilizando la palabra clave `add`. Cada directiva de autorización contiene un atributo `policyType` necesario único que es una cadena. El atributo especifica una directiva de autorización que permite la transformación de un conjunto de demandas de entrada en otro conjunto de demandas. Se puede permitir o denegar el acceso en base a eso. Para obtener más información, consulta <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Contiene una colección de valores para el comportamiento de un servicio.|  
  
## <a name="remarks"></a>Comentarios  
 Esta sección contiene elementos que afectan a la autorización, a los proveedores de roles personalizados y a la suplantación.  
  
 El atributo `principalPermissionMode` especifica los grupos de usuarios que se han de utilizar al autorizar el uso de un método protegido. El valor predeterminado es `UseWindowsGroups` y especifica que en los grupos de Windows, como "Administradores" o "Usuarios", se busca una identidad que intente obtener acceso a un recurso. También puede especificar `UseAspNetRoles` para usar un proveedor de roles personalizados que se configura bajo el \<system.web > elemento, como se muestra en el código siguiente.  
  
```xml  
<system.web>
  <membership defaultProvider="SqlProvider"
              userIsOnlineTimeWindow="15">
    <providers>
      <clear />
      <add name="SqlProvider"
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
  <!-- Other configuration code not shown. -->
</system.web>
```  
  
 El ejemplo de código siguiente muestra el `roleProviderName` utilizado con el atributo `principalPermissionMode`.  
  
```xml  
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```  
  
 Para obtener un ejemplo detallado del uso de este elemento de configuración, consulte [autorizar el acceso a las operaciones de servicio](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) y [directiva de autorización](../../../../../docs/framework/wcf/samples/authorization-policy.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Autorización de acceso a operaciones de servicio](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [Cómo: Crear un administrador de autorización personalizado para un servicio](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [Cómo: Restringir el acceso con la clase PrincipalPermissionAttribute](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [Directiva de autorización](../../../../../docs/framework/wcf/samples/authorization-policy.md)
