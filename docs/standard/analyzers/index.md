---
title: Los analizadores basados en Roslyn - .NET
description: Obtenga información sobre los analizadores basados en Roslyn que detectan problemas y sugieren soluciones para esos problemas.
author: billwagner
ms.author: wiwagn
ms.date: 01/24/2018
ms.technology: dotnet-standard
ms.openlocfilehash: 436cfb3904f0891f8c18bb5890563a13d65e2d1c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "62003059"
---
# <a name="the-roslyn-based-analyzers"></a>Los analizadores basados en Roslyn

Los analizadores basados en Roslyn usan el SDK de .NET Compiler (API de Roslyn) para analizar el código fuente de su proyecto a fin de detectar problemas y sugerir soluciones. Los diferentes analizadores buscan distintas clases de problemas, que van desde prácticas susceptibles de generar errores a inquietudes de seguridad relativas a la compatibilidad de la API.

Los analizadores basados en Roslyn trabajan de forma interactiva y durante las compilaciones. El analizador proporciona diversas instrucciones tanto en Visual Studio como en las compilaciones de líneas de comandos.

Mientras edita código en Visual Studio, los analizadores se ejecutan al realizar cambios, detectando posibles problemas tan pronto como cree código que desencadene preocupaciones. Algunos problemas se resaltan con subrayados ondulados. Visual Studio muestra una bombilla y, al hacer clic en ella, el analizador sugerirá posibles soluciones a ese problema. Al crear el proyecto, ya sea en Visual Studio o desde la línea de comandos, se analiza todo el código fuente y el analizador proporciona una lista completa de posibles problemas. En la siguiente ilustración se muestra un ejemplo.

![problemas notificados por el analizador de marco](./media/framework-analyzers-2.png)

Los analizadores basados en Roslyn notifican posibles problemas como errores, advertencias o información en función de la gravedad del problema.

Puede instalar los analizadores basados en Roslyn como paquetes NuGet en su proyecto. Los analizadores configurados y la configuración de cada uno de ellos se restauran y se ejecutan en la máquina de ese proyecto de los desarrolladores.

> [!NOTE]
> La experiencia de usuario en el caso de los analizadores basados en Roslyn es distinta de la de bibliotecas de análisis de código como las versiones anteriores de FxCop y las herramientas de análisis de seguridad.  No es necesario que ejecute de forma explícita los analizadores basados en Roslyn. Tampoco hace falta usar los elementos de menú "Ejecutar análisis de código" en el menú "Analizar" de Visual Studio. Los analizadores basados en Roslyn se ejecutan de forma asincrónica mientras trabaja.

## <a name="more-information-on-specific-analyzers"></a>Más información sobre analizadores específicos

Los siguientes analizadores se tratan en esta sección:

* [Analizador de API](api-analyzer.md): este analizador examina su código en busca de posibles riesgos de compatibilidad o usos de API en desuso.
* [Analizador de marco](framework-analyzer.md): este analizador examina su código para garantizar que siga las instrucciones de las aplicaciones de .NET Framework. Estas reglas incluyen varias recomendaciones basadas en seguridad.
* [Analizador de portabilidad de .NET](portability-analyzer.md): este analizador examina el código para ver cuánto trabajo es necesario para que la aplicación sea compatible con otras implementaciones y perfiles .NET, como .NET Core, .NET Standard, UWP y Xamarin para iOS, Android y Mac.
