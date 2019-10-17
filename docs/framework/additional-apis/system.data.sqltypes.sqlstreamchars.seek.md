---
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
ms.openlocfilehash: db8aba0a86c140ba62af8056011226532d415951
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395599"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a>SqlStreamChars. Seek (Int64, SeekOrigin) (método)

Cuando se reemplaza en una clase derivada, se establece la posición dentro de la secuencia actual. El ensamblado que contiene este método tiene una relación de confianza con SQLAccess. dll. Está pensado para su uso por SQL Server. En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a>Parámetros

`offset`\
Desplazamiento en bytes en relación con `origin`.

`origin`\
Uno de los valores de enumeración que indica el punto de referencia del que se va a obtener la nueva posición.

## <a name="returns"></a>Valores devueltos

<xref:System.Int32>\
La nueva posición dentro de la secuencia actual.

## <a name="remarks"></a>Comentarios

> [!WARNING]
> El método `SqlStreamChars.Seek` es privado y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Data.SqlTypes>

**Ensamblado:** System. Data (en System. Data. dll)

**.NET Framework versiones:** Disponible desde 2,0.
