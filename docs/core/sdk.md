---
title: Información general sobre el SDK de .NET Core
description: Obtenga información sobre el SDK de .NET Core, que es un conjunto de bibliotecas y herramientas utilizadas para crear proyectos .NET Core.
author: blackdwarf
ms.author: mairaw
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.openlocfilehash: 5fc04c3ef5a1502251a9caf0b6a5f5809faad5b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33210907"
---
# <a name="net-core-sdk-overview"></a>Información general sobre el SDK de .NET Core 

## <a name="introduction"></a>Introducción
El kit de desarrollo de software (SDK) de .NET Core es un conjunto de bibliotecas y herramientas que permiten a los desarrolladores crear aplicaciones y bibliotecas de .NET Core. Este es el paquete que es más probable que adquieran los desarrolladores. 

Incluye los componentes siguientes:

1. Las herramientas de línea de comandos de .NET Core que se usan para compilar aplicaciones.
2. .NET Core (bibliotecas y entorno de ejecución) que permiten compilar y ejecutar las aplicaciones.
3. El controlador `dotnet` para ejecutar los [comandos de la CLI](tools/index.md), así como también ejecutar aplicaciones.


## <a name="acquiring-the-net-core-sdk"></a>Adquisición del SDK de .NET Core
Del mismo modo que ocurre con todas las herramientas, lo primero que debe hacer es instalar las herramientas en su máquina. Según el escenario, puede usar los instaladores nativos para instalar el SDK, o bien puede usar el script de shell de instalación.

Los instaladores nativos están pensados principalmente para las máquinas de los desarrolladores. El SDK se distribuye mediante el uso del mecanismo de instalación nativo de cada plataforma compatible, por ejemplo, los paquetes DEB en Ubuntu o los conjuntos de MSI en Windows. Estos instaladores instalarán y configurarán el entorno según sea necesario para que el usuario use el SDK inmediatamente después de la instalación. Sin embargo, también se necesitan privilegios administrativos en la máquina. Puede ver las instrucciones de instalación en la [Guía de instalación de .NET Core](https://aka.ms/dotnetcoregs).

Por otro lado, los scripts de instalación no requieren privilegios administrativos. Sin embargo, tampoco instalan ningún requisito previo en la máquina; debe instalarlos todos manualmente. Los scripts están pensados principalmente para configurar servidores de compilación o cuando desee instalar las herramientas sin privilegios de administración (tenga en cuenta la salvedad con respecto a los requisitos previos que ya se mencionó). Puede encontrar más información en el [tema de referencia sobre los scripts de instalación](tools/dotnet-install-script.md). Si le interesa saber cómo configurar el SDK en el servidor de compilación de integración continua, consulte el documento sobre el [SDK con servidores de integración continua](tools/using-ci-with-cli.md). 

De forma predeterminada, el SDK se instalará "en paralelo". Esto significa que pueden coexistir varias versiones de las herramientas de la CLI en un momento dado en una sola máquina. El uso de la versión correcta se explica en detalle en la [sección de controladores](tools/index.md#driver) del tema sobre las herramientas de línea de comandos de .NET Core.
