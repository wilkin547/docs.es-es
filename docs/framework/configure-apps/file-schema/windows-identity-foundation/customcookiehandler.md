---
title: "&lt;customCookieHandler&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# &lt;customCookieHandler&gt;
Opcional.  Este elemento sólo puede estar presente si el `mode` atributo de la `<cookieHandler>` elemento es "Custom".  None  
  
## Sintaxis  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode=”Custom”>  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|type|Elemento  Descripción|  
  
### Elementos secundarios  
 None  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<cookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Configura el <xref:System.IdentityModel.Services.CookieHandler> que la <xref:System.IdentityModel.Services.SessionAuthenticationModule> se utiliza para leer y escribir cookies.|  
  
## Comentarios  
 Cuando se especifica un controlador personalizado cookie estableciendo la `mode` atributo de la `<cookieHandler>` elemento a "Personalizado", debe especificar el tipo de controlador de cookie personalizado incluyendo un `<customCookieHandler>` elemento secundario que hace referencia al tipo de controlador de la cookie.  Este elemento no puede ser especificado cuando el `mode` atributo se establece en "Chunked" o "Default".  Los controladores de cookie personalizado deben derivar de la <xref:System.IdentityModel.Services.CookieHandler> clase.  
  
 El `<customCookieHandler>` elemento está representado por el <xref:System.IdentityModel.Configuration.CustomTypeElement> clase.  
  
## Ejemplo  
 Para obtener más información, vea la documentación de la clase `MyNamespace.MyCustomCookieHandler`.  
  
```  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## Vea también  
 <xref:System.IdentityModel.Services.CookieHandler>