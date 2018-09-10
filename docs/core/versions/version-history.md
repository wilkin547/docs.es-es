---
title: Historial de versiones de .NET Core
description: Vea la escala de tiempo para las versiones del runtime de .NET Core, el SDK de .NET Core, el compilador de C# y el de VB.NET.
ms.date: 07/26/2018
ms.openlocfilehash: 90fd4ba57620a3a005f2148c0335a76a6fa54a30
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519070"
---
# <a name="net-core-version-history"></a>Historial de versiones de .NET Core

Los números de versión de .NET Core son un desafío porque el SDK de .NET Core y .NET Core Runtime se publican con ritmos diferentes. Las diferencias de ritmo significan que el equipo se vio forzado a realizar solo dos de las tres operaciones siguientes:

1. Publicar de forma independiente, y permitir específicamente que las herramientas, C# y VB avanzaran más rápido que .NET Core Runtime.
2. Mantener la alineación de los números de versión entre el SDK de .NET Core y .NET Core Runtime.
3. Usar el control de versiones semántico para el SDK de .NET Core y .NET Core Runtime.

En la versión 2.0.0 se forzó la alineación de las versiones y se continuó sin problemas hacia una versión. En diciembre de 2017 se publicó una versión de características del SDK de .NET Core, sin la versión correspondiente en .NET Core Runtime. El equipo eligió los objetivos 1 y 3, y se perdió la alineación entre .NET Core Runtime y el SDK. Antes de .NET Core Runtime 2.1 se publicaron varias versiones del SDK de .NET Core 2.1.x. Como el SDK no es compatible con versiones futuras, estas versiones 2.1.x del SDK no podían tener como destino .NET Core Runtime 2.1. Como respuesta a la evidente confusión, el equipo cambió a los objetivos 1 y 2, y abandonó el control de versiones semántico como se describe en [Control de versiones de .NET Core](index.md#versioning-details).

Debido a la sincronización de la decisión de abandonar el control de versiones semántico, hubo versiones transitorias en los intervalos de número de versión 2.1.10x y 2.1.20x que tampoco pueden tener como destino .NET Core Runtime 2.1.

Los dos primeros dígitos de los números de versión se vuelven a alinear con la versión 2.1.0 de .NET Core Runtime y la versión 2.1.300 del SDK de .NET Core.

En la [página de descargas de .NET Core](https://www.microsoft.com/net/download/dotnet-core/current) puede encontrar información detallada sobre las versiones de componentes individuales, incluidas las del marco de trabajo y el compilador de lenguaje. Para obtener información detallada sobre las versiones anteriores, seleccione la versión solicitada en la [página de archivos de descarga de .NET Core](https://www.microsoft.com/net/download/archives). En el artículo que describe la [política de soporte técnico de .NET](https://www.microsoft.com/net/Support/Policy) oficial puede encontrar información de soporte técnico detallada.