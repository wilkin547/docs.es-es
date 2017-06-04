---
title: "&lt;iriParsing&gt; (Elemento, Configuraci&#243;n de Uri) | Microsoft Docs"
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
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# &lt;iriParsing&gt; (Elemento, Configuraci&#243;n de Uri)
Especifica si el análisis de identificadores de recursos internacionales \(IRI\) se aplica a <xref:System.Uri> y si deben aplicarse las reglas de análisis IRI.  
  
## Jerarquía del esquema  
 [Elemento \<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<Uri\> \(Elemento, configuración de Uri\)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<iriParsing\>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## Sintaxis  
  
```  
<idn  
  enabled="true|false"  
/idn>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|`enabled`|Especifica si el análisis IRI está habilitado.  El valor predeterminado es `false`.|  
  
### Elementos secundarios  
 None  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[uri](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|Contiene los valores que especifican el modo en que .NET Framework administra las direcciones web expresadas mediante identificadores uniformes de recursos \(URI\).|  
  
## Comentarios  
 La clase <xref:System.Uri> existente se ha extendido en .NET Framework 3.5 3.0 SP1 y 2.0 SP1 para proporcionar compatibilidad con los identificadores de recursos internacionales \(IRI\) y los nombres de dominio internacionalizados \(IDN\).  Los usuarios actuales no percibirán ningún cambio en el comportamiento de .NET Framework 2.0 a menos que habiliten específicamente la compatibilidad con IRI e IDN.  De este modo, queda garantizada la compatibilidad de la aplicación con las versiones anteriores de .NET Framework.  
  
 Para habilitar la compatibilidad con los IRI, es preciso realizar los dos siguientes cambios:  
  
1.  Agregar la siguiente línea al archivo machine.config bajo el directorio de .NET Framework 2.0  
  
    ```  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  Especificar si deben aplicarse las reglas de análisis IRI.  Esto puede hacerse en el archivo machine.config o app.config.  
  
 Al habilitar el análisis IRI \(iriParsing enabled \= `true`\), la normalización y la comprobación de caracteres se realizarán de acuerdo con las últimas reglas IRI de RFC 3987.  El valor predeterminado es `false`, por lo que la normalización y la comprobación de caracteres se realizarán de acuerdo con RFC 2396 y RFC 3986 \(para literales de IPv6\).  
  
### Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo de código siguiente se muestra una configuración que la clase <xref:System.Uri> utiliza para proporcionar compatibilidad con el análisis IRI y los nombres IDN.  
  
### Código  
  
```  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Configuration.IriParsingElement?displayProperty=fullName>   
 <xref:System.Configuration.UriSection?displayProperty=fullName>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)