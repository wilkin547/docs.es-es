---
description: 'Más información sobre: SqlStreamChars. CanSeek (propiedad)'
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
ms.openlocfilehash: 5919a66bef9ac31e0ef15ad4af64b456700605f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802624"
---
# <a name="sqlstreamcharscanseek-property"></a>Propiedad SqlStreamChars. CanSeek

Cuando se reemplaza en una clase derivada, obtiene un valor que indica si la secuencia actual admite la operación de búsqueda. El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess.dll. Está pensado para su uso por SQL Server. En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a>Valor de propiedad

<xref:System.Boolean>\
`true` Si la secuencia actual admite la operación de búsqueda; en caso contrario, `false` .

## <a name="remarks"></a>Observaciones

> [!WARNING]
> La `SqlStreamChars.CanSeek` propiedad es privada y no está diseñada para usarse directamente en el código.
>
> Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Data.SqlTypes>

**Ensamblado:** System.Data (en System.Data.dll)

**.NET Framework versiones:** Disponible desde 2,0.
