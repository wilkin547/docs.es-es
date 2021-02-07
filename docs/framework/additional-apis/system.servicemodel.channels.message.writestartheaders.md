---
description: 'Más información sobre: Message. WriteStartHeaders (método)'
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
ms.openlocfilehash: 20cadf5f1eecf6d8e02c5dc4597889abaef4ec36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699368"
---
# <a name="messagewritestartheaders-method"></a>Message. WriteStartHeaders (método)

Escribe el encabezado de inicio en un archivo XML llamando al <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType> método.

```csharp
internal void WriteStartHeaders(XmlDictionaryWriter writer)
```

## <a name="parameters"></a>Parámetros

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  Escritor que se usa para escribir el encabezado de inicio en un archivo XML.

## <a name="remarks"></a>Observaciones

> [!WARNING]
> El `Message.WriteStartHeaders` método es interno y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.ServiceModel.Channels>

**Ensamblado:** System.ServiceModel.dll

**.NET Framework versiones:** Disponible desde 3,0.
