---
title: "&lt;add&gt; (Elemento para schemeSettings, Configuraci&#243;n de URI) | Microsoft Docs"
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
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# &lt;add&gt; (Elemento para schemeSettings, Configuraci&#243;n de URI)
Agrega un valor de esquema para un nombre de esquema.  
  
## Sintaxis  
  
```  
  
      <add   
   name = "http|https" genericUriParserOptions="DontUnescapePathDotsAndSlashes"  
/>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|nombre|El nombre de esquema para el que se aplica este valor.  Los únicos valores compatibles son name\="http" y name\="https".|  
  
## Atributo {nombre del atributo}  
  
|Valor|Descripción|  
|-----------|-----------------|  
|genericUriParserOptions|Las opciones de analizador de este esquema.  El único valor compatible es genericUriParserOptions\= "DontUnescapePathDotsAndSlashes".|  
  
### Elementos secundarios  
 None  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<schemeSettings\> \(Elemento, Configuración de URI\)](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|Especifica cómo se analizará <xref:System.Uri> para esquemas concretos.|  
  
## Comentarios  
 De forma predeterminada, la clase <xref:System.Uri?displayProperty=fullName> quita los caracteres de escape de los delimitadores de ruta de acceso codificados con porcentaje antes de ejecutar la compresión de la ruta de acceso.  Esto se implementó como un mecanismo de seguridad frente a ataques como el siguiente:  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Si este URI se pasa a los módulos sin controlar correctamente los caracteres codificados con porcentaje, podría ocurrir que el servidor ejecute el comando siguiente:  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 Por esta razón, la clase <xref:System.Uri?displayProperty=fullName> primero quita los caracteres de escape de los delimitadores de ruta de acceso y, a continuación, aplica la compresión de la ruta de acceso.  El resultado de pasar la dirección URL malintencionada anterior al constructor de clase <xref:System.Uri?displayProperty=fullName> produce el URI siguiente:  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Este comportamiento predeterminado se puede modificar para no quitar los caracteres de escape de los delimitadores de ruta de acceso codificados con porcentaje utilizando la opción de configuración schemeSettings para un esquema concreto.  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 El ejemplo de código siguiente muestra una configuración utilizada por la clase <xref:System.Uri> para permitir delimitadores de ruta de acceso con codificación de porcentaje para el esquema http.  
  
```  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=fullName>   
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=fullName>   
 <xref:System.Configuration.UriSection?displayProperty=fullName>   
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=fullName>   
 <xref:System.GenericUriParserOptions?displayProperty=fullName>   
 <xref:System.Uri?displayProperty=fullName>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)