---
title: Información general sobre el SDK de .NET
description: Obtenga información sobre el SDK de .NET, que es un conjunto de bibliotecas y herramientas utilizadas para crear proyectos de .NET.
ms.date: 07/31/2019
ms.technology: dotnet-cli
ms.openlocfilehash: 5236d4abec5dcbf950059dd906958158cfb592fe
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "99216146"
---
# <a name="net-sdk-overview"></a>Información general sobre el SDK de .NET

El SDK de .NET es un conjunto de bibliotecas y herramientas que permiten a los desarrolladores crear aplicaciones y bibliotecas de .NET. Contiene los siguientes componentes que se usan para compilar y ejecutar aplicaciones:

- La CLI de .NET.
- Entorno de ejecución y bibliotecas de .NET.
- El [controlador](tools/index.md#driver) `dotnet`.

## <a name="acquiring-the-net-sdk"></a>Adquisición del SDK de .NET

Del mismo modo que ocurre con todas las herramientas, lo primero que debe hacer es instalar las herramientas en su máquina. Según el escenario, puede instalar el SDK mediante uno de los métodos siguientes:

- Los instaladores nativos.
- El script de shell de instalación.

Los instaladores nativos están pensados principalmente para las máquinas de los desarrolladores. El SDK se distribuye mediante el mecanismo de instalación nativo de cada plataforma compatible, como los paquetes DEB en Ubuntu o los conjuntos de MSI en Windows. Estos instaladores instalan y configuran el entorno según sea necesario para que el usuario use el SDK inmediatamente después de la instalación. Sin embargo, también se necesitan privilegios administrativos en la máquina. Puede encontrar el SDK para instalar en la página de [descargas de .NET](https://dotnet.microsoft.com/download).

Por el contrario, los scripts de instalación no requieren privilegios administrativos, aunque tampoco instalan ningún requisito previo en el equipo; debe instalarlos todos manualmente el usuario. Los scripts están pensados principalmente para configurar servidores de compilación o cuando desee instalar las herramientas sin privilegios de administración (tenga en cuenta la salvedad con respecto a los requisitos previos que ya se mencionó). Puede encontrar más información en el artículo [referencia de scripts de dotnet-install](tools/dotnet-install-script.md). Si le interesa saber cómo configurar el SDK en el servidor de compilación de CI, vea el artículo [Uso del SDK y herramientas de .NET en la integración continua (CI)](tools/using-ci-with-cli.md).

De forma predeterminada, el SDK se instala en paralelo (SxS), lo que significa que varias versiones pueden coexistir en un único equipo en cualquier momento. La forma en la que se detecta la versión al ejecutar los comandos de la CLI se explica más detalladamente en el artículo [Selección de la versión de .NET Core que se va a usar](versions/selection.md).

## <a name="see-also"></a>Vea también

- [Información general sobre la CLI de .NET](tools/index.md)
- [Información general sobre el control de versiones de .NET](versions/index.md)
- [Procedimiento para quitar el entorno de ejecución y el SDK de .NET](install/remove-runtime-sdk-versions.md)
- [Selección de la versión de .NET Core que se va a usar](versions/selection.md)
