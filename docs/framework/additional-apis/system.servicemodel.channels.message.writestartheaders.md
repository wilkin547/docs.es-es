---
title: Método Message. WriteStartHeaders (System. ServiceModel. Channels)
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.WriteStartHeaders
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: c826e6a3b976e5705e9815586441e8a25b64f76e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214861"
---
# <a name="messagewritestartheaders-method"></a>Message. WriteStartHeaders (método)

Escribe el encabezado de inicio en un archivo XML llamando al método <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType>.

```csharp
internal void WriteStartHeaders(XmlDictionaryWriter writer)
```

## <a name="parameters"></a>Parámetros

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  Escritor que se usa para escribir el encabezado de inicio en un archivo XML.

## <a name="remarks"></a>Observaciones

> [!WARNING]
> El método `Message.WriteStartHeaders` es interno y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.ServiceModel.Channels>

**Ensamblado:** System. ServiceModel. dll

**.NET Framework versiones:** Disponible desde 3,0.
