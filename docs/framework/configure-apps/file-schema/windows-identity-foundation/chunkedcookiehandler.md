---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: b3b4cf0d7c2748079af7a94534622b1dbadd3ab5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941889"
---
# <a name="chunkedcookiehandler"></a>\<chunkedCookieHandler>
Configura el <xref:System.IdentityModel.Services.ChunkedCookieHandler>. Este elemento solo puede estar presente si el `mode` atributo `<cookieHandler>` del elemento es "default" o "fragmentado".  
  
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
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|chunkSize|Tamaño máximo, en caracteres, de los datos de cookies HTTP para cualquier cookie HTTP. Debe tener cuidado al ajustar el tamaño del fragmento. Los exploradores Web tienen límites diferentes en cuanto al tamaño de las cookies y el número permitido por dominio. Por ejemplo, la especificación de Netscape original estipulaba estos límites: 300 cookies en total, 4096 bytes por encabezado de cookie (incluidos los metadatos, no solo el valor de cookie) y 20 cookies por dominio. El valor predeterminado es 2000. Necesario.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Configura el <xref:System.IdentityModel.Services.CookieHandler> <xref:System.IdentityModel.Services.SessionAuthenticationModule> que usa (SAM) para leer y escribir cookies.|  
  
## <a name="remarks"></a>Comentarios  
 Cuando se especifica un <xref:System.IdentityModel.Services.ChunkedCookieHandler> estableciendo el `mode` atributo del `<cookieHandler>` elemento en "default" o "fragmentado", se puede especificar el tamaño del fragmento que el controlador de cookies utiliza para leer y escribir cookies incluyendo `<chunkedCookieHandler>` un elemento secundario y establecer su `chunkSize` atributo. Si el `<chunkedCookieHandler>` elemento no está presente, se utiliza el tamaño de fragmento predeterminado de 2000 bytes. No se puede especificar este elemento cuando `mode` el atributo se establece en "Custom".  
  
 El elemento se representa mediante la <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> clase. `<chunkedCookieHandler>`  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se configura un controlador de cookies fragmentado que escribe cookies en fragmentos de 3000 bytes.  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
