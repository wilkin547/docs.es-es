---
title: Propiedad SqlStreamChars.CanSeek (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: bde4764af9d0160997dc202f722a12393cfa59c1
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826855"
---
# <a name="sqlstreamcharscanseek-property"></a>Propiedad SqlStreamChars.CanSeek

Cuando se invalida en una clase derivada, obtiene un valor que indica si la secuencia actual admite la operación de búsqueda. El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess.dll. Está pensado para su uso con SQL Server. Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a>Valor de propiedad

<xref:System.Boolean>\
`true` Si la secuencia actual admite la operación de búsqueda; en caso contrario, `false`.

## <a name="remarks"></a>Comentarios

> [!WARNING]
> El `SqlStreamChars.CanSeek` propiedad es privada y no está pensada para usarse directamente en el código.
>
> Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Data.SqlTypes>

**Ensamblado:** System.Data (en System.Data.dll)

**Versiones de .NET framework:** Disponible desde la versión 2.0.