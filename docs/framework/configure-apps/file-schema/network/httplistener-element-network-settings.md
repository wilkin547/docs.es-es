---
title: '&lt;httpListener&gt; elemento (configuración de red)'
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 3daf18fab81ea481be8e45e4d9ad682047ada6f3
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50042641"
---
# <a name="lthttplistenergt-element-network-settings"></a>&lt;httpListener&gt; elemento (configuración de red)
Personaliza los parámetros utilizados por la <xref:System.Net.HttpListener> clase.  
  
 \<configuration>  
\<System.NET >  
\<Configuración >  
\<httpListener >  
  
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
|unescapeRequestUrl|Un valor booleano que indica si un <xref:System.Net.HttpListener> instancia usa el URI sin secuencias de escape de formato en lugar del URI convertido.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[Configuración](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## <a name="remarks"></a>Comentarios  
 El **unescapeRequestUrl** atributo indica si <xref:System.Net.HttpListener> usa el URI sin secuencias de escape de formato en lugar del URI convertido donde se convierten los valores codificados por porcentaje y se realizan otros pasos de normalización.  
  
 Cuando un <xref:System.Net.HttpListener> instancia recibe una solicitud a través de la `http.sys` servicio, crea una instancia de la cadena URI proporcionada por `http.sys`y lo expone como la <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> propiedad.  
  
 El `http.sys` servicio expone dos cadenas de identificador URI de solicitud:  
  
-   URI sin formato  
  
-   URI convertido  
  
 El URI sin procesar es el <xref:System.Uri?displayProperty=nameWithType> proporcionado en la línea de solicitud de una solicitud HTTP:  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 El URI sin formato proporcionado por `http.sys` para la solicitud se ha mencionado anteriormente, es "/ path /". Representa la cadena que sigue el verbo HTTP que se enviaron a través de la red.  
  
 El `http.sys` servicio crea un URI convertido de la información proporcionada en la solicitud usando el URI proporcionado en la línea de solicitud HTTP y el encabezado de Host para determinar el servidor de origen de la solicitud debe reenviarse al. Esto se hace mediante la comparación de la información de la solicitud con un conjunto de prefijos URI registrados. La documentación del SDK de servidor HTTP hace referencia a este URI convertido como la estructura HTTP_COOKED_URL.  
  
 Para poder comparar la solicitud con los prefijos URI registrados, debe realizarse alguna normalización de la solicitud. Para el ejemplo anterior del URI convertido sería como sigue:  
  
 `http://www.contoso.com/path/`  
  
 El `http.sys` servicio combina el <xref:System.Uri.Host%2A?displayProperty=nameWithType> valor de propiedad y la cadena en la línea de solicitud para crear un URI convertido. Además, `http.sys` y <xref:System.Uri?displayProperty=nameWithType> clase también hace lo siguiente:  
  
-   Escapes de Naciones Unidas por ciento de todos los valores codificados.  
  
-   Caracteres no ASCII de codificación de porcentaje se convierte en una representación de caracteres UTF-16. Tenga en cuenta que se admiten caracteres UTF-8 y ANSI/DBCS, así como caracteres Unicode (codificación Unicode con el formato % uXXXX).  
  
-   Ejecuta otros pasos de normalización, como la compresión de la ruta de acceso.  
  
 Puesto que la solicitud no contiene toda la información sobre la codificación utilizada para los valores codificados por porcentaje, no puede ser posible determinar la codificación correcta simplemente analizando los valores codificados por porcentaje.  
  
 Por lo tanto, `http.sys` proporciona dos claves del registro para modificar el proceso:  
  
|Clave del Registro|Valor predeterminado|Descripción|  
|------------------|-------------------|-----------------|  
|EnableNonUTF8|1|Si es cero, `http.sys` acepta solo direcciones URL codificado en UTF-8.<br /><br /> Si es distinto de cero, `http.sys` también acepta direcciones URL de la codificación ANSI o codificación DBCS en las solicitudes.|  
|FavorUTF8|1|Si es distinto de cero, `http.sys` siempre intenta descodificar una dirección URL como UTF-8 en primer lugar; si se produce un error en esa conversión y EnableNonUTF8 es distinto de cero, Http.sys, a continuación, intenta descodificarlo como ANSI o DBCS.<br /><br /> Si es cero (y EnableNonUTF8 es distinto de cero), `http.sys` intenta descodificarlo como ANSI o DBCS; si no se realiza correctamente, trata de una conversión de UTF-8.|  
  
 Cuando <xref:System.Net.HttpListener> recibe una solicitud, usa el URI convertido de `http.sys` como entrada el <xref:System.Net.HttpListenerRequest.Url%2A> propiedad.  
  
 Es necesario para admitir caracteres además de los caracteres y números en los URI. Un ejemplo es el URI siguiente, que se usa para recuperar información del cliente para el cliente número "1/3812":  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 Tenga en cuenta la barra diagonal codificada por porcentaje en el Uri (% 2F). Esto es necesario, ya que en este caso el carácter de barra diagonal representa los datos y no un delimitador de ruta de acceso.  
  
 Pasar la cadena al constructor Uri dará lugar al URI siguiente:  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 Dividir la ruta de acceso en sus segmentos daría lugar a los siguientes elementos:  
  
 `Customer('1`  
  
 `3812')`  
  
 Esto no es la intención del remitente de la solicitud.  
  
 Si el **unescapeRequestUrl** atributo está establecido en **false**, entonces, cuando el <xref:System.Net.HttpListener> recibe una solicitud, usa el URI sin formato en lugar del URI convertido de `http.sys` como entrada para el <xref:System.Net.HttpListenerRequest.Url%2A> propiedad.  
  
 El valor predeterminado para el **unescapeRequestUrl** atributo es **true**.  
  
 El <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> propiedad puede usarse para obtener el valor actual de la **unescapeRequestUrl** atributo desde archivos de configuración aplicables.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo configurar el <xref:System.Net.HttpListener> cuando recibe una solicitud para utilizar el URI sin formato en lugar del URI convertido de la clase `http.sys` como entrada el <xref:System.Net.HttpListenerRequest.Url%2A> propiedad.  
  
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
 <xref:System.Net.Configuration.HttpListenerElement>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpListenerRequest.Url%2A>  
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
