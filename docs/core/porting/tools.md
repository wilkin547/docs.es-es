---
title: Herramientas para la portabilidad a .NET Core
description: Más información sobre algunas de las herramientas que puede usar para realizar la portabilidad a .NET Core
author: cartermp
ms.date: 05/03/2020
ms.openlocfilehash: b8678ec72fe5d910d5f8cff4768106e7496f9276
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406133"
---
# <a name="tools-to-help-with-porting-to-net-core"></a>Herramientas útiles para la portabilidad a .NET Core

Las herramientas enumeradas en este artículo pueden ser útiles cuando realice la portabilidad:

- [Analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md): una cadena de herramientas que puede generar un informe de portabilidad del código entre .NET Framework y .NET Core:
  - Como una [herramienta de línea de comandos](https://github.com/Microsoft/dotnet-apiport/releases)
  - Como una [extensión de Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [Analizador de compatibilidad de plataformas](../../standard/analyzers/platform-compat-analyzer.md): analizador de Roslyn que informa a los desarrolladores cuando usan API específicas de la plataforma desde sitios de llamada en los que es posible que la API no esté disponible.
- [Analizador de API de .NET](../../standard/analyzers/api-analyzer.md): un analizador de Roslyn que puede ayudar a detectar problemas de compatibilidad de plataformas en aplicaciones y bibliotecas multiplataforma.
- [try-Convert](https://www.nuget.org/packages/try-convert/): herramienta global de .NET Core que puede convertir un proyecto o una solución completa en el SDK de .NET, así como trasladar aplicaciones de escritorio a .NET Core. No se recomienda si tiene establecida una compilación más complicada (como tareas personalizadas, destinos o importaciones); rechaza muchos tipos de proyecto que no son compatibles con .NET Core.
