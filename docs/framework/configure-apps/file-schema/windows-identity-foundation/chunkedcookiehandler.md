---
title: "&lt;chunkedCookieHandler&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;chunkedCookieHandler&gt;
Configura el <xref:System.IdentityModel.Services.ChunkedCookieHandler>.  Este elemento sólo puede estar presente si el `mode` atributo de la `<cookieHandler>` elemento es "Predeterminado" o "Segmentado".  
  
## Sintaxis  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|chunkSize|En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  Atributo  Descripción  type  El valor predeterminado es 2000.  Obligatorio.|  
  
### Elementos secundarios  
 None  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<cookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Configura el <xref:System.IdentityModel.Services.CookieHandler> que la <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\) se utiliza para leer y escribir cookies.|  
  
## Comentarios  
 Cuando se especifica un <xref:System.IdentityModel.Services.ChunkedCookieHandler> estableciendo la `mode` atributo de la `<cookieHandler>` elemento a "Default" o "Chunked", puede especificar el tamaño del fragmento que el controlador de la cookie se utiliza para leer y escribir cookies mediante la inclusión un `<chunkedCookieHandler>` elemento secundario y configuración de su `chunkSize` atributo.  None  Elemento  
  
 Descripción  
  
## Ejemplo  
 En el ejemplo siguiente se configura un controlador de cookie fragmentada que escribe las cookies en bloques de bytes 3000.  
  
```  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## Vea también  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>