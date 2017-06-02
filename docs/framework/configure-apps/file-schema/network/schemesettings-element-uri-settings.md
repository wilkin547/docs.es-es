---
title: "&lt;schemeSettings&gt; (Elemento, Configuraci&#243;n de URI) | Microsoft Docs"
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
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# &lt;schemeSettings&gt; (Elemento, Configuraci&#243;n de URI)
Especifica cómo se analizará <xref:System.Uri> para esquemas concretos.  
  
## Sintaxis  
  
```  
  
      <schemeSettings>   
</schemeSettings>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 None  
  
### Elementos secundarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[agregar](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-schemesettings-uri-settings.md)|Agrega un valor de esquema para un nombre de esquema.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-schemesettings-uri-settings.md)|Desactiva todos los valores de esquema existentes.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-schemesettings-uri-settings.md)|Quita un valor de esquema de un nombre de esquema.|  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[uri](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|Contiene los valores que especifican el modo en que .NET Framework administra las direcciones web expresadas mediante identificadores uniformes de recursos \(URI\).|  
  
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
  
## Información de elemento  
  
|||  
|-|-|  
|Espacio de nombres|Sistema|  
|Nombre de esquema||  
|Archivo de validación||  
|Puede estar vacío||  
  
## Vea también  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=fullName>   
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=fullName>   
 <xref:System.Configuration.UriSection?displayProperty=fullName>   
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=fullName>   
 <xref:System.GenericUriParserOptions?displayProperty=fullName>   
 <xref:System.Uri?displayProperty=fullName>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)