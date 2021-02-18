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
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a><span data-ttu-id="5a3e9-104">Procedimiento Escribir en un archivo de texto (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="5a3e9-104">How to write to a text file (C# Programming Guide)</span></span>

<span data-ttu-id="5a3e9-105">En este artículo hay varios ejemplos en los que muestran distintas formas de escribir texto en un archivo.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-105">In this article, there are several examples showing various ways to write text to a file.</span></span> <span data-ttu-id="5a3e9-106">En los dos primeros se usan métodos estáticos útiles de la clase <xref:System.IO.File?displayProperty=nameWithType> para escribir cada elemento de cualquier interfaz `IEnumerable<string>` y un elemento `string` en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-106">The first two examples use static convenience methods on the <xref:System.IO.File?displayProperty=nameWithType> class to write each element of any `IEnumerable<string>` and a `string` to a text file.</span></span> <span data-ttu-id="5a3e9-107">En el tercer ejemplo se muestra cómo agregar texto a un archivo cuando hay que procesar cada línea individualmente a medida que se escribe en el archivo.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-107">The third example shows how to add text to a file when you have to process each line individually as you write to the file.</span></span> <span data-ttu-id="5a3e9-108">En los tres primeros ejemplos se sobrescribe todo el contenido existente del archivo.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-108">In the first three examples, you overwrite all existing content in the file.</span></span> <span data-ttu-id="5a3e9-109">En el último ejemplo se muestra cómo anexar texto a un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-109">The final example shows how to append text to an existing file.</span></span>

 <span data-ttu-id="5a3e9-110">Todos estos ejemplos escriben literales de cadena en los archivos.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-110">These examples all write string literals to files.</span></span> <span data-ttu-id="5a3e9-111">Si quiere aplicar formato al texto escrito en un archivo, use el método <xref:System.String.Format%2A> o la característica [interpolación de cadenas](../../language-reference/tokens/interpolated.md) de C#.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-111">If you want to format text written to a file, use the <xref:System.String.Format%2A> method or C# [string interpolation](../../language-reference/tokens/interpolated.md) feature.</span></span>

## <a name="write-a-collection-of-strings-to-a-file"></a><span data-ttu-id="5a3e9-112">Escritura de una colección de cadenas en un archivo</span><span class="sxs-lookup"><span data-stu-id="5a3e9-112">Write a collection of strings to a file</span></span>

:::code language="csharp" source="snippets/write-text/WriteAllLines.cs":::

<span data-ttu-id="5a3e9-113">En el ejemplo de código fuente anterior:</span><span class="sxs-lookup"><span data-stu-id="5a3e9-113">The preceding source code example:</span></span>

- <span data-ttu-id="5a3e9-114">Se crea una instancia de una matriz de cadenas con tres valores.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-114">Instantiates a string array with three values.</span></span>
- <span data-ttu-id="5a3e9-115">Se espera una llamada a <xref:System.IO.File.WriteAllLinesAsync%2A?displayProperty=nameWithType> que:</span><span class="sxs-lookup"><span data-stu-id="5a3e9-115">Awaits a call to <xref:System.IO.File.WriteAllLinesAsync%2A?displayProperty=nameWithType> which:</span></span>

  - <span data-ttu-id="5a3e9-116">Crea de forma asincrónica un nombre de archivo *WriteLines.txt*.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-116">Asynchronously creates a file name *WriteLines.txt*.</span></span> <span data-ttu-id="5a3e9-117">Si el archivo ya existe, se sobrescribe.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-117">If the file already exists, it is overwritten.</span></span>
  - <span data-ttu-id="5a3e9-118">Escribe las líneas especificadas en el archivo.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-118">Writes the given lines to the file.</span></span>
  - <span data-ttu-id="5a3e9-119">Cierra el archivo, y vacía y elimina automáticamente según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-119">Closes the file, automatically flushing and disposing as needed.</span></span>

## <a name="write-one-string-to-a-file"></a><span data-ttu-id="5a3e9-120">Escritura de una cadena en un archivo</span><span class="sxs-lookup"><span data-stu-id="5a3e9-120">Write one string to a file</span></span>

:::code language="csharp" source="snippets/write-text/WriteAllText.cs":::

<span data-ttu-id="5a3e9-121">En el ejemplo de código fuente anterior:</span><span class="sxs-lookup"><span data-stu-id="5a3e9-121">The preceding source code example:</span></span>

- <span data-ttu-id="5a3e9-122">Se crea una instancia de una cadena en función del literal de cadena asignado.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-122">Instantiates a string given the assigned string literal.</span></span>
- <span data-ttu-id="5a3e9-123">Se espera una llamada a <xref:System.IO.File.WriteAllTextAsync%2A?displayProperty=nameWithType> que:</span><span class="sxs-lookup"><span data-stu-id="5a3e9-123">Awaits a call to <xref:System.IO.File.WriteAllTextAsync%2A?displayProperty=nameWithType> which:</span></span>

  - <span data-ttu-id="5a3e9-124">Crea de forma asincrónica un nombre de archivo *WriteText.txt*.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-124">Asynchronously creates a file name *WriteText.txt*.</span></span> <span data-ttu-id="5a3e9-125">Si el archivo ya existe, se sobrescribe.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-125">If the file already exists, it is overwritten.</span></span>
  - <span data-ttu-id="5a3e9-126">Escribe el texto especificado en el archivo.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-126">Writes the given text to the file.</span></span>
  - <span data-ttu-id="5a3e9-127">Cierra el archivo, y vacía y elimina automáticamente según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-127">Closes the file, automatically flushing and disposing as needed.</span></span>

## <a name="write-selected-strings-from-an-array-to-a-file"></a><span data-ttu-id="5a3e9-128">Escritura de cadenas seleccionadas de una matriz en un archivo</span><span class="sxs-lookup"><span data-stu-id="5a3e9-128">Write selected strings from an array to a file</span></span>

:::code language="csharp" source="snippets/write-text/StreamWriterOne.cs":::

<span data-ttu-id="5a3e9-129">En el ejemplo de código fuente anterior:</span><span class="sxs-lookup"><span data-stu-id="5a3e9-129">The preceding source code example:</span></span>

- <span data-ttu-id="5a3e9-130">Se crea una instancia de una matriz de cadenas con tres valores.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-130">Instantiates a string array with three values.</span></span>
- <span data-ttu-id="5a3e9-131">Se crea una instancia de un objeto <xref:System.IO.StreamWriter> con una ruta de acceso de archivo de *WriteLines2.txt* como una [declaración using](../../whats-new/csharp-8.md#using-declarations).</span><span class="sxs-lookup"><span data-stu-id="5a3e9-131">Instantiates a <xref:System.IO.StreamWriter> with a file path of *WriteLines2.txt* as a [using declaration](../../whats-new/csharp-8.md#using-declarations).</span></span>
- <span data-ttu-id="5a3e9-132">Itera por todas las líneas.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-132">Iterates through all the lines.</span></span>
- <span data-ttu-id="5a3e9-133">Espera condicionalmente una llamada a <xref:System.IO.StreamWriter.WriteLineAsync(System.String)?displayProperty=nameWithType>, que escribe la línea en el archivo cuando la línea no contiene `"Second"`.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-133">Conditionally awaits a call to <xref:System.IO.StreamWriter.WriteLineAsync(System.String)?displayProperty=nameWithType>, which writes the line to the file when the line doesn't contain `"Second"`.</span></span>

## <a name="append-text-to-an-existing-file"></a><span data-ttu-id="5a3e9-134">Anexión de texto a un archivo existente</span><span class="sxs-lookup"><span data-stu-id="5a3e9-134">Append text to an existing file</span></span>

:::code language="csharp" source="snippets/write-text/StreamWriterTwo.cs":::

<span data-ttu-id="5a3e9-135">En el ejemplo de código fuente anterior:</span><span class="sxs-lookup"><span data-stu-id="5a3e9-135">The preceding source code example:</span></span>

- <span data-ttu-id="5a3e9-136">Se crea una instancia de una matriz de cadenas con tres valores.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-136">Instantiates a string array with three values.</span></span>
- <span data-ttu-id="5a3e9-137">Crea una instancia de un objeto <xref:System.IO.StreamWriter> con una ruta de acceso de archivo de *WriteLines2.txt* como una [declaración using](../../whats-new/csharp-8.md#using-declarations), y se pasa `true` para anexar.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-137">Instantiates a <xref:System.IO.StreamWriter> with a file path of *WriteLines2.txt* as a [using declaration](../../whats-new/csharp-8.md#using-declarations), passing in `true` to append.</span></span>
- <span data-ttu-id="5a3e9-138">Espera una llamada a <xref:System.IO.StreamWriter.WriteLineAsync(System.String)?displayProperty=nameWithType>, que escribe la cadena en el archivo como una línea anexada.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-138">Awaits a call to <xref:System.IO.StreamWriter.WriteLineAsync(System.String)?displayProperty=nameWithType>, which writes the string to the file as an appended line.</span></span>

## <a name="exceptions"></a><span data-ttu-id="5a3e9-139">Excepciones</span><span class="sxs-lookup"><span data-stu-id="5a3e9-139">Exceptions</span></span>

<span data-ttu-id="5a3e9-140">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="5a3e9-140">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="5a3e9-141"><xref:System.InvalidOperationException>; El archivo ya existe y es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-141"><xref:System.InvalidOperationException>: The file exists and is read-only.</span></span>
- <span data-ttu-id="5a3e9-142"><xref:System.IO.PathTooLongException>; Puede que el nombre de ruta de acceso sea demasiado largo.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-142"><xref:System.IO.PathTooLongException>: The path name may be too long.</span></span>
- <span data-ttu-id="5a3e9-143"><xref:System.IO.IOException>; Es posible que el disco esté lleno.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-143"><xref:System.IO.IOException>: The disk may be full.</span></span>

<span data-ttu-id="5a3e9-144">Existen condiciones adicionales que pueden iniciar excepciones cuando se trabaja con el sistema de archivos; es mejor programar de forma defensiva.</span><span class="sxs-lookup"><span data-stu-id="5a3e9-144">There are additional conditions that may cause exceptions when working with the file system, it is best to program defensively.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a3e9-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a3e9-145">See also</span></span>

- [<span data-ttu-id="5a3e9-146">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5a3e9-146">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5a3e9-147">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="5a3e9-147">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
- [<span data-ttu-id="5a3e9-148">Ejemplo: guardar una colección en el almacenamiento para la aplicación</span><span class="sxs-lookup"><span data-stu-id="5a3e9-148">Sample: Save a collection to Application Storage</span></span>](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
