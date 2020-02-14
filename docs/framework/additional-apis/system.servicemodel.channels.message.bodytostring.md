---
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
ms.openlocfilehash: 9f1f852c0bd82299fd40afe66a5f90cd7c0335cf
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215506"
---
# <a name="messagebodytostring-method"></a>Message. BodyToString (método)

Convierte el cuerpo del mensaje en una cadena mediante una llamada al método <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A?displayProperty=nameWithType>.

```csharp
internal void BodyToString(XmlDictionaryWriter writer);
```

## <a name="parameters"></a>Parámetros

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  Escritor que se utiliza para convertir el cuerpo del mensaje en una cadena.

## <a name="remarks"></a>Observaciones

> [!WARNING]
> El método `Message.BodyToString` es interno y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.ServiceModel.Channels>

**Ensamblado:** System. ServiceModel. dll

**.NET Framework versiones:** Disponible desde 3,0.
