---
title: Elemento <uri> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: 2f22d70407d10dbb38f0cb8d3a8ac74ff3fe8763
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190207"
---
# <a name="uri-element-uri-settings"></a>Elemento \<uri> (configuración de URI)

Contiene opciones que especifican cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<uri>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  

 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[IDN](idn-element-uri-settings.md)|Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.|  
|[Análisisiri](iriparsing-element-uri-settings.md)|Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.|  
|[schemeSettings](schemesettings-element-uri-settings.md)|Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[configuration](../configuration-element.md)|Contiene la configuración de todos los espacios de nombres.|  
  
## <a name="remarks"></a>Observaciones  

 El `uri` elemento contiene la configuración de los miembros de la <xref:System.Uri> clase utilizada por las clases del <xref:System.Net> espacio de nombres. La configuración configura la compatibilidad con IRI e IDN.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  

 En el ejemplo siguiente se muestra una configuración utilizada por la <xref:System.Uri> clase para admitir el análisis de IRI y los nombres IDN. En el ejemplo también se borran todos los valores de esquema y, a continuación, se agrega compatibilidad para no escapar los delimitadores de ruta de acceso con codificación porcentual para el esquema http.  
  
### <a name="code"></a>Código  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de red](index.md)
