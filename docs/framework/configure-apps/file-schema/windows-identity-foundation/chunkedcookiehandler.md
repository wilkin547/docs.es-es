---
title: '&lt;chunkedCookieHandler&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: c5d526ccd48ea5e822d5d29fb38dacd895c2556c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltchunkedcookiehandlergt"></a>&lt;chunkedCookieHandler&gt;
Configura el <xref:System.IdentityModel.Services.ChunkedCookieHandler>. Este elemento sólo puede estar presente si el `mode` atributo de la `<cookieHandler>` elemento es "Default" o "Fragmentada".  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
\<cookieHandler >  
\<chunkedCookieHandler >  
  
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
|chunkSize|El tamaño máximo, en caracteres, de los datos de cookies HTTP para una cookie HTTP. Debe tener cuidado al ajustar el tamaño del fragmento. Los exploradores Web tienen distintos límites en el tamaño de las cookies y el número permitido para cada dominio. Por ejemplo, la especificación Netscape original estipulada estos límites: total de 300 cookies, 4096 bytes por encabezado cookie HTTP (incluidos los metadatos, no solo el valor de la cookie) y 20 cookies por dominio. El valor predeterminado es 2000. Requerido.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Configura el <xref:System.IdentityModel.Services.CookieHandler> que la <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) se utiliza para leer y escribir las cookies.|  
  
## <a name="remarks"></a>Comentarios  
 Cuando se especifica un <xref:System.IdentityModel.Services.ChunkedCookieHandler> estableciendo la `mode` atributo de la `<cookieHandler>` elemento a "Default" o "Chunked", puede especificar el tamaño del fragmento que usa el controlador de cookie para leer y escribir las cookies mediante la inclusión de un `<chunkedCookieHandler>` elemento secundario y establecer su `chunkSize` atributo. Si el `<chunkedCookieHandler>` elemento no está presente, se utiliza el tamaño del fragmento predeterminado de 2000 bytes. Este elemento no puede ser especificado cuando el `mode` atributo se establece en "Custom".  
  
 El `<chunkedCookieHandler>` elemento representado por la <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> clase.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se configura un controlador de cookie fragmentada que escribe las cookies en fragmentos de 3000 bytes.  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>
