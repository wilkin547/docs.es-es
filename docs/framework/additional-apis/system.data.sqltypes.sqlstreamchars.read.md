---
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
ms.openlocfilehash: 9c8a1526e75fdc304022e74a7cc52506762489ea
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395750"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a>SqlStreamChars. Read (Char [], Int32, Int32) (método)

Cuando se invalida en una clase derivada, lee el siguiente conjunto de caracteres del flujo de entrada. El ensamblado que contiene este método tiene una relación de confianza con SQLAccess. dll. Está pensado para su uso por SQL Server. En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.

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

## <a name="returns"></a>Valores devueltos

<xref:System.Int32>\
Número total de caracteres leídos en el búfer.

## <a name="remarks"></a>Comentarios

> [!WARNING]
> El método `SqlStreamChars.Read` es privado y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Data.SqlTypes>

**Ensamblado:** System. Data (en System. Data. dll)

**.NET Framework versiones:** Disponible desde 2,0.
