---
title: "&lt;httpListener&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
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
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# &lt;httpListener&gt; (Elemento, Configuraci&#243;n de red)
Personaliza los parámetros utilizados por la clase <xref:System.Net.HttpListener>.  
  
## Sintaxis  
  
```  
  
      <httpListener  
  unescapeRequestUrl ="true|false"  
/>  
```  
  
## Tipo  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|unescapeRequestUrl|Valor booleano que indica si una instancia de <xref:System.Net.HttpListener> usa el URI sin caracteres de escape y sin formato en lugar del URI convertido.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura las opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## Comentarios  
 El atributo **unescapeRequestUrl** indica si <xref:System.Net.HttpListener> usa el URI sin secuencias de escape y sin formato en lugar del URI convertido cuando se convierte cualquier valor codificado por porcentaje y se dan otros pasos de normalización.  
  
 Cuando una instancia <xref:System.Net.HttpListener> recibe una solicitud a través del servicio `http.sys`, crea una instancia de la cadena de URI proporcionada por `http.sys`, y la expone como la propiedad <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=fullName>.  
  
 El servicio `http.sys` expone dos cadenas del identificador URI especificado:  
  
-   URI sin formato  
  
-   URI convertido  
  
 El URI sin formato es el <xref:System.Uri?displayProperty=fullName> proporcionado en la línea de solicitud de una solicitud HTTP:  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 El URI sin formato proporcionado por `http.sys` para la solicitud arriba expresada, es "\/path\/".  Esto representa la cadena que sigue al verbo HTTP como se envió a través de la red.  
  
 El servicio `http.sys` crea un URI convertido a partir de la información proporcionada en la solicitud utilizando el URI proporcionado en la línea de solicitud HTTP y el encabezado de host, para determinar el servidor de origen al que la solicitud se debería reenviar.  Esto se hace comparando la información de la solicitud con un conjunto de prefijos URI registrados.  La documentación del SDK de servidor HTTP hace referencia a este URI convertido como la estructura HTTP\_COOKED\_URL.  
  
 Para poder comparar la solicitud con los prefijos URI registrados, necesita hacerse alguna normalización de la solicitud.  Para obtener el ejemplo anterior el identificador URI convertido sería como sigue:  
  
 `http://www.contoso.com/path/`  
  
 El servicio `http.sys` combina el valor de propiedad <xref:System.Uri.Host%2A?displayProperty=fullName> y la cadena en la línea de solicitud para crear un URI convertido.  Además, `http.sys` y la clase <xref:System.Uri?displayProperty=fullName> también realizan lo siguiente:  
  
-   Quita los caracteres de escape de todos los valores codificados con porcentaje.  
  
-   Convierte los caracteres no ASCII con codificación de porcentaje en una representación de caracteres UTF\-16.  Observe que se admiten caracteres UTF\-8 y ANSI\/DBCS así como caracteres Unicode \(codificación Unicode usando el formato %uXXXX\).  
  
-   Ejecuta otros pasos de normalización, como la compresión de la ruta de acceso.  
  
 Puesto que la solicitud no contiene ninguna información sobre la codificación usada para los valores codificados por porcentaje, no se puede determinar la codificación correcta simplemente analizando los valores codificados por porcentaje.  
  
 Por consiguiente, `http.sys` proporciona dos claves del Registro para modificar el proceso:  
  
|Clave del Registro|Valor predeterminado|Descripción|  
|------------------------|--------------------------|-----------------|  
|EnableNonUTF8|1|Si es cero, `http.sys` solo acepta direcciones URL UTF 8 codificadas.<br /><br /> Si es distinto de cero, `http.sys` también acepta direcciones URL codificadas por ANSI o codificadas por DBCS en las solicitudes.|  
|FavorUTF8|1|Si es distinto de cero, `http.sys` siempre intenta descodificar primero una dirección URL como UTF\-8; si se produce un error en esa conversión y EnableNonUTF8 es distinto de cero, Http.sys intenta descodificarla como ANSI o DBCS.<br /><br /> Si es cero \(y EnableNonUTF8 es distinto de cero\), `http.sys` intenta decodificarlo como ANSI o DBCS; si eso no es correcto, prueba una conversión de UTF\-8.|  
  
 Cuando <xref:System.Net.HttpListener> recibe una solicitud, usa el URI convertido de `http.sys` como entrada para la propiedad <xref:System.Net.HttpListenerRequest.Url%2A>.  
  
 Es necesario admitir los caracteres además de los caracteres y números en los URI.  Un ejemplo es el URI siguiente, que se usa para recuperar información del cliente para el cliente número "1\/3812":  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 Tenga en cuenta la barra diagonal codificada por porcentaje en el Uri \(%2F\).  Esto es necesario, ya que en este caso el carácter de barra diagonal representa los datos y no un delimitador de ruta de acceso.  
  
 Pasar la cadena al constructor Uri conducirá al URI siguiente:  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 Al dividir la ruta de acceso en sus segmentos daría lugar a los elementos siguientes:  
  
 `Customer('1`  
  
 `3812')`  
  
 Esta no es la intención del remitente de la solicitud.  
  
 Si el atributo **unescapeRequestUrl** se establece en **false**, cuando <xref:System.Net.HttpListener> recibe una solicitud, utiliza el URI sin formato en lugar del URI convertido de `http.sys` como entrada a la propiedad <xref:System.Net.HttpListenerRequest.Url%2A>.  
  
 El valor predeterminado del atributo **unescapeRequestUrl** es **true**.  
  
 La propiedad <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> se puede utilizar para obtener el valor actual del atributo **unescapeRequestUrl** de los archivos de configuración aplicables.  
  
## Ejemplo  
 El ejemplo de código siguiente muestra cómo configurar la clase <xref:System.Net.HttpListener> cuando recibe una solicitud para utilizar el URI sin formato en lugar del URI convertido de `http.sys` como entrada para la propiedad <xref:System.Net.HttpListenerRequest.Url%2A>.  
  
```  
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
  
## Información de elemento  
  
|||  
|-|-|  
|Espacio de nombres|System.Net|  
|Nombre de esquema||  
|Archivo de validación||  
|Puede estar vacío||  
  
## Vea también  
 <xref:System.Net.Configuration.HttpListenerElement>   
 <xref:System.Net.HttpListener>   
 <xref:System.Net.HttpListenerRequest.Url%2A>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)