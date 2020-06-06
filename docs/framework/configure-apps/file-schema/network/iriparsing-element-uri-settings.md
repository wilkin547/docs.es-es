---
title: Elemento <iriParsing> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: fd617d1b4ac8e532c6f9aeaa01465e9866b059e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "71698091"
---
# <a name="iriparsing-element-uri-settings"></a>Elemento \<iriParsing> (configuración de URI)
Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) a un <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<iriParsing>**  
  
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
|`enabled`|Especifica si está habilitado el análisis de IRI. El valor predeterminado es `false`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[uri](uri-element-uri-settings.md)|Contiene opciones que especifican cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).|  
  
## <a name="remarks"></a>Comentarios  
 La clase existente se ha <xref:System.Uri> ampliado en .NET Framework 3,5. 3,0 SP1 y 2,0 SP1 para proporcionar compatibilidad con los identificadores de recursos internacionales (IRI) y los nombres de dominio internacionalizados (IDN). Los usuarios actuales no verán ningún cambio en el comportamiento de .NET Framework 2,0 a menos que habiliten específicamente la compatibilidad con IRI e IDN. Esto garantiza la compatibilidad de las aplicaciones con versiones anteriores de .NET Framework.  
  
 Para habilitar la compatibilidad con IRI, se necesitan los dos cambios siguientes:  
  
1. Agregue la siguiente línea al archivo Machine. config en el directorio .NET Framework 2,0  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. Especifique si deben aplicarse las reglas de análisis de IRI. Esto puede hacerse en el archivo machine.config o app.config.  
  
 Al habilitar el análisis de IRI (Análisisiri Enabled = `true` ), se realizará la normalización y la comprobación de caracteres según las reglas de IRI más recientes en RFC 3987. El valor predeterminado es `false` y realizará la normalización y la comprobación de caracteres según rfc 2396 y rfc 3986 (para los literales de IPv6).  
  
### <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase para admitir el análisis de IRI y los nombres IDN.  
  
### <a name="code"></a>Código  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [Esquema de la configuración de red](index.md)
