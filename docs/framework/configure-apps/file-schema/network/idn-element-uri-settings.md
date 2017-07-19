---
title: "&lt;idn&gt; (Elemento, Configuraci&#243;n de Uri) | Microsoft Docs"
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
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;idn&gt; (Elemento, Configuraci&#243;n de Uri)
Especifica si el análisis de nombres de dominio internacionalizados \(IDN\) se aplica a un nombre de dominio.  
  
## Jerarquía del esquema  
 [Elemento \<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<Uri\> \(Elemento, configuración de Uri\)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<idn\>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## Sintaxis  
  
```  
<idn  
  enabled="All|AllExceptIntranet|None"  
/idn>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|`enabled`|Especifica si el análisis de nombres de dominio internacionalizados \(IDN\) se aplica a un nombre de dominio. El valor predeterminado es none.|  
  
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
  
2.  Especificar si se desea aplicar el análisis IDN \(nombres de dominio internacionalizados\) al nombre de dominio y si deben aplicarse las reglas de análisis IRI.  Esto puede hacerse en el archivo machine.config o app.config.  
  
 Hay tres valores posibles para IDN según los servidores DNS que se usen:  
  
-   idn enabled \= All  
  
     Este valor convierte cualquier nombre de dominio Unicode a su equivalente Punycode \(nombres IDN\).  
  
-   idn enabled \= AllExceptIntranet  
  
     Este valor convertirá todos los nombres de dominio Unicode que no estén en la intranet local para que se utilicen sus equivalentes \(nombres IDN\).  En este caso, para administrar los nombres internacionales en la intranet local, los servidores DNS que se utilizan para la intranet deben admitir la resolución de nombres Unicode.  
  
-   idn enabled \= None  
  
     Este valor no convierte ningún nombre de dominio Unicode para que se use Punycode.  Éste es el valor predeterminado, que es coherente con el comportamiento de .NET Framework 2.0.  
  
 Al habilitar IDN, todas las etiquetas Unicode de un nombre de dominio se convertirán en sus equivalentes Punycode.  Los nombres Punycode sólo contienen caracteres ASCII y siempre empiezan con el prefijo xn\-\-.  De este modo, se proporciona compatibilidad con los servidores DNS existentes en Internet, dado que la mayoría de estos servidores sólo admiten caracteres ASCII \(vea RFC 3940\).  
  
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
 <xref:System.Configuration.IdnElement?displayProperty=fullName>   
 <xref:System.Configuration.UriSection?displayProperty=fullName>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)