---
title: "&lt;Uri&gt; (Elemento, configuraci&#243;n de Uri) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;Uri&gt; (Elemento, configuraci&#243;n de Uri)
Contiene los valores que especifican el modo en que .NET Framework administra las direcciones web expresadas mediante identificadores uniformes de recursos \(URI\).  
  
## Jerarquía del esquema  
 [Elemento \<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<uri\>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## Sintaxis  
  
```  
<uri>  
</uri>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[idn](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|Especifica si el análisis de nombres de dominio internacionalizados \(IDN\) se aplica a los nombres de dominio.|  
|[el iriParsing](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|Especifica si el análisis de identificadores de recursos internacionales \(IRI\) se aplica a <xref:System.Uri> y si deben aplicarse las reglas de análisis IRI.|  
|[schemeSettings](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|Especifica cómo se analizará <xref:System.Uri> para esquemas concretos.|  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[configuration](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Contiene los valores de configuración para todos los espacios de nombres.|  
  
## Comentarios  
 El elemento `uri` contiene los valores de los miembros de la clase <xref:System.Uri> que se utilizan en las clases del espacio de nombres <xref:System.Net>.  Estos valores definen la compatibilidad con IRI e IDN.  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo de código siguiente se muestra una configuración que la clase <xref:System.Uri> utiliza para proporcionar compatibilidad con el análisis IRI y los nombres IDN.  En el ejemplo también se borra toda la configuración de esquema y después se agrega compatibilidad para delimitadores de ruta de acceso del esquema http con codificación de porcentaje cuando no se trata de caracteres de escape.  
  
### Código  
  
```  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)