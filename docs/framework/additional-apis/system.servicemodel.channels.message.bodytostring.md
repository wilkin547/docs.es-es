---
description: 'Más información sobre: Message. BodyToString (método)'
title: Método Message. BodyToString (System. ServiceModel. Channels)
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.BodyToString
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: babcd881d191ff46b98e9999c4ff04166479a68d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699381"
---
# <a name="messagebodytostring-method"></a>Message. BodyToString (método)

Convierte el cuerpo del mensaje en una cadena mediante una llamada al <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A?displayProperty=nameWithType> método.

```csharp
internal void BodyToString(XmlDictionaryWriter writer);
```

## <a name="parameters"></a>Parámetros

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  Escritor que se utiliza para convertir el cuerpo del mensaje en una cadena.

## <a name="remarks"></a>Observaciones

> [!WARNING]
> El `Message.BodyToString` método es interno y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.ServiceModel.Channels>

**Ensamblado:** System.ServiceModel.dll

**.NET Framework versiones:** Disponible desde 3,0.
