---
title: Método Message. WriteStartHeaders (System. ServiceModel. Channels)
author: mairaw
ms.author: mairaw
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.WriteStartHeaders
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: a2c82ee4029c7af0396219f5ded8c999fd01d65b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451291"
---
# <a name="messagewritestartheaders-method"></a>Message. WriteStartHeaders (método)

Escribe el encabezado de inicio en un archivo XML llamando al método <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType>.

```csharp
internal void WriteStartHeaders(XmlDictionaryWriter writer)
```

## <a name="parameters"></a>Parámetros

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  Escritor que se usa para escribir el encabezado de inicio en un archivo XML.

## <a name="remarks"></a>Comentarios

> [!WARNING]
> El método `Message.WriteStartHeaders` es interno y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.ServiceModel.Channels>

**Ensamblado:** System. ServiceModel. dll

**.NET Framework versiones:** Disponible desde 3,0.
