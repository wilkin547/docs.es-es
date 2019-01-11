---
title: Método SqlStreamChars.Read (Char [], Int32, Int32) (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: ce89e5f757034b79d5a60a1abbd49fdb2fdf3f06
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222121"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a>Método SqlStreamChars.Read (Char [], Int32, Int32)

Cuando se invalida en una clase derivada, lee el siguiente conjunto de caracteres del flujo de entrada. El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll. Está pensado para su uso con SQL Server. Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>Parámetros

`buffer`\
Una matriz de caracteres para leer.

`offset`\
Un desplazamiento con respecto al origen.

`count`\
El número de caracteres que leer en la secuencia actual.

## <a name="returns"></a>Valores devueltos

<xref:System.Int32>\
Número total de caracteres leídos en el búfer.

## <a name="remarks"></a>Comentarios

> [!WARNING]
> El `SqlStreamChars.Read` método es privado y no está pensado para usarse directamente en el código.
>
> Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Data.SqlTypes>

**Ensamblado:** System.Data (en System.Data.dll)

**Versiones de .NET framework:** Disponible desde la versión 2.0.