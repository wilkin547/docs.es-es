---
title: Agrupar resultados por claves contiguas (LINQ en C#)
description: Cómo agrupar resultados por claves con LINQ en C#.
ms.date: 08/14/2018
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: b5753c85bb07be4fc84b78a299eece961969ff9d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659909"
---
# <a name="group-results-by-contiguous-keys"></a>Agrupar resultados por claves contiguas

En el ejemplo siguiente se muestra cómo agrupar elementos en fragmentos que representan subsecuencias de claves contiguas. Por ejemplo, suponga que tiene la siguiente secuencia de pares clave-valor:

|Clave|Valor|
|---------|-----------|
|A|We|
|A|think|
|A|that|
|B|Linq|
|C|is|
|A|really|
|B|cool|
|B|!|

Los siguientes grupos se crearán en este orden:

1. We, think, that

2. Linq

3. is

4. really

5. cool, !

La solución se implementa como un método de extensión seguro para subprocesos que devuelve sus resultados mediante transmisión por secuencias. Es decir, genera sus grupos a medida que se desplaza por la secuencia de origen. A diferencia de los operadores `group` u `orderby`, puede comenzar a devolver grupos al llamador antes de que se haya leído toda la secuencia.

La seguridad de subprocesos se logra realizando una copia de cada grupo o fragmento a medida que se recorre en iteración la secuencia de origen, tal y como se explica en los comentarios del código fuente. Si la secuencia de origen tiene una secuencia grande de elementos contiguos, Common Language Runtime puede producir una excepción <xref:System.OutOfMemoryException>.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestran el método de extensión y el código de cliente que lo usa:

[!code-csharp[cscsrefContiguousGroups#1](~/samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]

Para usar el método de extensión en el proyecto, copie la clase estática `MyExtensions` en un archivo de código fuente nuevo o ya existente y, si es necesario, agregue una directiva `using` para el espacio de nombres donde se encuentra.

## <a name="see-also"></a>Vea también

- [Language-Integrated Query (LINQ)](index.md)
