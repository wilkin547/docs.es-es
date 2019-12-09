---
title: 'Estructura del programa de C#: un paseo por el lenguaje C#'
description: Conozca más acerca de los bloques de compilación básicos de un programa de C#.
ms.date: 08/10/2016
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
ms.openlocfilehash: 5e095e71549ed3eec6c73e6a134fdb5a64fb63c0
ms.sourcegitcommit: 68a4b28242da50e1d25aab597c632767713a6f81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "74884389"
---
# <a name="program-structure"></a>Estructura del programa

Los principales conceptos organizativos en C# son ***programas***, ***espacios de nombres***, ***tipos***, ***miembros*** y ***ensamblados***. Los programas de C# constan de uno o más archivos de origen. Los programas declaran tipos, que contienen miembros y pueden organizarse en espacios de nombres. Las clases e interfaces son ejemplos de tipos. Los campos, los métodos, las propiedades y los eventos son ejemplos de miembros. Cuando se compilan programas de C#, se empaquetan físicamente en ensamblados. Normalmente, los ensamblados tienen la extensión de archivo `.exe` o `.dll`, dependiendo de si implementan ***aplicaciones*** o ***bibliotecas***, respectivamente.

En el ejemplo se declara una clase denominada `Stack` en un espacio de nombres llamado `Acme.Collections`:

[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]

El nombre completo de esta clase es `Acme.Collections.Stack`. La clase contiene varios miembros: un campo denominado `top`, dos métodos denominados `Push` y `Pop`, y una clase anidada denominada `Entry`. La clase `Entry` contiene además tres miembros: un campo denominado `next`, un campo denominado `data` y un constructor. Suponiendo que el código fuente del ejemplo se almacene en el archivo `acme.cs`, la línea de comandos

```console
csc /t:library acme.cs
```

compila el ejemplo como una biblioteca (código sin un punto de entrada `Main` y genera un ensamblado denominado `acme.dll`.

> [!IMPORTANT]
> Los ejemplos anteriores usan `csc` como el compilador C# de línea de comandos. Este compilador es un ejecutable de Windows. Para usar C# en otras plataformas, debe emplear las herramientas de .NET Core. El ecosistema .NET Core usa la CLI de `dotnet` para administrar las compilaciones de línea de comandos. Esto incluye la administración de dependencias y la llamada al compilador de C#. Consulte [este tutorial](../../core/tutorials/cli-create-console-app.md) para obtener una descripción completa de estas herramientas en las plataformas compatibles con .NET Core.

Los ensamblados contienen código ejecutable en forma de instrucciones de lenguaje intermedio (IL) e información simbólica en forma de metadatos. Antes de ejecutarlo, el código de IL de un ensamblado se convierte automáticamente en código específico del procesador mediante el compilador de Just in Time (JIT) de .NET Common Language Runtime.

Dado que un ensamblado es una unidad autodescriptiva de funcionalidad que contiene código y metadatos, no hay necesidad de directivas `#include` ni archivos de encabezado de C#. Los tipos y miembros públicos contenidos en un ensamblado determinado estarán disponibles en un programa de C# simplemente haciendo referencia a dicho ensamblado al compilar el programa. Por ejemplo, este programa usa la clase `Acme.Collections.Stack` desde el ensamblado `acme.dll`:

[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]

Si el programa está almacenado en el archivo `example.cs`, cuando se compila `example.cs`, se puede hacer referencia al ensamblado acme.dl mediante la opción /r del compilador:

```console
csc /r:acme.dll example.cs
```

Esto crea un ensamblado ejecutable denominado `example.exe`, que, cuando se ejecuta, produce el resultado:

```console
100
10
1
```

C# permite que el texto de origen de un programa se almacene en varios archivos de origen. Cuando se compila un programa de C# de varios archivos, todos los archivos de origen se procesan juntos y los archivos de origen pueden hacerse referencia mutuamente de forma libre; desde un punto de vista conceptual, es como si todos los archivos de origen estuvieran concatenados en un archivo de gran tamaño antes de ser procesados. En C# nunca se necesitan declaraciones adelantadas porque, excepto en contadas ocasiones, el orden de declaración es insignificante. C# no limita un archivo de origen a declarar solamente un tipo público ni precisa que el nombre del archivo de origen coincida con un tipo declarado en el archivo de origen.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](types-and-variables.md)
