---
title: <cookieHandler>
ms.date: 03/30/2017
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
author: BrucePerlerMS
ms.openlocfilehash: 853dc9817d080e59ac7a792576eda862bd0b1f1d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252024"
---
# \<cookieHandler>
Configura el <xref:System.IdentityModel.Services.CookieHandler> que <xref:System.IdentityModel.Services.SessionAuthenticationModule> usa (SAM) para leer y escribir cookies.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cookieHandler>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler name=xs:string  
        path=Path  
        mode="Chunked||Custom||Default"  
        persistentSessionLifetime=xs:string  
        hideFromScript=xs:boolean  
        requireSSL=xs:boolean  
        domain=xs:string  
      <chunkedCookieHandler size=xs:int />  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|name|Especifica el nombre base para las cookies escritas. El valor predeterminado es "FedAuth".|  
|path|Especifica el valor de la ruta de acceso de las cookies escritas. El valor predeterminado es "HttpRuntime. AppDomainAppVirtualPath".|  
|mode|Uno de los <xref:System.IdentityModel.Services.CookieHandlerMode> valores de que especifica el tipo de controlador de cookies utilizado por el SAM. Se pueden usar los valores siguientes:<br /><br /> -"Predeterminado": igual que "fragmentada".<br />-"Fragmentado": utiliza una instancia de la <xref:System.IdentityModel.Services.ChunkedCookieHandler> clase. Este controlador de cookies garantiza que las cookies individuales no superen un tamaño máximo establecido. Para ello, podría "fragmentar" una cookie lógica en varias cookies en el cable.<br />-"Custom": utiliza una instancia de una clase personalizada derivada de <xref:System.IdentityModel.Services.CookieHandler> . El elemento secundario hace referencia a la clase derivada `<customCookieHandler>` .<br /><br /> El valor predeterminado es "default".|  
|persistentSessionLifetime|Especifica la duración de las sesiones persistentes. Si es cero, siempre se usan sesiones transitorias. El valor predeterminado es "0:0:0", que especifica una sesión transitoria. El valor máximo es "365:0:0", que especifica una sesión de 365 días. El valor debe especificarse según la restricción siguiente: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />` , donde el valor más a la izquierda especifica los días, el valor medio (si está presente) especifica las horas y el valor más a la derecha (si está presente) especifica minutos.|  
|requireSsl|Especifica si se emite la marca "Secure" para las cookies escritas. Si se establece este valor, las cookies de la sesión de inicio de sesión solo estarán disponibles a través de HTTPS. El valor predeterminado es "true".|  
|hideFromScript|Controla si se emite la marca "HttpOnly" para las cookies escritas. Algunos exploradores Web respetan esta marca manteniendo el script del lado cliente en el acceso al valor de la cookie. El valor predeterminado es "true".|  
|dominio|El valor de dominio para las cookies escritas. El valor predeterminado es "".|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<chunkedCookieHandler>](chunkedcookiehandler.md)|Configura el <xref:System.IdentityModel.Services.ChunkedCookieHandler> . Este elemento solo puede estar presente si el `mode` atributo del `<cookieHandler>` elemento es "default" o "fragmentado".|  
|[\<customCookieHandler>](customcookiehandler.md)|Establece el tipo de controlador de cookies personalizado. Este elemento debe estar presente si el `mode` atributo del `<cookieHandler>` elemento es "Custom". No puede estar presente para ningún otro valor del `mode` atributo. El tipo personalizado se debe derivar de la <xref:System.IdentityModel.Services.CookieHandler> clase.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Contiene la configuración que configura el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y el <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>Comentarios  
 El <xref:System.IdentityModel.Services.CookieHandler> es responsable de leer y escribir las cookies sin formato en el nivel de protocolo http. Puede configurar un <xref:System.IdentityModel.Services.ChunkedCookieHandler> o un controlador de cookies personalizado derivado de la <xref:System.IdentityModel.Services.CookieHandler> clase.  
  
 Para configurar un controlador de cookies fragmentado, establezca el atributo de modo en "fragmentado" o "predeterminado". El tamaño de fragmento predeterminado es de 2000 bytes, pero opcionalmente puede especificar un tamaño de fragmento diferente si incluye un `<chunkedCookieHandler>` elemento secundario.  
  
 Para configurar un controlador de cookies personalizado, establezca el atributo MODE en "Custom". También debe especificar un `<customCookieHandler>` elemento secundario que haga referencia al tipo del controlador personalizado.  
  
 El `<cookieHandler>` elemento se representa mediante la <xref:System.IdentityModel.Services.CookieHandlerElement> clase. El controlador de cookies que se especificó en la configuración está disponible en la <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> propiedad del <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> conjunto de objetos de la <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> propiedad.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código XML muestra un `<cookieHandler>` elemento. En este ejemplo, dado que `mode` no se especifica el atributo, el SAM usará el controlador de cookies predeterminado. Se trata de una instancia de la <xref:System.IdentityModel.Services.ChunkedCookieHandler> clase. Dado que `<chunkedCookieHandler>` no se especifica el elemento secundario, se usará el tamaño de fragmento predeterminado. HTTPS no será necesario porque el `requireSsl` atributo está establecido `false` .  
  
> [!WARNING]
> En este ejemplo, no se requiere HTTPS para escribir cookies de sesión. Esto se debe `requireSsl` a que el atributo del `<cookieHandler>` elemento se establece en `false` . Esta configuración no se recomienda para la mayoría de los entornos de producción, ya que puede suponer un riesgo para la seguridad.  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.IdentityModel.Services.CookieHandler>
- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
