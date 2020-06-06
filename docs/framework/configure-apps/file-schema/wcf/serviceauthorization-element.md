---
title: <serviceAuthorization> (elemento)
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: f476f754a340f52859be2986e42754cba0ef3771
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "71834019"
---
# <a name="serviceauthorization-element"></a>Elemento \<serviceAuthorization>

Especifica valores que autorizan que el acceso repare las operaciones

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthorization>**  

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

En las secciones siguientes se describen los atributos, los elementos secundarios y los elementos primarios:

### <a name="attributes"></a>Atributos

|Atributo|Descripción|  
|---------------|-----------------|  
|impersonateCallerForAllOperations|Un valor booleano que especifica si todas las operaciones en el servicio suplantan al autor de la llamada. De manera predeterminada, es `false`.<br /><br /> Cuando una operación de servicio concreta suplanta al llamador, el contexto del subproceso se intercambia al contexto del llamador antes de ejecutar el servicio especificado.|  
|principalPermissionMode|Establece la entidad de seguridad usada para llevar a cabo las operaciones en el servidor. Los valores son los siguientes:<br /><br /> -Ninguno<br />-UseWindowsGroups<br />-UseAspNetRoles<br />-Personalizado<br /><br /> El valor predeterminado es UseWindowsGroups. El valor es del tipo <xref:System.ServiceModel.Description.PrincipalPermissionMode>. Para obtener más información sobre el uso de este atributo, vea [Cómo: restringir el acceso con la clase PrincipalPermissionAttribute](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).|  
|roleProviderName|Una cadena que especifica el nombre del proveedor de roles, que proporciona información de rol para una aplicación Windows Communication Foundation (WCF). El valor predeterminado es una cadena vacía.|  
|ServiceAuthorizationManagerType|Una cadena que contiene el tipo de administrador de autorización de servicio. Para obtener más información, vea <xref:System.ServiceModel.ServiceAuthorizationManager>.|  

### <a name="child-elements"></a>Elementos secundarios

|Elemento|Descripción|  
|-------------|-----------------|  
|authorizationPolicies|Contiene una colección de tipos de directiva de autorización, que se pueden agregar utilizando la palabra clave `add`. Cada directiva de autorización contiene un atributo `policyType` necesario único que es una cadena. El atributo especifica una directiva de autorización que permite la transformación de un conjunto de demandas de entrada en otro conjunto de demandas. Se puede permitir o denegar el acceso en base a eso. Para obtener más información, vea <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.|  

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Contiene una colección de valores para el comportamiento de un servicio.|  

## <a name="remarks"></a>Comentarios

Esta sección contiene elementos que afectan a la autorización, a los proveedores de roles personalizados y a la suplantación.  
  
El atributo `principalPermissionMode` especifica los grupos de usuarios que se han de utilizar al autorizar el uso de un método protegido. El valor predeterminado es `UseWindowsGroups` y especifica que en los grupos de Windows, como "Administradores" o "Usuarios", se busca una identidad que intente obtener acceso a un recurso. También puede especificar `UseAspNetRoles` que se use un proveedor de roles personalizado que esté configurado en el \<system.web> elemento, como se muestra en el código siguiente:

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
  
En el código siguiente se muestra el `roleProviderName` utilizado con el `principalPermissionMode` atributo:
  
```xml
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```

Para obtener un ejemplo detallado del uso de este elemento de configuración, vea [autorizar el acceso a las operaciones de servicio y a](../../../wcf/samples/authorizing-access-to-service-operations.md) la [Directiva de autorización](../../../wcf/samples/authorization-policy.md).
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [Comportamientos de seguridad](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Autorización de acceso a operaciones de servicio](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [Procedimiento para crear un administrador de autorización personalizado para un servicio](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [Procedimiento para restringir el acceso con la clase PrincipalPermissionAttribute](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [Directiva de autorización](../../../wcf/samples/authorization-policy.md)
