---
title: '&lt;Análisisiri&gt; elemento (configuración de Uri)'
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f05f7e35d69f789d3ebb371689aafbc84004b732
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltiriparsinggt-element-uri-settings"></a>&lt;Análisisiri&gt; elemento (configuración de Uri)
Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) a un <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.  
  
## <a name="schema-hierarchy"></a>Jerarquía del esquema  
 [Elemento \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<URI > elemento (configuración de Uri)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<Análisisiri >](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|`enabled`|Especifica si está habilitado el análisis IRI. El valor predeterminado es `false`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[URI](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|Contiene valores que especifican cómo .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).|  
  
## <a name="remarks"></a>Comentarios  
 Existente <xref:System.Uri> clase se ha extendido en .NET Framework 3.5. 3.0 SP1 y 2.0 SP1 para proporcionar compatibilidad con identificadores de recursos internacionales (IRI) y nombres de dominio internacionalizados (IDN). Los usuarios actuales no verán ningún cambio del comportamiento de .NET Framework 2.0 a menos que habiliten específicamente IRI e IDN admite. Esto garantiza la compatibilidad de las aplicaciones con versiones anteriores de .NET Framework.  
  
 Para habilitar la compatibilidad con IRI, son necesarios los siguientes dos cambios:  
  
1.  Agregue la siguiente línea al archivo machine.config en el directorio de .NET Framework 2.0  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  Especifique si se debe aplicar las reglas de análisis IRI. Esto puede hacerse en el archivo machine.config o app.config.  
  
 Habilitar el análisis IRI (Análisisiri habilitada = `true`) realizará la normalización y las reglas de comprobación según el IRI más reciente de caracteres en el documento RFC 3987. El valor predeterminado es `false` y se la normalización y caracteres de comprobación en función de RFC 2396 y RFC 3986 (para literales de IPv6).  
  
### <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase para admitir el análisis IRI y los nombres IDN.  
  
### <a name="code"></a>Código  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
