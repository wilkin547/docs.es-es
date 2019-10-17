---
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
ms.openlocfilehash: 291d6e9395581f2370dafc728521a314d54a686d
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395721"
---
# <a name="sqlstreamcharssetlengthint64-method"></a>SqlStreamChars. SetLength (Int64) (método)

Cuando se reemplaza en una clase derivada, libera los recursos utilizados por la secuencia. El ensamblado que contiene este método tiene una relación de confianza con SQLAccess. dll. Está pensado para su uso por SQL Server. En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a>Parámetros

`value`\
Longitud deseada de la secuencia actual, en bytes.

## <a name="remarks"></a>Comentarios

> [!WARNING]
> El método `SqlStreamChars.SetLength` es privado y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Data.SqlTypes>

**Ensamblado:** System. Data (en System. Data. dll)

**.NET Framework versiones:** Disponible desde 2,0.
