---
description: 'Más información sobre: método MemoryStream. InternalGetOriginAndLength'
title: Método MemoryStream. InternalGetOriginAndLength (System.IO)
ms.date: 11/19/2019
topic_type:
- apiref
api_name:
- System.IO.MemoryStream.InternalGetOriginAndLength
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 4232852c0835a43454f36271a43062e1240297a5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802546"
---
# <a name="memorystreaminternalgetoriginandlength-method"></a>Método MemoryStream.InternalGetOriginAndLength

Obtiene los valores internos del origen y la longitud de la secuencia de memoria.

```csharp
internal void InternalGetOriginAndLength(out int origin, out int length)
```

## <a name="parameters"></a>Parámetros

- `origin` <xref:System.Int32>\
  Cuando este método devuelve, el desplazamiento de la matriz de bytes especificada al crear un nuevo <xref:System.IO.MemoryStream> objeto. Contiene 0 si la matriz de bytes fue creada por <xref:System.IO.MemoryStream> .

- `length` <xref:System.Int32>\
  Cuando este método devuelve, el número de bytes dentro de la secuencia de memoria.

## <a name="remarks"></a>Observaciones

> [!WARNING]
> El `MemoryStream.InternalGetOriginAndLength` método es interno y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.IO>

**Ensamblado:** mscorlib.dll (en mscorlib.dll)

**.NET Framework versiones:** Disponible desde 2,0.
