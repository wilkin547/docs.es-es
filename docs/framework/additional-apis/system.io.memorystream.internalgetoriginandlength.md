---
title: Método MemoryStream. InternalGetOriginAndLength (System.IO)
author: mairaw
ms.author: mairaw
ms.date: 11/19/2019
topic_type:
- apiref
api_name:
- System.IO.MemoryStream.InternalGetOriginAndLength
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: d2bfa087fe2fb247f963cfa687c27056363d5696
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74284046"
---
# <a name="memorystreaminternalgetoriginandlength-method"></a>MemoryStream. InternalGetOriginAndLength (método)

Obtiene los valores internos del origen y la longitud de la secuencia de memoria.

```csharp
internal void InternalGetOriginAndLength(out int origin, out int length)
```

## <a name="parameters"></a>Parámetros

- `origin` <xref:System.Int32>\
  Cuando este método devuelve, el desplazamiento de la matriz de bytes especificada al crear un nuevo objeto <xref:System.IO.MemoryStream>. Contiene 0 si la matriz de bytes se creó mediante <xref:System.IO.MemoryStream>.

- `length` <xref:System.Int32>\
  Cuando este método devuelve, el número de bytes dentro de la secuencia de memoria.

## <a name="remarks"></a>Comentarios

> [!WARNING]
> El método `MemoryStream.InternalGetOriginAndLength` es interno y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.IO>

**Ensamblado:** mscorlib. dll (en mscorlib. dll)

**.NET Framework versiones:** Disponible desde 2,0.
