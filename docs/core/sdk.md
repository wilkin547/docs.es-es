---
title: Información general sobre el SDK de .NET Core
description: Obtenga información sobre el SDK de .NET Core, que es un conjunto de bibliotecas y herramientas utilizadas para crear proyectos .NET Core.
ms.date: 07/31/2019
ms.technology: dotnet-cli
ms.openlocfilehash: f4c4982bacaf58c1b8c7db6c5319bd314e89b7ed
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566247"
---
# <a name="net-core-sdk-overview"></a>Información general sobre el SDK de .NET Core

El SDK de .NET Core es un conjunto de bibliotecas y herramientas que permiten a los desarrolladores crear aplicaciones y bibliotecas de .NET Core. Contiene los siguientes componentes que se usan para compilar y ejecutar aplicaciones:

- Herramientas de la CLI de .NET Core.
- Bibliotecas y runtime de .NET Core.
- [Controlador](tools/index.md#driver) `dotnet`.

## <a name="acquiring-the-net-core-sdk"></a>Adquisición del SDK de .NET Core

Del mismo modo que ocurre con todas las herramientas, lo primero que debe hacer es instalar las herramientas en su máquina. Según el escenario, puede instalar el SDK mediante uno de los métodos siguientes:

- Los instaladores nativos.
- El script de shell de instalación.

Los instaladores nativos están pensados principalmente para las máquinas de los desarrolladores. El SDK se distribuye mediante el mecanismo de instalación nativo de cada plataforma compatible, como los paquetes DEB en Ubuntu o los conjuntos de MSI en Windows. Estos instaladores instalan y configuran el entorno según sea necesario para que el usuario use el SDK inmediatamente después de la instalación. Sin embargo, también se necesitan privilegios administrativos en la máquina. Puede encontrar el SDK para instalar en la página de [descargas de .NET](https://dotnet.microsoft.com/download).

Por el contrario, los scripts de instalación no requieren privilegios administrativos, aunque tampoco instalan ningún requisito previo en el equipo; debe instalarlos todos manualmente el usuario. Los scripts están pensados principalmente para configurar servidores de compilación o cuando desee instalar las herramientas sin privilegios de administración (tenga en cuenta la salvedad con respecto a los requisitos previos que ya se mencionó). Puede encontrar más información en el artículo [referencia de scripts de dotnet-install](tools/dotnet-install-script.md). Si está interesado en cómo configurar el SDK en el servidor de compilación de CI, vea el artículo [Uso de .NET Core SDK y herramientas de integración continua (CI)](tools/using-ci-with-cli.md).

De forma predeterminada, el SDK se instala en paralelo (SxS), lo que significa que varias versiones de las herramientas de la CLI pueden coexistir en un único equipo en cualquier momento. La forma en que se detecta la versión al ejecutar los comandos de la CLI se explica más detalladamente en el artículo [Selección de la versión de .NET Core que se va a usar](versions/selection.md).

## <a name="see-also"></a>Vea también

- [CLI de .NET Core](tools/index.md)
- [Introducción a la creación de versiones de .NET Core](versions/index.md)
- [Cómo quitar los componentes .NET Core Runtime y SDK](versions/remove-runtime-sdk-versions.md)
- [Selección de la versión de .NET Core que se va a usar](versions/selection.md)
