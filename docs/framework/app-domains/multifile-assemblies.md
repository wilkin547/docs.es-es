---
title: Ensamblados de múltiples archivos
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- command-line compilers
- assembly manifest, multifile assemblies
- code modules
- multifile assemblies
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
ms.openlocfilehash: 2a70e45d50763cf99c55cf08600c3c816b4043b7
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644215"
---
# <a name="multifile-assemblies"></a>Ensamblados de múltiples archivos

Puede crear ensamblados de varios archivos que tengan como destino .NET Framework mediante compiladores de línea de comandos o Visual Studio con Visual C++. Un archivo del ensamblado debe contener el manifiesto del ensamblado. Los ensamblados que inicien una aplicación también deben contener un punto de entrada, como un método `Main` o `WinMain`.

Por ejemplo, supongamos que tiene una aplicación que contiene dos módulos de código, *Client.cs* y *Stringer.cs*. *Stringer.cs* crea el espacio de nombres `myStringer` al que hace referencia el código de *Client.cs*. *Client.cs* contiene el método `Main`, que es el punto de entrada de la aplicación. En este ejemplo, se compilan los dos módulos de código y, después, se crea un tercer archivo que contiene el manifiesto del ensamblado, que inicia la aplicación. El manifiesto del ensamblado hace referencia a los módulos *Client* y *Stringer*.

> [!NOTE]
> Los ensamblados de varios archivos pueden tener un único punto de entrada, incluso si el ensamblado tiene varios módulos de código.

Hay varias razones por las que le puede interesar crear un ensamblado de varios archivos:

- Para combinar módulos escritos en lenguajes diferentes. Esta es la razón más común para crear un ensamblado de varios archivos.

- Para optimizar la descarga de una aplicación al colocar los tipos menos usados en un módulo que solo se descarga cuando es necesario.

    > [!NOTE]
    > Si va a crear aplicaciones que se descargarán mediante la etiqueta `<object>` con Microsoft Internet Explorer, es importante que cree ensamblados de varios archivos. En este escenario, debe crear un archivo independiente de los módulos de código que solo contenga el manifiesto del ensamblado. Internet Explorer descarga primero el manifiesto del ensamblado y, después, crea subprocesos de trabajo para descargar los módulos o ensamblados adicionales necesarios. Mientras se descarga el archivo que contiene el manifiesto del ensamblado, Internet Explorer no responde a la entrada del usuario. Cuanto menor sea el archivo que contiene el manifiesto del ensamblado, menos tiempo estará sin responder Internet Explorer.

- Para combinar módulos de código escritos por varios desarrolladores. Aunque cada desarrollador puede compilar cada módulo de código en un ensamblado, esto puede hacer que se expongan públicamente algunos tipos que no se exponen cuando todos los módulos se colocan en un ensamblado de varios archivos.

Una vez creado el ensamblado, puede firmar el archivo que contiene el manifiesto del ensamblado (y, por tanto, el ensamblado), o bien puede asignarle al archivo y al ensamblado un nombre seguro y colocarlo en la caché global de ensamblados.

## <a name="see-also"></a>Vea también

- [Cómo: Compilar un ensamblado de varios archivos](build-multifile-assembly.md)
- [Programación con ensamblados](../../standard/assembly/index.md)
