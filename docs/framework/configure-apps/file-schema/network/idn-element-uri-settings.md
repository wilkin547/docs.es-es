---
title: '&lt;IDN&gt; elemento (configuración de Uri)'
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 17f68fbb92797928be911e530232e8638793687f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742577"
---
# <a name="ltidngt-element-uri-settings"></a>&lt;IDN&gt; elemento (configuración de Uri)
Especifica si el análisis de nombre de dominio internacionalizado (IDN) se aplica a un nombre de dominio.  
  
## <a name="schema-hierarchy"></a>Jerarquía del esquema  
 [Elemento \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<URI > elemento (configuración de Uri)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<IDN >](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|`enabled`|Especifica que si el análisis de nombre de dominio internacionalizado (IDN) se aplica a un nombre de dominio el valor predeterminado es none.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[URI](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|Contiene valores que especifican cómo .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).|  
  
## <a name="remarks"></a>Comentarios  
 Existente <xref:System.Uri> clase se ha extendido en .NET Framework 3.5. 3.0 SP1 y 2.0 SP1 con compatibilidad con identificadores de recursos internacionales (IRI) y nombres de dominio internacionalizados (IDN). Los usuarios actuales no verán ningún cambio del comportamiento de .NET Framework 2.0 a menos que habiliten específicamente IRI e IDN admite. Esto garantiza la compatibilidad de las aplicaciones con versiones anteriores de .NET Framework.  
  
 Para habilitar la compatibilidad con IRI, son necesarios los siguientes dos cambios:  
  
1.  Agregue la siguiente línea al archivo machine.config en el directorio de .NET Framework 2.0  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  Especifique si desea analizar el nombre de dominio internacionalizado (IDN) aplica para el nombre de dominio y si se debe aplicar las reglas de análisis IRI. Esto puede hacerse en el archivo machine.config o app.config.  
  
 Hay tres valores posibles para IDN según los servidores DNS que se utilizan:  
  
-   IDN habilitada = All  
  
     Este valor convertirá los nombres de dominio Unicode en su equivalente Punycode (nombres IDN).  
  
-   IDN habilitada = AllExceptIntranet  
  
     Este valor convertirá todos los nombres de dominio Unicode no estén en la Intranet local para que utilicen sus equivalentes Punycode (nombres IDN). En este caso, para administrar los nombres internacionales en la Intranet local, los servidores DNS que se utilizan para la Intranet deben admitir la resolución de nombre de Unicode.  
  
-   IDN habilitada = ninguno  
  
     Este valor no convierte los nombres de dominio Unicode usar Punycode. Este es el valor predeterminado que es coherente con el comportamiento de .NET Framework 2.0.  
  
 La activación de IDN convertirá todas la etiquetas Unicode de un nombre de dominio en sus equivalentes de Punycode. Los nombres de Punycode solo contienen caracteres ASCII y siempre empiezan con el prefijo xn--. De este modo, se admiten los servidores DNS existentes en Internet, ya que la mayoría de los servidores DNS solo admite caracteres ASCII (vea RFC 3940).  
  
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
 <xref:System.Configuration.IdnElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
