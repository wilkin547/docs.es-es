---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: d9c81d5de7bea343f0d67fa00037763fbae7b8c5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120788"
---
# <a name="chunkedcookiehandler"></a>\<chunkedCookieHandler>
Configura el <xref:System.IdentityModel.Services.ChunkedCookieHandler>. Este elemento solo puede estar presente si el `mode` atributo de la `<cookieHandler>` elemento es "Default" o "Fragmentada".  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<cookieHandler>  
\<chunkedCookieHandler>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|chunkSize|El tamaño máximo, en caracteres, de los datos de cookies HTTP para una cookie HTTP. Debe tener cuidado cuando ajuste el tamaño del fragmento. Los exploradores Web tienen distintos límites en el tamaño de las cookies y el número permitido por dominio. Por ejemplo, la especificación de Netscape original había estipulada estos límites: total de 300 cookies 4096 bytes por encabezado de cookie (incluidos los metadatos, no solo el valor de cookie) y 20 cookies por dominio. El valor predeterminado es 2000. Obligatorio.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<cookieHandler>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Configura el <xref:System.IdentityModel.Services.CookieHandler> que el <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) se usa para leer y escribir cookies.|  
  
## <a name="remarks"></a>Comentarios  
 Cuando se especifica un <xref:System.IdentityModel.Services.ChunkedCookieHandler> estableciendo el `mode` atributo de la `<cookieHandler>` elemento va a "Default" o "Chunked", puede especificar el tamaño del fragmento que usa el controlador de cookies para leer y escribir las cookies mediante la inclusión de un `<chunkedCookieHandler>` elemento secundario y establecer su `chunkSize` atributo. Si el `<chunkedCookieHandler>` elemento no está presente, se utiliza el tamaño del fragmento predeterminado de 2000 bytes. Este elemento no puede ser que se especificó cuando la `mode` atributo está establecido en "Custom".  
  
 El `<chunkedCookieHandler>` elemento representado por la <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> clase.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente configura un controlador de cookies fragmentado que escribe las cookies en fragmentos de 3000 bytes.  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
