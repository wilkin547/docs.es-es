---
title: Elemento <httpListener> (configuración de red)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 0054be3d2002e4ea5247f25d8094386ac7242422
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088375"
---
# <a name="httplistener-element-network-settings"></a>Elemento \<httpListener> (configuración de red)
Personaliza los parámetros utilizados por la <xref:System.Net.HttpListener> clase.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpListener>**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a>Tipo  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|unescapeRequestUrl|Valor booleano que indica si una <xref:System.Net.HttpListener> instancia de usa el URI sin escape sin formato en lugar del URI convertido.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[settings](settings-element-network-settings.md)|Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## <a name="remarks"></a>Comentarios  
 El atributo **unescapeRequestUrl** indica si <xref:System.Net.HttpListener> usa el URI sin escape sin formato en lugar del URI convertido en el que se convierten los valores con codificación porcentual y se toman otros pasos de normalización.  
  
 Cuando una <xref:System.Net.HttpListener> instancia recibe una solicitud a través del `http.sys` servicio, crea una instancia de la cadena URI proporcionada por `http.sys` y la expone como la <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> propiedad.  
  
 El `http.sys` servicio expone dos cadenas URI de solicitud:  
  
- URI sin formato  
  
- URI convertido  
  
 El URI sin formato es el <xref:System.Uri?displayProperty=nameWithType> proporcionado en la línea de solicitud de una solicitud http:  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 El URI sin formato proporcionado por `http.sys` para la solicitud mencionada anteriormente es "/path/". Representa la cadena que sigue al verbo HTTP tal como se envió a través de la red.  
  
 El `http.sys` servicio crea un URI convertido a partir de la información proporcionada en la solicitud mediante el URI proporcionado en la línea de solicitud HTTP y el encabezado de host para determinar el servidor de origen al que se debe reenviar la solicitud. Para ello, se compara la información de la solicitud con un conjunto de prefijos de URI registrados. La documentación del SDK del servidor HTTP hace referencia a este URI convertido como la estructura HTTP_COOKED_URL.  
  
 Para poder comparar la solicitud con prefijos URI registrados, es necesario realizar alguna normalización a la solicitud. Para el ejemplo anterior, el URI convertido sería como sigue:  
  
 `http://www.contoso.com/path/`  
  
 El `http.sys` servicio combina el <xref:System.Uri.Host%2A?displayProperty=nameWithType> valor de propiedad y la cadena en la línea de solicitud para crear un URI convertido. Además, `http.sys` la <xref:System.Uri?displayProperty=nameWithType> clase también hace lo siguiente:  
  
- Quita la escape de todos los valores codificados por porcentaje.  
  
- Convierte los caracteres que no son ASCII con codificación porcentual en una representación de caracteres UTF-16. Tenga en cuenta que se admiten los caracteres UTF-8 y ANSI/DBCS, así como caracteres Unicode (codificación Unicode con el formato% uXXXX).  
  
- Ejecuta otros pasos de normalización, como la compresión de la ruta de acceso.  
  
 Dado que la solicitud no contiene ninguna información sobre la codificación utilizada para los valores codificados con porcentaje, es posible que no sea posible determinar la codificación correcta solo mediante el análisis de los valores codificados por porcentaje.  
  
 Por lo tanto, `http.sys` proporciona dos claves del registro para modificar el proceso:  
  
|Clave del Registro|Valor predeterminado|Descripción|  
|------------------|-------------------|-----------------|  
|EnableNonUTF8|1|Si es cero, `http.sys` solo acepta direcciones URL con codificación UTF-8.<br /><br /> Si es distinto de cero, `http.sys` también acepta direcciones URL codificadas en ANSI o codificadas con DBCS en las solicitudes.|  
|FavorUTF8|1|Si es distinto de cero, `http.sys` siempre intenta descodificar una dirección URL como UTF-8 primero; si se produce un error en esa conversión y EnableNonUTF8 es distinto de cero, http. sys intenta descodificarlo como ANSI o DBCS.<br /><br /> Si cero (y EnableNonUTF8 es distinto de cero), `http.sys` intenta descodificarlo como ANSI o DBCS; si no se realiza correctamente, intenta una conversión UTF-8.|  
  
 Cuando <xref:System.Net.HttpListener> recibe una solicitud, utiliza el URI convertido de `http.sys` como entrada para la <xref:System.Net.HttpListenerRequest.Url%2A> propiedad.  
  
 Hay una necesidad de admitir caracteres además de caracteres y números en los URI. Un ejemplo es el URI siguiente, que se usa para recuperar información de cliente para el número de cliente "1/3812":  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 Observe la barra diagonal codificada en porcentaje en el URI (% 2F). Esto es necesario, ya que en este caso el carácter de barra diagonal representa datos y no un delimitador de ruta de acceso.  
  
 Al pasar la cadena al constructor URI se conducirá al URI siguiente:  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 La división de la ruta de acceso en sus segmentos daría lugar a los siguientes elementos:  
  
 `Customer('1`  
  
 `3812')`  
  
 No se trata de la intención del remitente de la solicitud.  
  
 Si el atributo **unescapeRequestUrl** se establece en **false**, cuando <xref:System.Net.HttpListener> recibe una solicitud, usa el URI sin formato en lugar del URI convertido desde `http.sys` como entrada a la <xref:System.Net.HttpListenerRequest.Url%2A> propiedad.  
  
 El valor predeterminado para el atributo **unescapeRequestUrl** es **true**.  
  
 La <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> propiedad se puede utilizar para obtener el valor actual del atributo **unescapeRequestUrl** de los archivos de configuración aplicables.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo configurar la <xref:System.Net.HttpListener> clase cuando recibe una solicitud para usar el URI sin formato en lugar del URI convertido desde `http.sys` como entrada a la <xref:System.Net.HttpListenerRequest.Url%2A> propiedad.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpListener  
        unescapeRequestUrl="false"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="element-information"></a>Información de elemento  
  
|||
|-|-|  
|Espacio de nombres|System.Net|  
|Nombre del esquema||  
|Archivo de validación||  
|Puede estar vacío||  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [Esquema de la configuración de red](index.md)
