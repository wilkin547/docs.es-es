---
title: Método SqlStreamChars.Seek (Int64, SeekOrigin) (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d52a1cd4dd70c29fc1af3fcf50c4f9b0c90125df
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827388"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a>Método SqlStreamChars.Seek (Int64, SeekOrigin)

Cuando se reemplaza en una clase derivada, se establece la posición dentro de la secuencia actual. El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll. Está pensado para su uso con SQL Server. Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a>Parámetros

`offset`\
Desplazamiento de bytes relativo a `origin`.

`origin`\
Uno de los valores de enumeración que indica el punto de referencia desde el que se va a obtener la nueva posición.

## <a name="returns"></a>Valores devueltos

<xref:System.Int32>\
La nueva posición dentro de la secuencia actual.

## <a name="remarks"></a>Comentarios

> [!WARNING]
> El `SqlStreamChars.Seek` método es privado y no está pensado para usarse directamente en el código.
>
> Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Data.SqlTypes>

**Ensamblado:** System.Data (en System.Data.dll)

**Versiones de .NET framework:** Disponible desde la versión 2.0.