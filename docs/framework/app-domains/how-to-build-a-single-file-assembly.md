---
title: Procedimiento para compilar un ensamblado de un solo archivo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a73b2d8948c9a046fd77c02f1bcc87f5738105d9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304004"
---
# <a name="how-to-build-a-single-file-assembly"></a>Procedimiento para compilar un ensamblado de un solo archivo

Un ensamblado de único archivo, que es el tipo de ensamblado más sencillo, contiene información y la implementación del tipo, así como el [manifiesto del ensamblado](../../../docs/framework/app-domains/assembly-manifest.md). Puede usar los compiladores de la línea de comandos o Visual Studio para crear un ensamblado de único archivo. De forma predeterminada, el compilador crea un archivo de ensamblado con la extensión .exe.

> [!NOTE]
> Visual Studio para C# y Visual Basic solo se pueden usar para crear ensamblados de único archivo. Si desea crear ensamblados de múltiples archivos, debe usar compiladores de la línea de comandos o Visual C++.

En los procedimientos siguientes se muestra cómo crear ensamblados de único archivo mediante los compiladores de la línea de comandos.

## <a name="to-create-an-assembly-with-an-exe-extension"></a>Para crear un ensamblado con una extensión .exe

1. En el símbolo del sistema, escriba el siguiente comando:

     \<*comando del compilador*> \<*nombre del módulo*>

     En este comando, *comando de compilador* es el comando del compilador del lenguaje usado en el módulo del código, mientras que *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.

 En el ejemplo siguiente se crea un ensamblado llamado `myCode.exe` desde un módulo de código llamado `myCode`.

```console
csc myCode.cs
```

```console
vbc myCode.vb
```

### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a>Para crear un ensamblado con la extensión .exe y especificar el nombre de archivo de salida

1. En el símbolo del sistema, escriba el siguiente comando:

     \<*comando del compilador*> **/out:**\<*nombre del archivo*> \<*nombre del módulo*>

     En este comando, *comando del compilador* es el comando del compilador del lenguaje usado en el módulo del código, *nombre del archivo* es el nombre del archivo de salida y *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.

 En el ejemplo siguiente se crea un ensamblado llamado `myAssembly.exe` desde un módulo de código llamado `myCode`.

```console
csc -out:myAssembly.exe myCode.cs
```

```console
vbc -out:myAssembly.exe myCode.vb
```

## <a name="creating-library-assemblies"></a>Crear ensamblados de biblioteca
 Los ensamblados de biblioteca se parecen a las bibliotecas de clases. Contiene tipos a los que harán referencia otros ensamblados, pero no tiene ningún punto de entrada para comenzar la ejecución.

### <a name="to-create-a-library-assembly"></a>Para crear un ensamblado de biblioteca

1. En el símbolo del sistema, escriba el siguiente comando:

     \<*comando del compilador*> **-t:library** \<*nombre del módulo*>

     En este comando, *comando de compilador* es el comando del compilador del lenguaje usado en el módulo del código, mientras que *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado. También puede usar otras opciones del compilador, como la opción **-out:**.

 En el ejemplo siguiente se crea un ensamblado de biblioteca llamado `myCodeAssembly.dll` desde un módulo de código llamado `myCode`.

```console
csc -out:myCodeLibrary.dll -t:library myCode.cs
```

```console
vbc -out:myCodeLibrary.dll -t:library myCode.vb
```

## <a name="see-also"></a>Vea también

- [Creación de ensamblados](../../../docs/framework/app-domains/create-assemblies.md)
- [Ensamblados de múltiples archivos](../../../docs/framework/app-domains/multifile-assemblies.md)
- [Cómo: Compilar un ensamblado de varios archivos](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)