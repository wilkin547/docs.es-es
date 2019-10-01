---
title: Elemento <httpListener> (configuración de red)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 3f75096681ab07dd6d4788fbded5ca5c4a024aef
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698194"
---
# <a name="httplistener-element-network-settings"></a>\<httpListener (elemento >) (configuración de red)
Personaliza los parámetros utilizados por la clase <xref:System.Net.HttpListener>.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **@no__t -4System. net >** ](system-net-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<settings >** ](settings-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<httpListener >**  
  
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
|unescapeRequestUrl|Un valor booleano que indica si una instancia de <xref:System.Net.HttpListener> usa el URI sin escape sin formato en lugar del URI convertido.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[Configuración](settings-element-network-settings.md)|Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## <a name="remarks"></a>Comentarios  
 El atributo **unescapeRequestUrl** indica si <xref:System.Net.HttpListener> usa el URI sin escape sin formato en lugar del URI convertido en el que se convierten los valores con codificación porcentual y se toman otros pasos de normalización.  
  
 Cuando una instancia de <xref:System.Net.HttpListener> recibe una solicitud a través del servicio `http.sys`, crea una instancia de la cadena URI proporcionada por `http.sys` y la expone como la propiedad <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType>.  
  
 El servicio `http.sys` expone dos cadenas URI de solicitud:  
  
- URI sin formato  
  
- URI convertido  
  
 El URI sin formato es el <xref:System.Uri?displayProperty=nameWithType> proporcionado en la línea de solicitud de una solicitud HTTP:  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 El URI sin formato proporcionado por `http.sys` para la solicitud mencionada anteriormente es "/path/". Representa la cadena que sigue al verbo HTTP tal como se envió a través de la red.  
  
 El servicio `http.sys` crea un URI convertido a partir de la información proporcionada en la solicitud mediante el URI proporcionado en la línea de solicitud HTTP y el encabezado de host para determinar el servidor de origen al que se debe reenviar la solicitud. Para ello, se compara la información de la solicitud con un conjunto de prefijos de URI registrados. La documentación del SDK del servidor HTTP hace referencia a este URI convertido como la estructura HTTP_COOKED_URL.  
  
 Para poder comparar la solicitud con prefijos URI registrados, es necesario realizar alguna normalización a la solicitud. Para el ejemplo anterior, el URI convertido sería como sigue:  
  
 `http://www.contoso.com/path/`  
  
 El servicio `http.sys` combina el valor de la propiedad <xref:System.Uri.Host%2A?displayProperty=nameWithType> y la cadena en la línea de solicitud para crear un URI convertido. Además, `http.sys` y la clase <xref:System.Uri?displayProperty=nameWithType> también hace lo siguiente:  
  
- Quita la escape de todos los valores codificados por porcentaje.  
  
- Convierte los caracteres que no son ASCII con codificación porcentual en una representación de caracteres UTF-16. Tenga en cuenta que se admiten los caracteres UTF-8 y ANSI/DBCS, así como caracteres Unicode (codificación Unicode con el formato% uXXXX).  
  
- Ejecuta otros pasos de normalización, como la compresión de la ruta de acceso.  
  
 Dado que la solicitud no contiene ninguna información sobre la codificación utilizada para los valores codificados con porcentaje, es posible que no sea posible determinar la codificación correcta solo mediante el análisis de los valores codificados por porcentaje.  
  
 Por lo tanto `http.sys` proporciona dos claves del registro para modificar el proceso:  
  
|Clave del Registro|Valor predeterminado|Descripción|  
|------------------|-------------------|-----------------|  
|EnableNonUTF8|1|Si es cero, `http.sys` solo acepta direcciones URL con codificación UTF-8.<br /><br /> Si es distinto de cero, `http.sys` también acepta direcciones URL con codificación ANSI o codificadas con DBCS en las solicitudes.|  
|FavorUTF8|1|Si es distinto de cero, `http.sys` siempre intenta descodificar una dirección URL como UTF-8 primero; Si se produce un error en esa conversión y EnableNonUTF8 es distinto de cero, http. sys intenta descodificarlo como ANSI o DBCS.<br /><br /> Si cero (y EnableNonUTF8 es distinto de cero), `http.sys` intenta descodificarlo como ANSI o DBCS; Si no se realiza correctamente, intenta una conversión UTF-8.|  
  
 Cuando <xref:System.Net.HttpListener> recibe una solicitud, utiliza el URI convertido de `http.sys` como entrada para la propiedad <xref:System.Net.HttpListenerRequest.Url%2A>.  
  
 Hay una necesidad de admitir caracteres además de caracteres y números en los URI. Un ejemplo es el URI siguiente, que se usa para recuperar información de cliente para el número de cliente "1/3812":  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 Observe la barra diagonal codificada en porcentaje en el URI (% 2F). Esto es necesario, ya que en este caso el carácter de barra diagonal representa datos y no un delimitador de ruta de acceso.  
  
 Al pasar la cadena al constructor URI se conducirá al URI siguiente:  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 La división de la ruta de acceso en sus segmentos daría lugar a los siguientes elementos:  
  
 `Customer('1`  
  
 `3812')`  
  
 No se trata de la intención del remitente de la solicitud.  
  
 Si el atributo **unescapeRequestUrl** se establece en **false**, cuando el <xref:System.Net.HttpListener> recibe una solicitud, usa el URI sin formato en lugar del URI convertido de `http.sys` como entrada para la propiedad <xref:System.Net.HttpListenerRequest.Url%2A>.  
  
 El valor predeterminado para el atributo **unescapeRequestUrl** es **true**.  
  
 Se puede usar la propiedad <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> para obtener el valor actual del atributo **unescapeRequestUrl** de los archivos de configuración aplicables.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo configurar la clase <xref:System.Net.HttpListener> cuando recibe una solicitud para usar el URI sin formato en lugar del URI convertido de `http.sys` como entrada para la propiedad <xref:System.Net.HttpListenerRequest.Url%2A>.  
  
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
|Nombre de esquema||  
|Archivo de validación||  
|Puede estar vacío||  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [Esquema de la configuración de red](index.md)
