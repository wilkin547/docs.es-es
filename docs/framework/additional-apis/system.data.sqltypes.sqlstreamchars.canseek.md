---
title: Propiedad SqlStreamChars. CanSeek (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: eb32978f62b7d46f0abf715e2bca347592c0fda8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395776"
---
# <a name="sqlstreamcharscanseek-property"></a>Propiedad SqlStreamChars. CanSeek

Cuando se reemplaza en una clase derivada, obtiene un valor que indica si la secuencia actual admite la operación de búsqueda. El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess. dll. Está pensado para su uso por SQL Server. En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a>Valor de propiedad

<xref:System.Boolean>\
`true` si la secuencia actual admite la operación de búsqueda; de lo contrario, `false`.

## <a name="remarks"></a>Comentarios

> [!WARNING]
> La propiedad `SqlStreamChars.CanSeek` es privada y no está diseñada para usarse directamente en el código.
>
> Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Data.SqlTypes>

**Ensamblado:** System. Data (en System. Data. dll)

**.NET Framework versiones:** Disponible desde 2,0.
