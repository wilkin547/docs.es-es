---
title: <idn> Elemento (configuración de Uri)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 3940f30f2ef90a77560a82edc909071f0ee8e130
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129407"
---
# <a name="idn-element-uri-settings"></a>\<IDN > elemento (configuración de Uri)
Especifica si el análisis de nombres de dominio internacionalizados (IDN) se aplican a un nombre de dominio.  
  
## <a name="schema-hierarchy"></a>Jerarquía del esquema  
 [\<Configuración > elemento](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<URI > elemento (configuración de Uri)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<idn>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|**Elemento**|**Descripción**|  
|-----------------|---------------------|  
|`enabled`|Especifica que si se aplican el análisis de nombres de dominio internacionalizados (IDN) para un nombre de dominio, el valor predeterminado es none.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Elemento**|**Descripción**|  
|-----------------|---------------------|  
|[uri](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|Contiene valores que especifican cómo .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).|  
  
## <a name="remarks"></a>Comentarios  
 Existente <xref:System.Uri> se ha ampliado la clase en .NET Framework 3.5. 3.0 SP1 y 2.0 SP1 con compatibilidad para los identificadores de recursos internacionales (IRI) y los nombres de dominio internacionalizados (IDN). Los usuarios actuales no verán ningún cambio respecto al comportamiento de .NET Framework 2.0, a menos que habiliten específicamente IRI e IDN admite. Esto garantiza la compatibilidad de las aplicaciones con versiones anteriores de .NET Framework.  
  
 Para habilitar la compatibilidad con IRI, se requieren los siguientes dos cambios:  
  
1.  Agregue la siguiente línea al archivo machine.config en el directorio de .NET Framework 2.0  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  Especifique si desea analizar el nombre de dominio internacionalizado (IDN) aplicado en el nombre de dominio y si debe aplicarse las reglas de análisis de IRI. Esto puede hacerse en el archivo machine.config o app.config.  
  
 Hay tres valores posibles para IDN dependiendo de los servidores DNS que se usan:  
  
-   IDN habilitado = All  
  
     Este valor convierte cualquier nombre de dominio Unicode a su equivalente Punycode (nombres IDN).  
  
-   IDN habilitado = AllExceptIntranet  
  
     Este valor convertirá todos los nombres de dominio Unicode no en la Intranet local para que utilicen sus equivalentes Punycode (nombres IDN). En este caso para controlar los nombres internacionales en la Intranet local, los servidores DNS que se usan para la Intranet deben admitir la resolución de nombre de Unicode.  
  
-   IDN habilitado = ninguno  
  
     Este valor no convierte cualquier nombre de dominio Unicode para que se use Punycode. Este es el valor predeterminado que es coherente con el comportamiento de .NET Framework 2.0.  
  
 La activación de IDN convertirá todas la etiquetas Unicode de un nombre de dominio en sus equivalentes de Punycode. Los nombres de Punycode solo contienen caracteres ASCII y siempre empiezan con el prefijo xn--. De este modo, se admiten los servidores DNS existentes en Internet, ya que la mayoría de los servidores DNS solo admite caracteres ASCII (vea RFC 3940).  
  
### <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 El ejemplo siguiente muestra una configuración utilizada por el <xref:System.Uri> clase para admitir el análisis de IRI y nombres de IDN.  
  
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

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
