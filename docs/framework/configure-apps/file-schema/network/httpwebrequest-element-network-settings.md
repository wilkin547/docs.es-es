---
title: Elemento <httpWebRequest> (configuración de red)
description: El <httpWebRequest> elemento de configuración de red Personaliza los parámetros de la solicitud Web en el .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: 59ab425dcef8ac5283035910a9d78a89a16be8b1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504594"
---
# <a name="httpwebrequest-element-network-settings"></a>Elemento \<httpWebRequest> (configuración de red)
Personaliza los parámetros de la solicitud Web.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|**Attribute**|**Descripción**|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|Especifica la longitud máxima de un encabezado de respuesta, en kilobytes. El valor predeterminado es 64. Un valor de-1 indica que no se impondrá ningún límite de tamaño en los encabezados de respuesta.|  
|`maximumErrorResponseLength`|Especifica la longitud máxima de una respuesta de error, en kilobytes. El valor predeterminado es 64. Un valor de-1 indica que no se impondrá ningún límite de tamaño en la respuesta de error.|  
|`maximumUnauthorizedUploadLength`|Especifica la longitud máxima de una carga en respuesta a un código de error no autorizado, en bytes. El valor predeterminado es -1. Un valor -1 indica que no se impondrá límite de tamaño a la carga.|  
|`useUnsafeHeaderParsing`|Especifica si está habilitado el análisis de encabezados no seguros. El valor predeterminado es `false`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[settings](settings-element-network-settings.md)|Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, el .NET Framework aplica estrictamente la RFC 2616 para el análisis de URI. Algunas respuestas del servidor pueden incluir caracteres de control en campos prohibidos, lo que hará que el <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> método produzca una excepción <xref:System.Net.WebException> . Si **useUnsafeHeaderParsing** se establece en **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> no se producirá en este caso; sin embargo, la aplicación será vulnerable a varias formas de ataques de análisis de URI. La mejor solución es cambiar el servidor para que la respuesta no incluya caracteres de control.  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar una longitud de encabezado máxima mayor que la normal.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también:

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [Esquema de la configuración de red](index.md)
