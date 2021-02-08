---
description: 'Más información sobre: SqlStreamChars. Read (Char [], Int32, Int32) (método)'
title: Método SqlStreamChars. Read (Char [], Int32, Int32) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: a899ddff7b7242fcc32aaf7b7f7794970596027b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802585"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a>SqlStreamChars. Read (Char [], Int32, Int32) (método)

Cuando se invalida en una clase derivada, lee el siguiente conjunto de caracteres del flujo de entrada. El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll. Está pensado para su uso por SQL Server. En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>Parámetros

`buffer`\
Matriz de caracteres que se va a leer.

`offset`\
Desplazamiento relativo al origen.

`count`\
Número de caracteres que se van a leer de la secuencia actual.

## <a name="returns"></a>Devoluciones

<xref:System.Int32>\
Número total de caracteres leídos en el búfer.

## <a name="remarks"></a>Observaciones

> [!WARNING]
> El `SqlStreamChars.Read` método es privado y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Data.SqlTypes>

**Ensamblado:** System.Data (en System.Data.dll)

**.NET Framework versiones:** Disponible desde 2,0.
