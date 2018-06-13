---
title: '&lt;schemaImporterExtensions&gt; (Elemento)'
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: c9f4f6800c2718c3b2c2b9b5b2b6d97e1114dbcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581334"
---
# <a name="ltschemaimporterextensionsgt-element"></a>&lt;schemaImporterExtensions&gt; (Elemento)
Contiene tipos que son utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> para asignar de los tipos XSD a los tipos de .NET Framework. Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</SchemaImporterExtension>  
```  
  
## <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[Elemento \<add> de \<xmlSchemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)|Agrega tipos que son usados por <xref:System.Xml.Serialization.XmlSchemaImporter> para crear las asignaciones.|  
  
## <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[Elemento \<system.xml.serialization>](../../../docs/standard/serialization/system-xml-serialization-element.md)|El elemento de nivel superior para controlar la serialización XML.|  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra cómo agregar tipos que son utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> al asignar los tipos XSD a los tipos de .NET Framework.  
  
```xml  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =   
        "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
/system.sxml.serializaiton>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
 [Esquema de los archivos de configuración](../../../docs/framework/configure-apps/file-schema/index.md)  
 [Elemento \<dateTimeSerialization>](../../../docs/standard/serialization/datetimeserialization-element.md)  
 [Elemento \<add> de \<xmlSchemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)  
 [Elemento \<system.xml.serialization>](../../../docs/standard/serialization/system-xml-serialization-element.md)
