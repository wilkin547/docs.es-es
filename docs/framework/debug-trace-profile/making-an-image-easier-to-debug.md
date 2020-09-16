---
title: Facilitar la depuración de una imagen en .NET
description: Aprenda a configurar una imagen ejecutable para facilitar la depuración mediante conmutadores IDE y opciones de línea de comandos.
ms.date: 08/30/2018
helpviewer_keywords:
- images [.NET Framework], debugging
- executable image for debugging
- debugging [.NET Framework], executable images for
ms.assetid: 7d90ea7a-150f-4f97-98a7-f9c26541b9a3
ms.openlocfilehash: a3305dc864e7852c2336009503732a51868410d2
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558516"
---
# <a name="making-an-image-easier-to-debug-in-net"></a>Facilitar la depuración de una imagen en .NET

Al compilar código no administrado, puede configurar una imagen ejecutable para depurarla si establece algunos modificadores IDE u opciones de línea de comandos. Por ejemplo, puede usar la opción de línea de comandos /**Zi** en Visual C++ para solicitarle que emita archivos de símbolo de depuración (con la extensión de archivo .pdb). De forma similar, la opción de línea de comandos /**Od** indica al compilador que deshabilite la optimización. El código resultante se ejecuta más lentamente, pero es más fácil de depurar, en caso de que sea necesario.

Al compilar .NET Framework código administrado, los compiladores como Visual C++, Visual Basic y C# compilan su programa de origen en lenguaje intermedio de Microsoft (MSIL). Después, MSIL se compila con JIT, justo antes de la ejecución, en código máquina nativo. Al igual que con el código no administrado, puede configurar una imagen ejecutable para depurarla si establece algunos modificadores IDE u opciones de línea de comandos. También puede configurar la compilación JIT para la depuración de la misma manera.

Esta configuración JIT tiene dos aspectos:

- Puede solicitar al compilador JIT que genere información de seguimiento. Esto permite que el depurador empareje una cadena de MSIL con su equivalente de código administrado y realizar un seguimiento de dónde se almacenan las variables locales y los argumentos de función. A partir de la versión 2,0 de .NET Framework, el compilador JIT genera siempre información de seguimiento, por lo que no es necesario solicitarla.

- Puede solicitar al compilador JIT que no optimice el código de equipo resultante.

Normalmente, el compilador que genera el MSIL establece estas opciones del compilador JIT correctamente, en función de los modificadores IDE o las opciones de la línea de comandos que se especifiquen, por ejemplo,/**OD**.

En algunos casos, puede cambiar el comportamiento del compilador JIT de forma que el código máquina que genera sea más fácil de depurar. Por ejemplo, cuando desee generar información de seguimiento JIT para una compilación comercial o la optimización de controles. Puede hacer esto con un archivo de inicialización (.ini).

Por ejemplo, si el ensamblado que desea depurar se denomina *MyApp.exe*, puede crear un archivo de texto denominado *MyApp.ini*en la misma carpeta que *MyApp.exe*, que contiene estas tres líneas:

```ini
[.NET Framework Debugging Control]
GenerateTrackingInfo=1
AllowOptimize=0
```

Puede establecer el valor de cada opción en 0 o 1. Cualquier opción que no se encuentre presente tiene el valor predeterminado 0. Si se establece el valor de `GenerateTrackingInfo` en 1 y el valor de `AllowOptimize` en 0, se obtiene la depuración más fácil.

A partir de la .NET Framework versión 2,0, el compilador JIT genera siempre información de seguimiento independientemente del valor de `GenerateTrackingInfo` ; sin embargo, el `AllowOptimize` valor todavía tiene un efecto. Al usar [Ngen.exe (generador de imágenes nativo)](../tools/ngen-exe-native-image-generator.md) para precompilar la imagen nativa sin la optimización, el archivo .ini debe estar presente en la carpeta de destino con `AllowOptimize=0` cuando se ejecuta Ngen.exe. Si ha precompilado un ensamblado sin la optimización, debe quitar el código precompilado con NGen.exe opción **/Uninstall** antes de volver a ejecutar Ngen.exe para precompilar el código como optimizado. Si el archivo. ini no está presente en la carpeta, de forma predeterminada Ngen.exe precompila el código como optimizado.

<xref:System.Diagnostics.DebuggableAttribute?displayProperty=nameWithType> controla los valores de un ensamblado. **DebuggableAttribute** incluye dos campos que controlan si el compilador JIT debe optimizar y/o generar información de seguimiento. A partir de la versión 2,0 de .NET Framework, el compilador JIT genera siempre información de seguimiento.

En una compilación comercial, los compiladores no establecen ningún **atributo DebuggableAttribute**. De forma predeterminada, el compilador JIT genera el mayor rendimiento, es más difícil de depurar código máquina. Si se habilita el seguimiento JIT, disminuye un poco el rendimiento; si se deshabilita, disminuye mucho.

**DebuggableAttribute** se aplica a un ensamblado completo cada vez, no a módulos individuales dentro del ensamblado. Por tanto, las herramientas de desarrollo deben asociar los atributos personalizados al token de metadatos del ensamblado, si ya se ha creado un ensamblado, o a la clase denominada **System.Runtime.CompilerServices.AssemblyAttributesGoHere**. A continuación, la herramienta ALink promueve estos atributos **DebuggableAttribute** desde cada módulo al ensamblado del que forman parte. Si hay un conflicto, se produce un error en la operación ALink.

> [!NOTE]
> En el caso de la versión 1.0 de .NET Framework, el compilador de Microsoft Visual C++ agrega el atributo **DebuggableAttribute** cuando se especifican las opciones del compilador **/clr** y **/Zi**. En la versión 1,1 del .NET Framework, debe agregar el **atributo DebuggableAttribute** manualmente en el código o usar la opción **/AssemblyDebug** del vinculador.

## <a name="see-also"></a>Vea también

- [Depurar, trazar y generar perfiles](index.md)
- [Habilitar la depuración de adjuntos JIT](enabling-jit-attach-debugging.md)
- [Habilitar la generación de perfiles](/previous-versions/dotnet/netframework-4.0/s5ec0es1(v=vs.100))
