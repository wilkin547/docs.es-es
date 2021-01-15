---
title: Introducción a Azure y .NET
description: Obtenga información sobre los conceptos básicos que necesita saber acerca de Azure y .NET.
ms.date: 06/20/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: b5766012b77da88ae9a696939b6e498ebc421522
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025047"
---
# <a name="introduction-to-azure-and-net"></a>Introducción a Azure y .NET

## <a name="what-is-azure"></a>¿Qué es Azure?

Azure es una plataforma en la nube diseñada para simplificar el proceso de creación de aplicaciones modernas.  Tanto si decide hospedar completamente las aplicaciones en Azure como ampliar las aplicaciones locales con los servicios de Azure, Azure le ayuda a crear aplicaciones escalables, confiables y fáciles de mantener.  Con una amplia compatibilidad con las herramientas que ya usa, como Visual Studio y Visual Studio Code, y una biblioteca completa de SDK, Azure está diseñado para que usted, el desarrollador de .NET, sea productivo desde el principio.

## <a name="application-development-scenarios-on-azure"></a>Escenarios de desarrollo de aplicaciones en Azure

Puede incorporar Azure en su aplicación de diferentes formas, en función de sus necesidades.

- **Hospedaje de aplicaciones en Azure:** Azure puede hospedar toda la pila de aplicaciones, desde aplicaciones web y API, a bases de datos y servicios de almacenamiento. Azure admite una gran variedad de modelos de hospedaje, desde servicios completamente administrados hasta contenedores y máquinas virtuales. Al usar los servicios de Azure totalmente administrados, las aplicaciones pueden beneficiarse de las ventajas de la escalabilidad, la alta disponibilidad y la seguridad integradas en Azure.

- **Consumo de servicios en la nube de aplicaciones:** las aplicaciones existentes pueden incorporar servicios de Azure para ampliar sus capacidades.  Esto podría incluir la incorporación de la funcionalidad de búsqueda de texto completo con [Azure Cognitive Search](/azure/search/search-what-is-azure-search), el almacenamiento seguro de secretos de aplicación en [Azure Key Vault](/azure/key-vault/), o la incorporación de funcionalidades de visión, voz y lenguaje con [Azure Cognitive Services](/azure/cognitive-services/).  Estos servicios están totalmente administrados por Azure y se pueden agregar fácilmente a la aplicación sin cambiar el modelo de implementación ni la arquitectura de la aplicación actual.

- **Arquitecturas sin servidor modernas:** Azure Functions simplifica la creación de soluciones para administrar flujos de trabajo orientados a eventos, ya sea responder a solicitudes HTTP, controlar cargas de archivos en almacenamiento de blobs o procesar eventos en una cola.  Solo escriba el código necesario para controlar el evento sin preocuparse por los servidores o el código de la plataforma.  Además, puede beneficiarse de los más de 250 conectores a otros servicios de Azure y de terceros para abordar los problemas de integración más difíciles.

## <a name="access-azure-services-from-net-applications"></a>Acceso a los servicios de Azure desde aplicaciones .NET

Tanto si la aplicación está hospedada en Azure como en un entorno local, el acceso a la mayoría de los servicios de Azure se proporciona a través del **SDK de Azure para .NET**.  El SDK de Azure para .NET se proporciona como una serie de paquetes NuGet y se puede usar en aplicaciones de .NET Core (2.1 y versiones posteriores) y .NET Framework (4.6.1 y versiones posteriores). El SDK de Azure para .NET hace que la incorporación de servicios de Azure a la aplicación sea algo tan sencillo como instalar el paquete NuGet correcto, crear las instancias de un objeto de cliente y llamar a los métodos adecuados. Puede encontrar más información sobre el SDK de Azure para .NET en la [Información general sobre el SDK de Azure para .NET](./sdk/azure-sdk-for-dotnet.md).

![Diagrama en el que se muestra cómo usan las aplicaciones .NET el SDK de Azure para acceder a los servicios de Azure](./media/azure-sdk-for-dotnet-overview.png)

## <a name="next-steps"></a>Pasos siguientes

A continuación, obtenga información sobre los [servicios de Azure usados con frecuencia](./key-azure-services.md) para el desarrollo de .NET.
