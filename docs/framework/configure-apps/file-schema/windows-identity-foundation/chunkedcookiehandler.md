---
description: 'Más información acerca de: <chunkedCookieHandler>'
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: b0090706d3d7a9f62e17ae63ec16e4b3a869a812
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664293"
---
# \<chunkedCookieHandler>

Configura el <xref:System.IdentityModel.Services.ChunkedCookieHandler> . Este elemento solo puede estar presente si el `mode` atributo del `<cookieHandler>` elemento es "default" o "fragmentado".  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<chunkedCookieHandler>**  
  
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
|chunkSize|Tamaño máximo, en caracteres, de los datos de cookies HTTP para cualquier cookie HTTP. Debe tener cuidado al ajustar el tamaño del fragmento. Los exploradores Web tienen límites diferentes en cuanto al tamaño de las cookies y el número permitido por dominio. Por ejemplo, la especificación de Netscape original estipulaba estos límites: 300 cookies total, 4096 bytes por encabezado de cookie (incluidos los metadatos, no solo el valor de cookie) y 20 cookies por dominio. El valor predeterminado es 2000. Necesario.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Configura el <xref:System.IdentityModel.Services.CookieHandler> que <xref:System.IdentityModel.Services.SessionAuthenticationModule> usa (SAM) para leer y escribir cookies.|  
  
## <a name="remarks"></a>Observaciones  

 Cuando se especifica un estableciendo <xref:System.IdentityModel.Services.ChunkedCookieHandler> el `mode` atributo del `<cookieHandler>` elemento en "default" o "fragmentado", se puede especificar el tamaño del fragmento que el controlador de cookies utiliza para leer y escribir cookies incluyendo un `<chunkedCookieHandler>` elemento secundario y estableciendo su `chunkSize` atributo. Si el `<chunkedCookieHandler>` elemento no está presente, se utiliza el tamaño de fragmento predeterminado de 2000 bytes. No se puede especificar este elemento cuando el `mode` atributo se establece en "Custom".  
  
 El `<chunkedCookieHandler>` elemento se representa mediante la <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> clase.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se configura un controlador de cookies fragmentado que escribe cookies en fragmentos de 3000 bytes.  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
