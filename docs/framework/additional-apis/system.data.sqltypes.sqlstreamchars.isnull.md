---
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
ms.openlocfilehash: d80f653724b3ef0a1cadb69a5f72b1d9455597d6
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395731"
---
# <a name="sqlstreamcharsisnull-property"></a>SqlStreamChars. IsNull (propiedad)

Cuando se reemplaza en una clase derivada, obtiene un valor que indica si la secuencia es `null`. El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess. dll. Está pensado para su uso por SQL Server. En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.

## <a name="syntax"></a>Sintaxis

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a>Valor de propiedad

<xref:System.Boolean>\
`true` si la secuencia es `null`; de lo contrario, `false`.

## <a name="remarks"></a>Comentarios

> [!WARNING]
> La propiedad `SqlStreamChars.IsNull` es privada y no está diseñada para usarse directamente en el código.
>
> Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Data.SqlTypes>

**Ensamblado:** System. Data (en System. Data. dll)

**.NET Framework versiones:** Disponible desde 2,0.
