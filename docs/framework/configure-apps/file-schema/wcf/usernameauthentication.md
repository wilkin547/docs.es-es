---
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: 30fd78d6c56e8b22e0e744a38f18ac076dc70162
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178039"
---
# \<userNameAuthentication>

Especifica las credenciales de un servicio basadas en el nombre de usuario y contraseña.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameAuthentication>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<xref:System.TimeSpan> que especifica la duración máxima que un token está almacenado en la memoria caché. El valor predeterminado es 00:15:00.|  
|`cacheLogonTokens`|Un valor booleano que especifica si los tokens de inicio de sesión están almacenados en memoria caché. El valor predeterminado es `false`.|  
|`customUserNamePasswordValidatorType`|Una cadena que especifica el tipo de validador de contraseña de nombre de usuario personalizado que se va a utilizar. El valor predeterminado es una cadena vacía.|  
|`includeWindowsGroups`|Un valor booleano que especifica si los grupos de Windows están incluidos en el contexto de seguridad. El valor predeterminado es `true`.<br /><br /> Al establecer este atributo en `true`, se tiene un impacto de rendimiento y tiene como resultado una expansión de grupo completa. Establezca esta propiedad en `false` si no necesita establecer la lista de grupos a los que un usuario pertenece.|  
|`maxCacheLogonTokens`|Un entero que especifica el número máximo de tokens de inicio de sesión para almacenar en memoria caché. Este valor debería ser mayor que cero. El valor predeterminado es 128.|  
|`membershipProviderName`|Cuando el atributo `clientCredentialType` de un enlace está establecido en `username`, el nombre de usuario está asignado a las cuentas de Windows. Puede invalidar este comportamiento mediante este atributo, que es una cadena que contiene el nombre del valor <xref:System.Web.Security.MembershipProvider> que proporciona el mecanismo de validación de contraseña pertinente.|  
|`userNamePasswordValidationMode`|Especifica la manera en la que se valida la contraseña del nombre de usuario. Los valores válidos son:<br /><br /> -Windows<br />-MembershipProvider<br />-Personalizado<br /><br /> El valor predeterminado es Windows. Este atributo es del tipo <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.|  
  
## <a name="remarks"></a>Observaciones  

 Si ninguno de los enlaces utilizados por un servicio se configura para la autenticación mediante el nombre de usuario/contraseña, se omiten los atributos para este elemento. Entre estos se incluyen los eventos `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName` y `userNamePasswordValidationMode`.  
  
 Si ninguno de los enlaces utilizados por un servicio configurado para utilizar la autenticación de Windows para el nombre de usuario/contraseña, se omite la configuración relacionada con almacenar en memoria caché los tokens de inicio de sesión. Éstos incluyen `cacheLogonTokenLifetime`, `cacheLogonTokens` y `maxCacheLogonTokens`.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
