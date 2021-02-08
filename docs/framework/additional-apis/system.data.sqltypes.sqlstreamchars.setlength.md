---
description: 'Más información sobre: SqlStreamChars. SetLength (Int64) (método)'
title: Método SqlStreamChars. SetLength (Int64) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d10ce55126ae09062fe895c3a686ce5d94174554
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804145"
---
# <a name="sqlstreamcharssetlengthint64-method"></a>SqlStreamChars. SetLength (Int64) (método)

Cuando se reemplaza en una clase derivada, libera los recursos utilizados por la secuencia. El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll. Está pensado para su uso por SQL Server. En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a>Parámetros

`value`\
Longitud deseada de la secuencia actual, en bytes.

## <a name="remarks"></a>Observaciones

> [!WARNING]
> El `SqlStreamChars.SetLength` método es privado y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Data.SqlTypes>

**Ensamblado:** System.Data (en System.Data.dll)

**.NET Framework versiones:** Disponible desde 2,0.
