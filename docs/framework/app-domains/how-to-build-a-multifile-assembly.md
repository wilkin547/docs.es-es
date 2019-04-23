---
title: Procedimiento para compilar un ensamblado de varios archivos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- Al.exe
- command-line compilers
- assembly manifest, multifile assemblies
- assemblies [.NET Framework], compiling
- Assembly Linker
- code modules
- multifile assemblies
ms.assetid: 261c5583-8a76-412d-bda7-9b8ee3b131e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bcc451903f7fbf7f82e2ed64834d26e605a0c069
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187803"
---
# <a name="how-to-build-a-multifile-assembly"></a>Procedimiento para compilar un ensamblado de varios archivos
En este artículo se explica cómo crear un ensamblado de múltiples archivos e incluye código que muestra cada paso del procedimiento.

> [!NOTE]
> El IDE de Visual Studio para C# y Visual Basic solo se pueden utilizar para crear ensamblados de un solo archivo. Si desea crear ensamblados de múltiples archivos, debe usar compiladores de la línea de comandos o Visual Studio con Visual C++.

### <a name="to-create-a-multifile-assembly"></a>Para crear un ensamblado de varios archivos

01. Compile en módulos de código todos los archivos que contengan espacios de nombres a los que hacen referencia otros módulos del ensamblado. La extensión predeterminada de los módulos de código es .netmodule.

    Por ejemplo, supongamos que el archivo `Stringer` tiene un espacio de nombres denominado `myStringer`, que incluye una clase denominada `Stringer`. La clase `Stringer` contiene un método denominado `StringerMethod` que escribe una única línea en la consola.

    [!code-cpp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#1)]
    [!code-csharp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#1)]
    [!code-vb[Conceptual.Assembly.Multifile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#1)]

    Use el comando siguiente para compilar este código:

    [!code-cpp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#2)]
    [!code-csharp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#2)]
    [!code-vb[Conceptual.Assembly.Multifile#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#2)]

    Si se especifica el parámetro *module* con la opción del compilador **/t:**, se indica que el archivo se debe compilar como un módulo y no como un ensamblado. El compilador produce un módulo denominado `Stringer.netmodule`, que se puede agregar a un ensamblado.

02. Compile los módulos restantes, usando las opciones de compilador necesarias para indicar los otros módulos a los que hace referencia el código. En este paso se usa la opción del compilador **/addmodule**.

    En el siguiente ejemplo, un módulo de código denominado `Client` tiene un método `Main` de punto de entrada que hace referencia a un método del módulo `Stringer.dll` creado en el paso 1.

    [!code-cpp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#3)]
    [!code-csharp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#3)]
    [!code-vb[Conceptual.Assembly.Multifile#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#3)]

    Use el comando siguiente para compilar este código:

    [!code-cpp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#4)]
    [!code-csharp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#4)]
    [!code-vb[Conceptual.Assembly.Multifile#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#4)]

    Especifique la opción **/t:module**, ya que este módulo se va a agregar a un ensamblado en un paso posterior. Especifique la opción **/addmodule**, ya que el código de `Client` hace referencia a un espacio de nombres creado por el código en `Stringer.netmodule`. El compilador produce un módulo denominado `Client.netmodule` que contiene una referencia a otro módulo, `Stringer.netmodule`.

    >[!NOTE]
    >Los compiladores de C# y Visual Basic son compatibles con la creación directa de ensamblados de múltiples archivos mediante las dos siguientes sintaxis distintas.
    >
    >- Dos compilaciones crean un ensamblado de dos archivos:
    >
    >    [!code-cpp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#5)]
    >    [!code-csharp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#5)]
    >    [!code-vb[Conceptual.Assembly.Multifile#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#5)]
    >
    >- Una compilación crea un ensamblado de dos archivos:
    >
    >    [!code-cpp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#6)]
    >    [!code-csharp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#6)]
    >    [!code-vb[Conceptual.Assembly.Multifile#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#6)]

03. Use la [herramienta Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) para crear el archivo de salida que contendrá el manifiesto del ensamblado. Este archivo contiene información de referencia de todos los módulos o recursos que forman parte del ensamblado.

    En el símbolo del sistema, escriba el siguiente comando:

    **al** \<*nombre del módulo*> \<*nombre del módulo*> … **/main:**\<*nombre del método*> **/out:**\<*nombre del archivo*> **/target:**\<*tipo de archivo de ensamblado*>

    En este comando, los argumentos de *nombre del módulo* especifican el nombre de todos los módulos que se van a incluir en el ensamblado. La opción **/main:** especifica el nombre del método que es el punto de entrada del ensamblado. La opción **/out:** especifica el nombre del archivo de salida, que contiene metadatos del ensamblado. La opción **/target:** especifica que el ensamblado es un archivo ejecutable de aplicación de consola (.exe), un archivo ejecutable de Windows (.win) o un archivo de biblioteca (.lib).

    En el siguiente ejemplo, Al.exe crea un ensamblado que es un ejecutable de aplicación de consola denominado `myAssembly.exe`. Esta aplicación está formada por dos módulos denominados `Client.netmodule` y `Stringer.netmodule`, y por el archivo ejecutable denominado `myAssembly.exe,`, que solo contiene metadatos del ensamblado. El punto de entrada del ensamblado es el método `Main` de la clase `MainClientApp`, que se encuentra en `Client.dll`.

    ```
    al Client.netmodule Stringer.netmodule /main:MainClientApp.Main /out:myAssembly.exe /target:exe
    ```

    Se puede usar el [Desensamblador de MSIL (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) para examinar el contenido de un ensamblado o determinar si un archivo es un ensamblado o un módulo.

## <a name="see-also"></a>Vea también

- [Creación de ensamblados](../../../docs/framework/app-domains/create-assemblies.md)
- [Cómo: Ver el contenido de un ensamblado](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Ensamblados de múltiples archivos](../../../docs/framework/app-domains/multifile-assemblies.md)
