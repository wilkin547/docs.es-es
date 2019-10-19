---
title: Método XmlReader. CreateSqlReader (System. xml)
author: mairaw
ms.author: mairaw
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 302be4eff32d2c96a1571d291e0b289e77694db8
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582785"
---
# <a name="xmlreadercreatesqlreader-method"></a>Método XmlReader. CreateSqlReader

Crea una nueva instancia <xref:System.Xml.XmlReader> con el flujo, la configuración y la información de contexto especificados para el análisis.

```csharp
internal static XmlReader CreateSqlReader(Stream input, 
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a>Parámetros

- `input` <xref:System.IO.Stream>  
  Flujo que contiene los datos XML.

- `settings` <xref:System.Xml.XmlReaderSettings>  
  Configuración de la nueva instancia <xref:System.Xml.XmlReader>. Este valor puede ser `null`.

- `inputContext` <xref:System.Xml.XmlParserContext>  
  Información de contexto necesaria para analizar el fragmento XML. Este valor puede ser `null`.

## <a name="returns"></a>Valores devueltos

<xref:System.Xml.XmlReader>  
Objeto usado para leer los datos XML del flujo.

## <a name="remarks"></a>Comentarios

> [!WARNING]
> El método `XmlReader.CreateSqlReader` es interno y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Xml>

**Ensamblado:** System. Xml. dll

**.NET Framework versiones:** Disponible desde 2,0.
