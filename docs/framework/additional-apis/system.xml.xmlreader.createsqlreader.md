---
description: 'Más información sobre: método XmlReader. CreateSqlReader'
title: Método XmlReader. CreateSqlReader (System.Xml)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 61d594c0438c86863ce4052387439f5483d8a34c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740440"
---
# <a name="xmlreadercreatesqlreader-method"></a>Método XmlReader.CreateSqlReader

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

## <a name="returns"></a>Devoluciones

<xref:System.Xml.XmlReader>  
Objeto usado para leer los datos XML del flujo.

## <a name="remarks"></a>Observaciones

> [!WARNING]
> El `XmlReader.CreateSqlReader` método es interno y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Xml>

**Ensamblado:** System.Xml.dll

**.NET Framework versiones:** Disponible desde 2,0.
