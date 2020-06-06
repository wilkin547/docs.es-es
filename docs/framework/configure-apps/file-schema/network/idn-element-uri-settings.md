---
title: Elemento <idn> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 533b2562f6e5c8d6c2bf452e56dff9a8bf8ab376
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "71698172"
---
# <a name="idn-element-uri-settings"></a>Elemento \<idn> (configuración de URI)

Especifica si el análisis de nombres de dominio internacionalizados (IDN) se aplica a un nombre de dominio.
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<idn>**  
  
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
|`enabled`|Especifica si el análisis de nombres de dominio internacionalizados (IDN) se aplica a un nombre de dominio. el valor predeterminado es None.|  

### <a name="child-elements"></a>Elementos secundarios

None
  
### <a name="parent-elements"></a>Elementos primarios

|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[uri](uri-element-uri-settings.md)|Contiene opciones que especifican cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).|  

## <a name="remarks"></a>Comentarios

La clase existente se ha <xref:System.Uri> ampliado en .NET Framework 3,5. 3,0 SP1 y 2,0 SP1 compatible con los identificadores de recursos internacionales (IRI) y los nombres de dominio internacionalizados (IDN). Los usuarios actuales no verán ningún cambio en el comportamiento de .NET Framework 2,0 a menos que habiliten específicamente la compatibilidad con IRI e IDN. Esto garantiza la compatibilidad de las aplicaciones con versiones anteriores de .NET Framework.

Para habilitar la compatibilidad con IRI, se necesitan los dos cambios siguientes:

1. Agregue la siguiente línea al archivo Machine. config en el directorio .NET Framework 2,0:
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. Especifique si desea que se aplique el análisis de nombres de dominio internacionalizados (IDN) al nombre de dominio y si se deben aplicar reglas de análisis de IRI. Esto puede hacerse en el archivo machine.config o app.config.

 Hay tres valores posibles para IDN en función de los servidores DNS que se usan:

- IDN habilitado = All  

     Este valor convierte cualquier nombre de dominio Unicode a su equivalente Punycode (nombres IDN).

- IDN habilitado = AllExceptIntranet

     Este valor convertirá todos los nombres de dominio Unicode que no estén en la Intranet local para usar los equivalentes Punycode (nombres IDN). En este caso, para administrar nombres internacionales en la Intranet local, los servidores DNS que se usan para la intranet deben admitir la resolución de nombres Unicode.

- IDN habilitado = ninguno

     Este valor no convierte ningún nombre de dominio Unicode para que se use Punycode. Este es el valor predeterminado que es coherente con el comportamiento de .NET Framework 2.0.

 La activación de IDN convertirá todas la etiquetas Unicode de un nombre de dominio en sus equivalentes de Punycode. Los nombres de Punycode solo contienen caracteres ASCII y siempre empiezan con el prefijo xn--. De este modo, se admiten los servidores DNS existentes en Internet, ya que la mayoría de los servidores DNS solo admite caracteres ASCII (vea RFC 3940).

### <a name="configuration-files"></a>Archivos de configuración

Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase para admitir el análisis de IRI y los nombres IDN:

```xml
<configuration>
  <uri>
    <idn enabled="All" />
    <iriParsing enabled="true" />
  </uri>
</configuration>
```

## <a name="see-also"></a>Consulte también

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [Esquema de la configuración de red](index.md)
