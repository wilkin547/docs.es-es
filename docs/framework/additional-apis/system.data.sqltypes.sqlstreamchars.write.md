---
title: Método SqlStreamChars. Write (Char [], Int32, Int32) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 9d952041122ceb3824712bd81cab7ce4789c9db8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395586"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a>SqlStreamChars. Write (Char [], Int32, Int32) (método)

Cuando se reemplaza en una clase derivada, escribe una secuencia de caracteres en la secuencia actual y avanza la posición actual dentro de la secuencia según el número de caracteres escritos. El ensamblado que contiene este método tiene una relación de confianza con SQLAccess. dll. Está pensado para su uso por SQL Server. En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>Parámetros

`buffer`  
Matriz de caracteres que se va a escribir.

`offset`  
Desplazamiento relativo al origen.

`count`  
Número de caracteres que se van a escribir en la secuencia actual.

## <a name="remarks"></a>Comentarios

> [!WARNING]
> El método `SqlStreamChars.Write` es privado y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método de escritura en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Data.SqlTypes>

**Ensamblado:** System. Data (en System. Data. dll)

**.NET Framework versiones:** Disponible desde 2,0.
