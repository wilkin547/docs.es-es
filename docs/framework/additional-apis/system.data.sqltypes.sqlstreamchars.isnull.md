---
description: 'Más información sobre: SqlStreamChars. IsNull (propiedad)'
title: Propiedad SqlStreamChars. IsNull (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: b1408a8ba9cd1c38f73d5fa6b818f441d6223bc8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791925"
---
# <a name="sqlstreamcharsisnull-property"></a>SqlStreamChars. IsNull (propiedad)

Cuando se reemplaza en una clase derivada, obtiene un valor que indica si la secuencia es `null` . El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess.dll. Está pensado para su uso por SQL Server. En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.

## <a name="syntax"></a>Sintaxis

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a>Valor de propiedad

<xref:System.Boolean>\
`true` Si la secuencia es `null` ; en caso contrario, `false` .

## <a name="remarks"></a>Observaciones

> [!WARNING]
> La `SqlStreamChars.IsNull` propiedad es privada y no está diseñada para usarse directamente en el código.
>
> Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Data.SqlTypes>

**Ensamblado:** System.Data (en System.Data.dll)

**.NET Framework versiones:** Disponible desde 2,0.
