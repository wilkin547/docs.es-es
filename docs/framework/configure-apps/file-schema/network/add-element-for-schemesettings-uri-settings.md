---
title: Elemento <add> para schemeSettings (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: 027c7aaffea7950739f532309255d77afa031ada
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659552"
---
# <a name="add-element-for-schemesettings-uri-settings"></a>\<Agregar > elemento para schemeSettings (configuración de URI)
Agrega una configuración de esquema para un nombre de esquema.  
  
 \<configuration>  
\<Uri >  
\<schemeSettings>  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|Nombre|Nombre del esquema para el que se aplica esta configuración. Los únicos valores admitidos son name = "http" y name = "https".|  
  
## <a name="attribute-name-attribute"></a>{Nombre de atributo} Atribui  
  
|Value|DESCRIPCIÓN|  
|-----------|-----------------|  
|genericUriParserOptions|Opciones del analizador para este esquema. El único valor admitido es genericUriParserOptions = "DontUnescapePathDotsAndSlashes".|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[Elemento \<schemeSettings> (configuración de URI)](schemesettings-element-uri-settings.md)|Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.|  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, <xref:System.Uri?displayProperty=nameWithType> la clase no escapa los delimitadores de ruta de acceso codificados por porcentaje antes de ejecutar la compresión de la ruta de acceso. Esto se implementó como un mecanismo de seguridad contra ataques como los siguientes:  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Si este URI se pasa a los módulos que no controlan correctamente los caracteres codificados por porcentaje, podría provocar que el servidor ejecute el siguiente comando:  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 Por esta razón, <xref:System.Uri?displayProperty=nameWithType> la clase primero anula el escape de los delimitadores de ruta de acceso y, a continuación, aplica la compresión de la ruta de acceso. El resultado de pasar la dirección URL malintencionada anterior <xref:System.Uri?displayProperty=nameWithType> al constructor de clase da como resultado el siguiente URI:  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Este comportamiento predeterminado se puede modificar para que no se eliminen los delimitadores de ruta de acceso codificados por porcentaje mediante la opción de configuración schemeSettings para un esquema específico.  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una configuración utilizada <xref:System.Uri> por la clase para admitir delimitadores de ruta de acceso no codificados por porcentaje para el esquema http.  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [Esquema de la configuración de red](index.md)
