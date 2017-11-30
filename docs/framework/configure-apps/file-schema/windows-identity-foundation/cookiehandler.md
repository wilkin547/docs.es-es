---
title: '&lt;cookieHandler&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 88e968d025c959ec33674a9d8edb5e63341433ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltcookiehandlergt"></a>&lt;cookieHandler&gt;
Configura el <xref:System.IdentityModel.Services.CookieHandler> que la <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) se utiliza para leer y escribir las cookies.  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
\<cookieHandler >  
  
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
|name|Especifica el nombre base para cualquier de las cookies escritas. El valor predeterminado es "FedAuth".|  
|ruta de acceso|Especifica el valor de ruta de acceso para cualquier de las cookies escritas. El valor predeterminado es "Objeto HttpRuntime.AppDomainAppVirtualPath".|  
|modo|Uno de los <xref:System.IdentityModel.Services.CookieHandlerMode> valores que especifica el tipo de controlador de cookie utilizada por el SAM. Pueden utilizarse los siguientes valores:<br /><br /> -"Default", igual que "Chunked".<br />-"Fragmentada", utiliza una instancia de la <xref:System.IdentityModel.Services.ChunkedCookieHandler> clase. Este controlador de cookies se asegura de que las cookies individuales no superen un tamaño máximo del conjunto. Para ello, "fragmentación" potencialmente una cookie lógica en un número de cookies en el cable.<br />-"Custom", utiliza una instancia de una clase personalizada derivada de <xref:System.IdentityModel.Services.CookieHandler>. Se hace referencia a la clase derivada mediante el `<customCookieHandler>` elemento secundario.<br /><br /> El valor predeterminado es "Default".|  
|persistentSessionLifetime|Especifica la duración de las sesiones persistentes. Si es cero, siempre se utilizan sesiones transitorias. El valor predeterminado es "0:0:0", que especifica una sesión transitoria. El valor máximo es "365:0:0", que especifica una sesión de 365 días. Debe especificarse el valor de acuerdo con la restricción siguiente: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, donde el valor de la izquierda especifica días, el valor medio (si existe) especifica horas y el valor más a la derecha (si existe) especifica los minutos.|  
|RequireSsl|Especifica si el marcador "Secure" se emite para cualquier de las cookies escritas. Si se establece este valor, las cookies de inicio de sesión sólo estará disponibles a través de HTTPS. El valor predeterminado es "true".|  
|hideFromScript|Controla si la marca "HttpOnly" se emite para cualquier de las cookies escritas. Algunos exploradores web respetan esta marca manteniendo el script de cliente de acceso al valor de cookie. El valor predeterminado es "true".|  
|dominio|El valor de dominio para cualquier de las cookies escritas. El valor predeterminado es "".|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<chunkedCookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md)|Configura el <xref:System.IdentityModel.Services.ChunkedCookieHandler>. Este elemento sólo puede estar presente si el `mode` atributo de la `<cookieHandler>` elemento es "Default" o "Fragmentada".|  
|[\<customCookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/customcookiehandler.md)|Establece el tipo de controlador de cookie personalizado. Este elemento debe estar presente si el `mode` atributo de la `<cookieHandler>` elemento es "Custom". No pueden estar presente para cualquier otro valor de la `mode` atributo. El tipo personalizado debe derivarse de la <xref:System.IdentityModel.Services.CookieHandler> clase.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Contiene los valores que configuran la <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>Comentarios  
 El <xref:System.IdentityModel.Services.CookieHandler> es responsable de nivel de protocolo de lectura y escritura de las cookies sin formato en HTTP. Configurar un <xref:System.IdentityModel.Services.ChunkedCookieHandler> o un controlador de cookies personalizado derivado de la <xref:System.IdentityModel.Services.CookieHandler> clase.  
  
 Para configurar un controlador de cookies fragmentado, establezca el atributo de modo que "Chunked" o "Default". El tamaño del fragmento predeterminado es 2000 bytes, pero también puede especificar un tamaño de fragmento diferente mediante la inclusión de un `<chunkedCookieHandler>` elemento secundario.  
  
 Para configurar un controlador de cookies personalizado, establezca el atributo de modo en "Custom". También debe especificar un `<customCookieHandler>` elemento secundario que hace referencia al tipo de su controlador personalizado.  
  
 El `<cookieHandler>` elemento representado por la <xref:System.IdentityModel.Services.CookieHandlerElement> clase. El controlador de cookies que se especificó en la configuración está disponible en la <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> propiedad de la <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> objeto establecido en el <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> propiedad.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra un `<cookieHandler>` elemento. En este ejemplo, porque el `mode` atributo no se especifica, se usará el controlador de cookies predeterminado por el SAM. Se trata de una instancia de la <xref:System.IdentityModel.Services.ChunkedCookieHandler> clase. Dado que el `<chunkedCookieHandler>` elemento secundario no se especifica, se utilizará el tamaño del fragmento predeterminado. HTTPS no será necesarios porque el `requireSsl` se establece el atributo `false`.  
  
> [!WARNING]
>  En este ejemplo, HTTPS no es necesario escribir las cookies de sesión. Esto es porque el `requireSsl` del atributo en el `<cookieHandler>` elemento está establecido en `false`. Esta configuración no se recomienda para la mayoría de los entornos de producción, tal y como puede suponer un riesgo de seguridad.  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IdentityModel.Services.CookieHandler>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>
