---
title: <schemaImporterExtensions> (Elemento)
description: El elemento <schemaImporterExtensions> contiene tipos que se usan en XmlSchemaImporter para asignar tipos XSD a tipos de .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 35626618a8dd7c63a7008d10bc3568484836a488
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282267"
---
# <a name="schemaimporterextensions-element"></a>Elemento \<schemaImporterExtensions>

Contiene tipos que <xref:System.Xml.Serialization.XmlSchemaImporter> usa para asignar de los tipos XSD a los tipos de .NET. Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<add> Elemento para \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md)|Agrega tipos que son usados por <xref:System.Xml.Serialization.XmlSchemaImporter> para crear las asignaciones.|  
  
## <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[Elemento \<system.xml.serialization>](system-xml-serialization-element.md)|El elemento de nivel superior para controlar la serialización XML.|  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra cómo agregar tipos que <xref:System.Xml.Serialization.XmlSchemaImporter> usa al asignar los tipos XSD a los tipos de .NET.  
  
```xml  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =
        "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.xml.serialization>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [Esquema de los archivos de configuración](../../framework/configure-apps/file-schema/index.md)
- [Elemento \<dateTimeSerialization>](datetimeserialization-element.md)
- [\<add> Elemento para \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md)
- [Elemento \<system.xml.serialization>](system-xml-serialization-element.md)
