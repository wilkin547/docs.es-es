---
title: '&lt;agregar&gt; (elemento) para &lt;schemaImporterExtensions&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 3d3c72fd64042032d44c49ebde867d111ce03b94
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43542645"
---
# <a name="ltaddgt-element-for-ltschemaimporterextensionsgt"></a>&lt;agregar&gt; (elemento) para &lt;schemaImporterExtensions&gt;
Agrega tipos utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> para asignar los tipos XSD a los tipos de .NET Framework. Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).  
  
 \<configuration>  
\<system.xml.serialization>  
\<schemaImporterExtensions>  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|**name**|Un nombre sencillo que se utiliza para buscar la instancia.|  
|**type**|Requerido. Especifica la clase de extensión de esquema que se agrega. El valor del atributo **type** debe estar en una línea e incluye el nombre de tipo completo. Cuando el ensamblado se encuentra en la caché global de ensamblados (GAC), también debe incluir la versión, la referencia cultural y el token de clave pública del ensamblado firmado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|\<schemaImporterExtensions>|Contiene los tipos que utiliza <xref:System.Xml.Serialization.XmlSchemaImporter> .|  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente agrega un tipo de extensión que XmlSchemaImporter puede utilizar al asignar los tipos.  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <schemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,   
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a" />   
    </schemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 [Elemento \<system.xml.serialization>](../../../docs/standard/serialization/system-xml-serialization-element.md)  
 [Elemento \<schemaImporterExtensions>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
