---
title: Propiedad SqlStreamChars.Length (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/19/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: ac6e6af9c9411ebc25039e0992133fae2b35ee23
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221186"
---
# <a name="sqlstreamcharslength-property"></a>Propiedad SqlStreamChars.Length

Cuando se invalida en una clase derivada, obtiene la longitud de la secuencia actual. El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess.dll. Está pensado para su uso con SQL Server. Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.

## <a name="syntax"></a>Sintaxis

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a>Valor de propiedad

<xref:System.Int64>\
Longitud de la secuencia.

## <a name="remarks"></a>Comentarios

> [!WARNING]
> El `SqlStreamChars.Length` propiedad es privada y no está pensada para usarse directamente en el código.
>
> Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Data.SqlTypes>

**Ensamblado:** System.Data (en System.Data.dll)

**Versiones de .NET framework:** Disponible desde la versión 2.0.