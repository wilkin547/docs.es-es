---
title: Facilitar la depuración de .NET de una imagen
description: Obtenga información sobre cómo configurar una imagen ejecutable para una depuración más sencilla mediante el IDE se activa y las opciones de línea de comandos.
ms.date: 08/30/2018
helpviewer_keywords:
- images [.NET Framework], debugging
- executable image for debugging
- debugging [.NET Framework], executable images for
ms.assetid: 7d90ea7a-150f-4f97-98a7-f9c26541b9a3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f25eaaa17d4c4bd2e9522591bb0fd66445cdb6f
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44076854"
---
# <a name="making-an-image-easier-to-debug-in-net"></a>Facilitar la depuración de .NET de una imagen

Al compilar código no administrado, puede configurar una imagen ejecutable para depurarla si establece algunos modificadores IDE u opciones de línea de comandos. Por ejemplo, puede usar la opción de línea de comandos /**Zi** en Visual C++ para solicitarle que emita archivos de símbolo de depuración (con la extensión de archivo .pdb). De forma similar, la opción de línea de comandos /**Od** indica al compilador que deshabilite la optimización. El código resultante se ejecuta más lentamente, pero es más fácil de depurar, esto será necesario.

Cuando se compila en .NET Framework código administrado, los compiladores como Visual C++, Visual Basic y C# compilan el programa fuente en lenguaje intermedio de Microsoft (MSIL). MSIL es, a continuación, compila con JIT, justo antes de ejecutarse, en código máquina nativo. Al igual que con el código no administrado, puede configurar una imagen ejecutable para depurarla si establece algunos modificadores IDE u opciones de línea de comandos. También puede configurar la compilación JIT para la depuración de la misma manera.

Esta configuración JIT tiene dos aspectos:

- Puede solicitar el compilador JIT para generar información de seguimiento. Esto permite que el depurador empareje una cadena de MSIL con su equivalente de código administrado y realizar un seguimiento de dónde se almacenan las variables locales y los argumentos de función. A partir de la versión 2.0 de .NET Framework, el compilador JIT genera siempre información de seguimiento, así que no hay ninguna necesidad de solicitarla.

- Puede solicitar al compilador JIT que no optimice el código máquina resultante.

Normalmente, el compilador que genera el MSIL establece estas opciones del compilador JIT la forma adecuada, en función de los modificadores IDE u opciones de línea de comandos que especifique, por ejemplo, /**Od**.

En algunos casos, puede cambiar el comportamiento del compilador JIT de forma que el código máquina que genera sea más fácil de depurar. Por ejemplo, cuando desee generar información de seguimiento JIT para una compilación comercial o la optimización de controles. Puede hacer esto con un archivo de inicialización (.ini).

Por ejemplo, si el ensamblado que desea depurar se llama a *MyApp.exe*, a continuación, puede crear un archivo de texto denominado *MyApp.ini*, en la misma carpeta que *MyApp.exe*, que contiene estas tres líneas:

```txt
[.NET Framework Debugging Control]
GenerateTrackingInfo=1
AllowOptimize=0
```

Puede establecer el valor de cada opción en 0 o 1. Cualquier opción que no se encuentre presente tiene el valor predeterminado 0. Si se establece el valor de `GenerateTrackingInfo` en 1 y el valor de `AllowOptimize` en 0, se obtiene la depuración más fácil.

A partir de la versión 2.0 de .NET Framework, el compilador JIT genera siempre información de seguimiento, independientemente del valor de `GenerateTrackingInfo`; sin embargo, el `AllowOptimize` valor sigue teniendo efecto. Al usar [Ngen.exe (generador de imágenes nativo)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) para precompilar la imagen nativa sin la optimización, el archivo .ini debe estar presente en la carpeta de destino con `AllowOptimize=0` cuando se ejecuta Ngen.exe. Si ha precompilado un ensamblado sin la optimización, debe quitar el código precompilado con NGen.exe **/ uninstall** opción antes de volver a ejecutar Ngen.exe para precompilar el código como optimizado. Si el archivo .ini no está presente en la carpeta, de forma predeterminada Ngen.exe precompila el código como optimizado.

<xref:System.Diagnostics.DebuggableAttribute?displayProperty=nameWithType> controla los valores de un ensamblado. **DebuggableAttribute** incluye dos campos que controlan si el compilador JIT debe optimizar y/o generar información de seguimiento. A partir de la versión 2.0 de .NET Framework, el compilador JIT genera siempre información de seguimiento.

Para una compilación comercial, los compiladores no establecen ningún **DebuggableAttribute**. De forma predeterminada, el compilador JIT genera el mayor rendimiento, más difícil de depurar el código máquina. Si se habilita el seguimiento JIT, disminuye un poco el rendimiento; si se deshabilita, disminuye mucho.

**DebuggableAttribute** se aplica a un ensamblado completo cada vez, no a módulos individuales dentro del ensamblado. Por tanto, las herramientas de desarrollo deben asociar los atributos personalizados al token de metadatos del ensamblado, si ya se ha creado un ensamblado, o a la clase denominada **System.Runtime.CompilerServices.AssemblyAttributesGoHere**. La herramienta ALink, a continuación, promociona estos **DebuggableAttribute** atributos desde cada módulo al ensamblado del que forman parte de. Si hay un conflicto, se produce un error en la operación ALink.

> [!NOTE]
> En el caso de la versión 1.0 de .NET Framework, el compilador de Microsoft Visual C++ agrega el atributo **DebuggableAttribute** cuando se especifican las opciones del compilador **/clr** y **/Zi**. En el caso de la versión 1.1 de .NET Framework, debe agregar manualmente en el código el atributo **DebugabbleAttribute** o usar la opción del vinculador **/ASSEMBLYDEBUG**.

## <a name="see-also"></a>Vea también

- [Depurar, trazar y generar perfiles](../../../docs/framework/debug-trace-profile/index.md)
- [Habilitar la depuración de adjuntos JIT](../../../docs/framework/debug-trace-profile/enabling-jit-attach-debugging.md)
- [Habilitar la generación de perfiles](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s5ec0es1(v=vs.100))
