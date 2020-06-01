---
title: Memoria e intervalos
ms.date: 10/03/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Memory<T>
- Span<T>
- buffers"
- pipeline processing
ms.openlocfilehash: c60c08d27c0e41228a15e8acdf01a9af28a23762
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201963"
---
# <a name="memory--and-span-related-types"></a>Tipos relacionados con el intervalo y la memoria

A partir de .NET Core 2.1, .NET incluye una serie de tipos interrelacionados que representan una región contigua de memoria arbitraria fuertemente tipada. Se incluyen los siguientes:

- <xref:System.Span%601?displayProperty=nameWithType>, un tipo que se usa para acceder a una región de memoria contigua. Se puede respaldar una instancia de <xref:System.Span%601> mediante cualquier matriz de tipo `T`, un elemento <xref:System.String>, a búfer asignado con [stackalloc](../../csharp/language-reference/operators/stackalloc.md) o un puntero a memoria sin administrar. Como debe asignarse en la pila, tiene una serie de restricciones. Por ejemplo, un campo de una clase no puede ser de tipo <xref:System.Span%601>, ni se puede usar un intervalo en operaciones asincrónicas.

- <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, una versión inmutable de la estructura <xref:System.Span%601>.

- <xref:System.Memory%601?displayProperty=nameWithType>, una región contigua de memoria que se asigna en el montón administrado en lugar de en la pila. Se puede respaldar una instancia de <xref:System.Memory%601> mediante cualquier matriz de tipo `T` o un elemento <xref:System.String>. Dado que puede almacenarse en el montón administrado, <xref:System.Memory%601> no tiene ninguna de las limitaciones de <xref:System.Span%601>.

- <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>, una versión inmutable de la estructura <xref:System.Memory%601>.

- <xref:System.Buffers.MemoryPool%601?displayProperty=nameWithType>, que asigna bloques de memoria fuertemente tipados de un grupo de memoria a un propietario. Se pueden alquilar instancias de <xref:System.Buffers.IMemoryOwner%601> del grupo mediante la llamada a <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType> y liberarse de nuevo en el grupo mediante la llamada a <xref:System.Buffers.MemoryPool%601.Dispose?displayProperty=nameWithType>.

- <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>, que representa el propietario de un bloque de memoria y controla su administración de duración.

- <xref:System.Buffers.MemoryManager%601>, una clase base abstracta que puede usarse para reemplazar la implementación de <xref:System.Memory%601> para que <xref:System.Memory%601> pueda respaldarse mediante tipos adicionales, como controladores seguros. <xref:System.Buffers.MemoryManager%601> está pensado para escenarios avanzados.

- <xref:System.ArraySegment%601>, un contenedor para un determinado número de elementos de matriz, que comienza en un índice determinado.

- <xref:System.MemoryExtensions?displayProperty=nameWithType>, una colección de métodos de extensión para convertir cadenas, matrices y segmentos de matriz en bloques de <xref:System.Memory%601>.

> [!NOTE]
> En plataformas anteriores, <xref:System.Span%601> y <xref:System.Memory%601> están disponibles en el [paquete NuGet System.Memory](https://www.nuget.org/packages/System.Memory/).

Para obtener más información, vea el espacio de nombres <xref:System.Buffers?displayProperty=nameWithType>.

## <a name="working-with-memory-and-span"></a>Uso de memoria e intervalo

Dado que los tipos relacionados con el intervalo y la memoria se usan normalmente para almacenar datos en una canalización de procesamiento, es importante que los desarrolladores sigan un conjunto de procedimientos recomendados al usar <xref:System.Span%601>, <xref:System.Memory%601> y tipos relacionados. Estos procedimientos recomendados se documentan en las directrices de uso de [Memory\<T> y Span\<T>](memory-t-usage-guidelines.md).

## <a name="see-also"></a>Vea también

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
- <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>
- <xref:System.Buffers?displayProperty=nameWithType>
