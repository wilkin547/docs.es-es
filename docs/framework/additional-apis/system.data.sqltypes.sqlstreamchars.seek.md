---
description: 'Más información sobre: SqlStreamChars. Seek (Int64, SeekOrigin) (método)'
title: Método SqlStreamChars. Seek (Int64, SeekOrigin) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 00f71aff95045d566b7932aec3f7e18259b4dfa0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802572"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a>SqlStreamChars. Seek (Int64, SeekOrigin) (método)

Cuando se reemplaza en una clase derivada, se establece la posición dentro de la secuencia actual. El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll. Está pensado para su uso por SQL Server. En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a>Parámetros

`offset`\
Desplazamiento de bytes relacionado con `origin`.

`origin`\
Uno de los valores de enumeración que indica el punto de referencia del que se va a obtener la nueva posición.

## <a name="returns"></a>Devoluciones

<xref:System.Int32>\
La nueva posición dentro de la secuencia actual.

## <a name="remarks"></a>Observaciones

> [!WARNING]
> El `SqlStreamChars.Seek` método es privado y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Data.SqlTypes>

**Ensamblado:** System.Data (en System.Data.dll)

**.NET Framework versiones:** Disponible desde 2,0.
