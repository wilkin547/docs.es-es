---
title: "&lt;serviceTokenResolver&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;serviceTokenResolver&gt;
Registra a la resolución de símbolo \(token\) de servicio que utiliza controladores en la colección de controladores de símbolo \(token\).  La resolución del servicio de símbolo \(token\) se utiliza para resolver el token de cifrado de mensajes y los tokens entrantes.  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|type|Especifica el tipo de la resolución de símbolo \(token\) de servicio.  Ya sea la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> tipo o un tipo que se deriva de la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase.  Para obtener más información acerca de cómo especificar el `type` de atributo, consulte [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).  Obligatorio.|  
  
### Elementos secundarios  
 None  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Proporciona la configuración de una colección de seguridad de los controladores de símbolo \(token\).|  
  
## Comentarios  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  Atributo  Descripción  type  
  
 Algunos controladores de símbolo \(token\) permiten especificar la configuración de resolución de símbolo \(token\) de servicio en la configuración.  Valor sobre los controladores de símbolo \(token\) individuales reemplaza a los especificados en la colección de controladores de token de seguridad.  
  
> [!NOTE]
>  Especificación de la `<serviceTokenResolver>` elemento como elemento secundario de la [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento se ha degradado, pero todavía se admite por compatibilidad con versiones anteriores.  Elemento  
  
## Ejemplo  
  
```  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```