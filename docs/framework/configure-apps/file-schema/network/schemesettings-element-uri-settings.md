---
title: Elemento <schemeSettings> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 498aef77a1dfd8cffcac73b704b8d1bb6df5d165
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697770"
---
# <a name="schemesettings-element-uri-settings"></a>\<elemento > schemeSettings (configuración de URI)
Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;[ **uri de\<&nbsp;>** ](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp; **\<schemeSettings >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno  
  
### <a name="child-elements"></a>Elemento secundario  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[add](add-element-for-schemesettings-uri-settings.md)|Agrega una configuración de esquema para un nombre de esquema.|  
|[clear](clear-element-for-schemesettings-uri-settings.md)|Borra todos los valores de esquema existentes.|  
|[remove](remove-element-for-schemesettings-uri-settings.md)|Quita un valor de esquema para un nombre de esquema.|  
  
### <a name="parent-elements"></a>Elemento principal  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[uri](uri-element-uri-settings.md)|Contiene opciones que especifican cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).|  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, la clase <xref:System.Uri?displayProperty=nameWithType> no aplica el escape a los delimitadores de ruta de acceso codificados por porcentaje antes de ejecutar la compresión de la ruta de acceso. Esto se implementó como un mecanismo de seguridad contra ataques como los siguientes:  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Si este URI se pasa a los módulos que no controlan correctamente los caracteres codificados por porcentaje, podría provocar que el servidor ejecute el siguiente comando:  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 Por esta razón, <xref:System.Uri?displayProperty=nameWithType> clase primero quita los caracteres de escape de los delimitadores de ruta de acceso y, a continuación, aplica la compresión de la ruta de acceso. El resultado de pasar la dirección URL malintencionada anterior a <xref:System.Uri?displayProperty=nameWithType> constructor de clase da como resultado el URI siguiente:  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Este comportamiento predeterminado se puede modificar para que no se eliminen los delimitadores de ruta de acceso codificados por porcentaje mediante la opción de configuración schemeSettings para un esquema específico.  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una configuración utilizada por la clase <xref:System.Uri> para admitir los delimitadores de ruta de acceso no codificados por porcentaje para el esquema http.  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a>Información del elemento  
  
|||
|-|-|  
|Espacio de nombres|System|  
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
