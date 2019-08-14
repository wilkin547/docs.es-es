---
title: 'Información general de las herramientas de diagnóstico: .NET Core'
description: Información general de las herramientas y técnicas disponibles para diagnosticar las aplicaciones de .NET Core.
author: sdmaclea
ms.author: stmaclea
ms.date: 08/05/2019
ms.topic: overview
ms.openlocfilehash: f107d15fa5584bb5a4834b5f11f1096bec7eb749
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974153"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a>¿Qué herramientas de diagnóstico están disponibles en .NET Core?

El comportamiento del software no siempre es el esperado, pero .NET Core tiene herramientas y API que lo ayudarán a diagnosticar estos problemas de manera rápida y eficaz.

Este artículo lo ayuda a encontrar las distintas herramientas que necesita.

## <a name="managed-debuggersmanaged-debuggersmd"></a>[Depuradores administrados](managed-debuggers.md)
Los depuradores administrados le permiten interactuar con el programa. Pausar, ejecutar de manera incremental, examinar y reanudar le proporcionan información sobre el comportamiento del código. Un depurador es la primera opción para diagnosticar problemas funcionales que se pueden reproducir de manera fácil.

## <a name="logging-and-tracinglogging-tracingmd"></a>[Registro y seguimiento](logging-tracing.md)
El registro y seguimiento son técnicas relacionadas. Hacen referencia a la instrumentación del código para crear archivos de registro. Los archivos registran los detalles de lo que hace un programa. Estos detalles se pueden usar para diagnosticar los problemas más complejos. Cuando se combinan con marcas de tiempo, estas técnicas también son valiosas para investigaciones de rendimiento.

## <a name="unit-testingtestingindexmd"></a>[Pruebas unitarias](../testing/index.md)
Las pruebas unitarias son un componente clave de la integración continua y la implementación de software de alta calidad. Las pruebas unitarias están diseñadas para brindarle una advertencia temprana cuando se daña algo.
