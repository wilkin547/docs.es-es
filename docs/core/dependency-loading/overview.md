---
title: 'Carga de dependencias: .NET Core'
description: Información general sobre la carga de dependencias administradas y no administradas en .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.topic: overview
ms.openlocfilehash: 2eaa01fad3913272dc90891592d0e35cd89ad2ab
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506323"
---
# <a name="dependency-loading-in-net-core"></a>Carga de dependencias en .NET Core

Todas las aplicaciones .NET Core tienen dependencias. Incluso la aplicación sencilla `hello world` tiene dependencias en partes de las bibliotecas de clases de .NET Core.

La descripción de la lógica de carga de ensamblados predeterminados de .NET Core puede ayudar a comprender y depurar incidencias de implementación habituales.

En algunas aplicaciones, las dependencias se determinan dinámicamente en tiempo de ejecución. En estas situaciones, es fundamental entender cómo se cargan los ensamblados administrados y las dependencias no administradas.

## <a name="understanding-assemblyloadcontext"></a>Descripción de AssemblyLoadContext

La API <xref:System.Runtime.Loader.AssemblyLoadContext> es fundamental para el diseño de carga de .NET Core. En el artículo [Descripción de AssemblyLoadContext ](understanding-assemblyloadcontext.md) se proporciona información general conceptual para el diseño.

## <a name="loading-details"></a>Carga de detalles

Los detalles del algoritmo de carga se describen brevemente en varios artículos:

- [Algoritmo de carga de ensamblado administrado](loading-managed.md)
- [Algoritmo de carga de ensamblado satélite](loading-resources.md)
- [Algoritmo de carga de biblioteca no administrada (nativa)](loading-unmanaged.md)
- [Sondeo predeterminado](default-probing.md)

## <a name="create-a-net-core-application-with-plugins"></a>Creación de una aplicación de .NET Core con complementos

En el tutorial [Creación de una aplicación .NET Core con complementos](../tutorials/creating-app-with-plugin-support.md) se describe cómo crear un elemento AssemblyLoadContext personalizado. Usa un elemento <xref:System.Runtime.Loader.AssemblyDependencyResolver> para resolver las dependencias del complemento. El tutorial aísla correctamente las dependencias del complemento de la aplicación host.

## <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a>Uso y depuración de la descargabilidad de ensamblado en .NET Core

El artículo [Uso y depuración de la descargabilidad de ensamblado en .NET Core](../../standard/assembly/unloadability.md) es un tutorial paso a paso. Muestra cómo cargar una aplicación .NET Core, ejecutarla y luego descargarla. En el artículo también se proporcionan sugerencias de depuración.

## <a name="collect-detailed-assembly-loading-information"></a>Recopilación de información detallada de carga de ensamblados

En el artículo [Recopilación de información detallada de carga de ensamblados](collect-details.md) se describe cómo recopilar información detallada sobre la carga de ensamblados administrados en el entorno de ejecución. Usa la herramienta [dotnet-trace](../diagnostics/dotnet-trace.md) para capturar eventos del cargador de ensamblados en un seguimiento de un proceso en ejecución.
