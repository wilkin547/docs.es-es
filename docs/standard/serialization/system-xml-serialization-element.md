---
title: Elemento <system.xml.serialization>
description: En este artículo se describe el elemento <system.xml.serialization>, que es el elemento de nivel superior para controlar la serialización XML.
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: f69e80592e9321de64421b977a63b83d8be2ad9e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289491"
---
# <a name="systemxmlserialization-element"></a>\<system.xml.serialization> (Elemento)

El elemento de nivel superior para controlar la serialización XML. Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).

\<configuration>\
\<system.xml.serialization>

## <a name="syntax"></a>Sintaxis

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

Ninguno.

### <a name="child-elements"></a>Elementos secundarios

|Elemento|Descripción|
|-------------|-----------------|
|[Elemento \<dateTimeSerialization>](datetimeserialization-element.md)|Determina el modo de serialización XML de los objetos <xref:System.DateTime>.|
|[Elemento \<schemaImporterExtensions>](schemaimporterextensions-element.md)|Contiene tipos que son utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> para asignar de los tipos XSD a los tipos de .NET Framework.|

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|[Elemento \<configuration>](../../framework/configure-apps/file-schema/configuration-element.md)|Elemento raíz necesario en cada archivo de configuración utilizado por Common Language Runtime y las aplicaciones de .NET Framework.|

## <a name="example"></a>Ejemplo

El ejemplo de código siguiente muestra cómo especificar el modo de la serialización de un objeto <xref:System.DateTime> y la suma de tipos utilizada por <xref:System.Xml.Serialization.XmlSchemaImporter> al asignar los tipos XSD a los tipos de .NET Framework.

```xml
<system.xml.serialization>
    <xmlSerializer checkDeserializeAdvances="false" />
    <dateTimeSerialization mode = "Local" />
    <schemaImporterExtensions>
        <add
        name = "MobileCapabilities"
        type = "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
        PublicKeyToken=b03f5f6f11d40a3a" />
    </schemaImporterExtensions>
</system.xml.serialization>
```

## <a name="see-also"></a>Vea también

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [Esquema de los archivos de configuración](../../framework/configure-apps/file-schema/index.md)
- [Elemento \<dateTimeSerialization>](datetimeserialization-element.md)
- [Elemento \<schemaImporterExtensions>](schemaimporterextensions-element.md)
- [\<add> Elemento para \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md)
