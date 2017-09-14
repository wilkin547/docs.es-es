---
title: '&lt;add&gt; (Elemento para &lt;xmlSchemaImporterExtensions&gt;)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <xmlSchemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
caps.latest.revision: 3
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: 859e348359ed35e971baff8611fa4f676808f5a7
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="ltaddgt-element-for-ltxmlschemaimporterextensionsgt"></a>&lt;add&gt; (Elemento para &lt;xmlSchemaImporterExtensions&gt;)
Agrega tipos utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> para asignar los tipos XSD a los tipos de .NET Framework. Para obtener más información sobre los archivos de configuración, vea [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).  
  
 \<configuration>  
\<system.xml.serialization>  
\<XmlSchemaImporterExtensions>  
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
|**type**|Obligatorio. Especifica la clase de extensión de esquema que se agrega. El valor del atributo **type** debe estar en una línea e incluye el nombre de tipo completo. Cuando el ensamblado se encuentra en la caché global de ensamblados (GAC), también debe incluir la versión, la referencia cultural y el token de clave pública del ensamblado firmado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|\<xmlSchemaImporterExtensions>|Contiene los tipos que utiliza <xref:System.Xml.Serialization.XmlSchemaImporter> .|  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente agrega un tipo de extensión que XmlSchemaImporter puede utilizar al asignar los tipos.  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSchemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,   
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a" />   
    </xmlSchemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 [Elemento \<system.xml.serialization>](../../../docs/standard/serialization/system-xml-serialization-element.md)   
 [Elemento \<schemaImporterExtensions>](../../../docs/standard/serialization/schemaimporterextensions-element.md)

