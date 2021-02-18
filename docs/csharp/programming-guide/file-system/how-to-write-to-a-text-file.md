---
title: 'Procedimiento Escribir en un archivo de texto: Guía de programación de C#'
description: Aprenda a escribir un archivo de texto con C#. Vea varios ejemplos de código y examine los recursos adicionales disponibles.
ms.date: 02/11/2021
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.topic: how-to
ms.custom: contperf-fy21q3
ms.openlocfilehash: ecc3ba73161d4f4571bbc6ae0c9aaa3337586ef7
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475622"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>Procedimiento Escribir en un archivo de texto (Guía de programación de C#)

En este artículo hay varios ejemplos en los que muestran distintas formas de escribir texto en un archivo. En los dos primeros se usan métodos estáticos útiles de la clase <xref:System.IO.File?displayProperty=nameWithType> para escribir cada elemento de cualquier interfaz `IEnumerable<string>` y un elemento `string` en un archivo de texto. En el tercer ejemplo se muestra cómo agregar texto a un archivo cuando hay que procesar cada línea individualmente a medida que se escribe en el archivo. En los tres primeros ejemplos se sobrescribe todo el contenido existente del archivo. En el último ejemplo se muestra cómo anexar texto a un archivo existente.

 Todos estos ejemplos escriben literales de cadena en los archivos. Si quiere aplicar formato al texto escrito en un archivo, use el método <xref:System.String.Format%2A> o la característica [interpolación de cadenas](../../language-reference/tokens/interpolated.md) de C#.

## <a name="write-a-collection-of-strings-to-a-file"></a>Escritura de una colección de cadenas en un archivo

:::code language="csharp" source="snippets/write-text/WriteAllLines.cs":::

En el ejemplo de código fuente anterior:

- Se crea una instancia de una matriz de cadenas con tres valores.
- Se espera una llamada a <xref:System.IO.File.WriteAllLinesAsync%2A?displayProperty=nameWithType> que:

  - Crea de forma asincrónica un nombre de archivo *WriteLines.txt*. Si el archivo ya existe, se sobrescribe.
  - Escribe las líneas especificadas en el archivo.
  - Cierra el archivo, y vacía y elimina automáticamente según sea necesario.

## <a name="write-one-string-to-a-file"></a>Escritura de una cadena en un archivo

:::code language="csharp" source="snippets/write-text/WriteAllText.cs":::

En el ejemplo de código fuente anterior:

- Se crea una instancia de una cadena en función del literal de cadena asignado.
- Se espera una llamada a <xref:System.IO.File.WriteAllTextAsync%2A?displayProperty=nameWithType> que:

  - Crea de forma asincrónica un nombre de archivo *WriteText.txt*. Si el archivo ya existe, se sobrescribe.
  - Escribe el texto especificado en el archivo.
  - Cierra el archivo, y vacía y elimina automáticamente según sea necesario.

## <a name="write-selected-strings-from-an-array-to-a-file"></a>Escritura de cadenas seleccionadas de una matriz en un archivo

:::code language="csharp" source="snippets/write-text/StreamWriterOne.cs":::

En el ejemplo de código fuente anterior:

- Se crea una instancia de una matriz de cadenas con tres valores.
- Se crea una instancia de un objeto <xref:System.IO.StreamWriter> con una ruta de acceso de archivo de *WriteLines2.txt* como una [declaración using](../../whats-new/csharp-8.md#using-declarations).
- Itera por todas las líneas.
- Espera condicionalmente una llamada a <xref:System.IO.StreamWriter.WriteLineAsync(System.String)?displayProperty=nameWithType>, que escribe la línea en el archivo cuando la línea no contiene `"Second"`.

## <a name="append-text-to-an-existing-file"></a>Anexión de texto a un archivo existente

:::code language="csharp" source="snippets/write-text/StreamWriterTwo.cs":::

En el ejemplo de código fuente anterior:

- Se crea una instancia de una matriz de cadenas con tres valores.
- Crea una instancia de un objeto <xref:System.IO.StreamWriter> con una ruta de acceso de archivo de *WriteLines2.txt* como una [declaración using](../../whats-new/csharp-8.md#using-declarations), y se pasa `true` para anexar.
- Espera una llamada a <xref:System.IO.StreamWriter.WriteLineAsync(System.String)?displayProperty=nameWithType>, que escribe la cadena en el archivo como una línea anexada.

## <a name="exceptions"></a>Excepciones

Las condiciones siguientes pueden provocar una excepción:

- <xref:System.InvalidOperationException>; El archivo ya existe y es de solo lectura.
- <xref:System.IO.PathTooLongException>; Puede que el nombre de ruta de acceso sea demasiado largo.
- <xref:System.IO.IOException>; Es posible que el disco esté lleno.

Existen condiciones adicionales que pueden iniciar excepciones cuando se trabaja con el sistema de archivos; es mejor programar de forma defensiva.

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Registro y sistema de archivos (Guía de programación de C#)](./index.md)
- [Ejemplo: guardar una colección en el almacenamiento para la aplicación](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
