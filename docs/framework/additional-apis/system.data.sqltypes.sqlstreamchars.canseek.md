---
title: Propiedad SqlStreamChars.CanSeek (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/19/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 0145fe87e2c8aa3dd40e73f0089fe40b6b6cca30
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152738"
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