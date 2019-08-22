---
title: Elemento <schemeSettings> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 46012b15d41422fb3357e57438e320136809ef41
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664012"
---
# <a name="schemesettings-element-uri-settings"></a>\<schemeSettings > elemento (configuración de URI)
Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.  
  
 \<configuration>  
\<Uri >  
\<schemeSettings>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 None  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[add](add-element-for-schemesettings-uri-settings.md)|Agrega una configuración de esquema para un nombre de esquema.|  
|[clear](clear-element-for-schemesettings-uri-settings.md)|Borra todos los valores de esquema existentes.|  
|[remove](remove-element-for-schemesettings-uri-settings.md)|Quita un valor de esquema para un nombre de esquema.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[uri](uri-element-uri-settings.md)|Contiene opciones que especifican cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).|  
  
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
  
## <a name="element-information"></a>Información de elemento  
  
|||
|-|-|  
|Espacio de nombres|Sistema|  
|Nombre de esquema||  
|Archivo de validación||  
|Puede estar vacío||  
  
## <a name="see-also"></a>Vea también

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [Esquema de la configuración de red](index.md)
