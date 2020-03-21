---
title: Elemento <schemeSettings> (configuración de URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: c745c90bb61b9ee393687d7f6db4fd11565c7dc7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154652"
---
# <a name="schemesettings-element-uri-settings"></a>\<Elemento schemeSettings> (configuración de URI)
Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.  
  
[**\<configuración>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**  
  
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
  
|**Elemento**|**Descripción**|  
|-----------------|---------------------|  
|[agregar](add-element-for-schemesettings-uri-settings.md)|Agrega una configuración de esquema para un nombre de esquema.|  
|[Claro](clear-element-for-schemesettings-uri-settings.md)|Borra todos los valores de esquema existentes.|  
|[quitar](remove-element-for-schemesettings-uri-settings.md)|Quita una configuración de esquema para un nombre de esquema.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Elemento**|**Descripción**|  
|-----------------|---------------------|  
|[Uri](uri-element-uri-settings.md)|Contiene valores que especifican cómo .NET Framework controla las direcciones web expresadas mediante identificadores de recursos uniformes (URI).|  
  
## <a name="remarks"></a>Observaciones  
 De forma <xref:System.Uri?displayProperty=nameWithType> predeterminada, la clase desestrata delimitadores de ruta de acceso con codificación porcentual antes de ejecutar la compresión de ruta de acceso. Esto se implementó como un mecanismo de seguridad contra ataques como el siguiente:  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Si este URI se pasa a módulos que no controlan correctamente los caracteres codificados porcentuales, podría dar lugar a que el servidor ejecute el siguiente comando:  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 Por este <xref:System.Uri?displayProperty=nameWithType> motivo, la clase primero anula los delimitadores de ruta de acceso y, a continuación, aplica la compresión de ruta de acceso. El resultado de pasar la <xref:System.Uri?displayProperty=nameWithType> dirección URL malintencionada anterior al constructor de clase da como resultado el uri siguiente:  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Este comportamiento predeterminado se puede modificar para no anular el escape de delimitadores de ruta de acceso codificados por porcentaje mediante la opción de configuración schemeSettings para un esquema específico.  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se <xref:System.Uri> muestra una configuración utilizada por la clase para admitir no escapar los delimitadores de ruta codificados porcentuales para el esquema http.  
  
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
|Nombre del esquema||  
|Archivo de validación||  
|Puede estar vacío||  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [Esquema de configuración de red](index.md)
