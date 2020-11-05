---
title: Control de errores de E/S en .NET
description: Aprenda a controlar errores de E/S en .NET. Asigne códigos de error a excepciones, controle excepciones en operaciones de E/S y controle IOException.
ms.date: 08/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O, exception handling
- I/O, errors
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: bd7112b3052f246a01e4a36d6d425b37cb6174dd
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188047"
---
# <a name="handling-io-errors-in-net"></a>Control de errores de E/S en .NET

Además de las excepciones que se pueden producir en cualquier llamada al método (como <xref:System.OutOfMemoryException> cuando un sistema está sobrecargado o <xref:System.NullReferenceException> debido a errores de programador), los métodos del sistema de archivos de .NET pueden producir las excepciones siguientes:

- <xref:System.IO.IOException?displayProperty=nameWithType>, la clase base de todos los tipos de excepción <xref:System.IO>. Se produce por errores cuyos códigos de retorno del sistema operativo no se asignan directamente a cualquier otro tipo de excepción.
- <xref:System.IO.FileNotFoundException?displayProperty=nameWithType>.
- <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType>.
- <xref:System.IO.DriveNotFoundException??displayProperty=nameWithType>.
- <xref:System.IO.PathTooLongException?displayProperty=nameWithType>.
- <xref:System.OperationCanceledException?displayProperty=nameWithType>.
- <xref:System.UnauthorizedAccessException?displayProperty=nameWithType>.
- <xref:System.ArgumentException?displayProperty=nameWithType>, que se produce para caracteres de ruta no válidos en .NET Framework y en .NET Core 2.0 y versiones anteriores.
- <xref:System.NotSupportedException?displayProperty=nameWithType>, que se produce para dos puntos no válidos en .NET Framework.
- <xref:System.Security.SecurityException?displayProperty=nameWithType>, que se produce para las aplicaciones que se ejecutan con confianza limitada y que carecen de los permisos necesarios solo en .NET Framework. (La plena confianza es el valor predeterminado en .NET Framework).

## <a name="mapping-error-codes-to-exceptions"></a>Asignación de códigos de error a excepciones

Dado que el sistema de archivos es un recurso del sistema operativo, los métodos de E/S de .NET Core y .NET Framework encapsulan llamadas en el sistema operativo subyacente. Cuando se produce un error de E/S en el código ejecutado por el sistema operativo, el sistema operativo devuelve información de error para el método de E/S de .NET. El método después traduce la información de error, normalmente en forma de un código de error, en un tipo de excepción de .NET. En la mayoría de los casos, lo hace convirtiendo directamente el código de error en su correspondiente tipo de excepción; no realiza ninguna asignación especial del error en función del contexto de la llamada al método.

Por ejemplo, en el sistema operativo Windows, una llamada al método que devuelve un código de error `ERROR_FILE_NOT_FOUND`, o bien 0 x 02, se asigna a <xref:System.IO.FileNotFoundException>, y un código de error `ERROR_PATH_NOT_FOUND`, o bien 0 x 03, se asigna a <xref:System.IO.DirectoryNotFoundException>.

Sin embargo, las condiciones precisas en las que el sistema operativo devuelve códigos de error concretos no suelen estar documentadas o, en caso de estarlo, la documentación suele ser escasa. Como resultado, pueden producirse excepciones inesperadas. Por ejemplo, puesto que está trabajando con un directorio en lugar de un archivo, cabría esperar que proporcionar una ruta de acceso de directorio no válida para el constructor <xref:System.IO.DirectoryInfo.%23ctor%2A> produzca <xref:System.IO.DirectoryNotFoundException>. Sin embargo, también puede producir <xref:System.IO.FileNotFoundException>.

## <a name="exception-handling-in-io-operations"></a>Control de excepciones en operaciones de E/S

Debido a esta dependencia en el sistema operativo, condiciones de excepción idénticas (como el caso en que el directorio no encontró el error en nuestro ejemplo) pueden dar lugar a que un método de E/S genere cualquier clase entera de excepciones de E/S. Esto significa que, al llamar a API de E/S, el código debe prepararse para controlar la mayoría de estas excepciones o todas, como se muestra en la siguiente tabla:

| Tipo de excepción | .NET Core, y .NET 5 y versiones posteriores | .NET Framework |
|---|---|---|
| <xref:System.IO.IOException> | Sí | Sí |
| <xref:System.IO.FileNotFoundException> | Sí | Sí |
| <xref:System.IO.DirectoryNotFoundException> | Sí | Sí |
| <xref:System.IO.DriveNotFoundException?> | Sí | Sí |
| <xref:System.IO.PathTooLongException> | Sí | Sí |
| <xref:System.OperationCanceledException> | Sí | Sí |
| <xref:System.UnauthorizedAccessException> | Sí | Sí |
| <xref:System.ArgumentException> | .NET Core 2.0 y versiones anteriores| Sí |
| <xref:System.NotSupportedException> | No | Sí |
| <xref:System.Security.SecurityException> | No | Confianza limitada solo |

## <a name="handling-ioexception"></a>Control de excepciones de E/S

Como la clase base para las excepciones en el espacio de nombres <xref:System.IO>, también se produce <xref:System.IO.IOException> para cualquier código de error que no se asigna a un tipo de excepción predefinido. Esto significa que se puede iniciar con cualquier operación de E/S.

> [!IMPORTANT]
> Dado que <xref:System.IO.IOException> es la clase base de los otros tipos de excepción en el espacio de nombres <xref:System.IO>, se debe controlar en un bloque `catch` después de haber controlado las otras excepciones relacionadas con E/S.

Además, a partir de .NET Core 2.1, se han quitado las comprobaciones de validación de la exactitud de la ruta de acceso (por ejemplo, para asegurarse de que los caracteres no válidos no están presentes en una ruta de acceso), y el tiempo de ejecución produce una excepción que se asigna desde un código de error del sistema operativo y no desde su propio código de validación. La excepción que es más probable que se produzca en este caso es <xref:System.IO.IOException>, aunque también podría generarse cualquier otro tipo de excepción.

Tenga en cuenta que, en el código de control de excepciones, siempre debe controlar la última clase <xref:System.IO.IOException>. De lo contrario, como se trata de la clase base de todas las excepciones de E/S, los bloques catch de las clases derivadas no se evaluarán.

Si se trata de <xref:System.IO.IOException>, puede obtener información de error adicional de la propiedad [IOException.HResult](xref:System.Exception.HResult). Para convertir el valor HResult en un código de error de Win32, quite los 16 bits superiores del valor de 32 bits. En la tabla siguiente se enumeran los códigos de error que pueden encapsularse en <xref:System.IO.IOException>.

| HResult | Constante | Descripción |
| --- | --- | --- |
| ERROR_SHARING_VIOLATION | 32 | Falta el nombre de archivo, o el archivo o directorio está en uso. |
| ERROR_FILE_EXISTS | 80 | El archivo ya existe. |
| ERROR_INVALID_PARAMETER | 87 | El argumento proporcionado al método no es válido. |
| ERROR_ALREADY_EXISTS | 183 | El archivo o directorio ya existe. |

Puede controlarlos con una cláusula `When` en una instrucción catch, como se muestra en el ejemplo siguiente.

[!code-csharp[io-exception-handling](~/samples/snippets/standard/io/io-exceptions/cs/io-exceptions.cs)]
[!code-vb[io-exception-handling](~/samples/snippets/standard/io/io-exceptions/vb/io-exceptions.vb)]

## <a name="see-also"></a>Vea también

- [Controlar y generar excepciones en .NET](../exceptions/index.md)
- [Control de excepciones (biblioteca TPL)](../parallel-programming/exception-handling-task-parallel-library.md)
- [Procedimientos recomendados para excepciones](../exceptions/best-practices-for-exceptions.md)
- [Uso de excepciones específicas en un bloque Catch](../exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)
