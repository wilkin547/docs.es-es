---
title: ¿Qué es el código administrado?
description: Obtenga información sobre cómo el código administrado es código cuya ejecución la administra un tiempo de ejecución, Common Language Runtime (CLR).
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: 20bb7ea8-192e-4a96-8ef3-e10e1950fd3d
ms.openlocfilehash: 950dd5c32663b0716247c2a31a2f729fcf85f97b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163108"
---
# <a name="what-is-managed-code"></a>¿Qué es el "código administrado"?

Al trabajar con .NET, a menudo se encontrará con el término "código administrado". En este documento se explica el significado de este término y otra información relacionada.

Dicho en pocas palabras, el código administrado es simplemente eso: código cuya ejecución está administrada mediante un tiempo de ejecución. En este caso, el tiempo de ejecución en cuestión se denomina **Common Language Runtime** o CLR, con independencia de la implementación (por ejemplo, [Mono](https://www.mono-project.com/), .NET Framework o .NET Core/.NET 5+). CLR se encarga de tomar el código administrado, compilarlo en código máquina y, después, ejecutarlo. Además de eso, el tiempo de ejecución proporciona varios servicios importantes, como la administración de memoria automática, los límites de seguridad, la seguridad de los tipos, etc.

Compare esto con la forma en que ejecutaría un programa escrito en C/C++, también denominado "código no administrado". En un entorno no administrado, el programador se encarga prácticamente de todo. El programa real es, básicamente, un archivo binario que el sistema operativo (SO) carga en la memoria e inicia. Todo lo demás, desde la administración de memoria hasta las consideraciones de seguridad, son responsabilidad del programador.

El código administrado se escribe en uno de los lenguajes de alto nivel que se pueden ejecutar en la plataforma .NET, como C#, Visual Basic, F# y otros. Cuando se compila código escrito en estos lenguajes con su compilador correspondiente, no se obtiene código máquina. Se obtiene código de **lenguaje intermedio**, que más adelante el tiempo de ejecución compila y ejecuta. C++ es la única excepción a esta regla, ya que también puede generar archivos binarios nativos y no administrados que se ejecutan en Windows.

## <a name="intermediate-language--execution"></a>Lenguaje intermedio y ejecución

¿Qué es el "lenguaje intermedio" (o IL)? Es un producto de la compilación de código escrito en lenguajes .NET de alto nivel. Una vez compilado el código escrito en uno de estos idiomas, se obtiene un archivo binario integrado por IL. Es importante tener en cuenta que el lenguaje intermedio es independiente de cualquier lenguaje específico que se ejecute sobre el tiempo de ejecución; incluso hay una especificación independiente para él, que puede leer si le interesa.

Una vez que haya producido IL a partir del código de alto nivel, lo más probable es que quiera ejecutarlo. Aquí es donde CLR se encarga del proceso e inicia la compilación **Just-In-Time** o **JIT** del código IL en código máquina, que se puede ejecutar en una CPU. De esta manera, CLR sabe exactamente qué hace el código y puede _administrarlo_ con eficacia.

El lenguaje intermedio a veces también se denomina Lenguaje intermedio común (CIL) o Lenguaje intermedio de Microsoft (MSIL).

## <a name="unmanaged-code-interoperability"></a>Interoperabilidad con código no administrado

Por supuesto, CLR permite traspasar los límites entre el entorno administrado y no administrado, y hay una gran cantidad de código que lo hace, incluso en [bibliotecas de clases base](framework-libraries.md). Esto se denomina **interoperabilidad** o simplemente **interop** para abreviar. Estas disposiciones permitirían, por ejemplo, encapsular una biblioteca no administrada y llamarla. Pero es importante tener en cuenta que, una vez hecho esto, cuando el código pasa los límites del tiempo de ejecución, la administración real de la ejecución vuelve a depender del código no administrado y, por tanto, se enfrenta a las mismas restricciones.

De modo parecido, C# es un lenguaje que permite usar construcciones no administradas, como punteros, directamente en el código mediante el uso de lo que se conoce como **contexto no seguro**, que designa un fragmento de código cuya ejecución no se administrada mediante CLR.

## <a name="more-resources"></a>Más recursos

* [Información general acerca de .NET Framework](../framework/get-started/overview.md)
* [Código no seguro y punteros](../csharp/programming-guide/unsafe-code-pointers/index.md)
* [Interoperabilidad nativa](./native-interop/index.md)
