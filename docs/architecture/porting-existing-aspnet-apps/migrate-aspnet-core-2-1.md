---
title: Migración a ASP.NET Core 2.1
description: Como la última versión de .NET Core para admitir .NET Framework destino en tiempo de ejecución, ¿la migración a .NET Core 2,1 tiene sentido como paso intermedio en algunos planes de migración de aplicaciones?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 0c478ae194c6d9118bfbca73f8933d7623246e2c
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401731"
---
# <a name="migrate-to-aspnet-core-21"></a>Migración a ASP.NET Core 2.1

ASP.NET Core 2,1 es una versión interesante porque es la única versión de .NET Core compatible actualmente para admitir los tiempos de ejecución de .NET Core y .NET Framework. Por lo tanto, puede ofrecer una ruta de actualización más sencilla para algunas aplicaciones en comparación con la actualización de todas las partes de la aplicación a .NET Core a la vez. Como versión de LTS, la compatibilidad con .NET Core 2,1 continuará hasta agosto de 2021. La compatibilidad con ASP.NET Core 2,1 que se ejecutan en .NET Framework continuará siempre que se admita su .NET Framework subyacente.

## <a name="should-apps-run-on-net-framework-with-aspnet-core-21"></a>¿Las aplicaciones deben ejecutarse en .NET Framework con ASP.NET Core 2,1

ASP.NET Core 2,2 y versiones anteriores admitían .NET Core y los tiempos de ejecución de .NET Framework. ¿Tiene sentido migrar algunas o todas las aplicaciones a ASP.NET Core 2,1 como una piedra de paso, antes de migrar completamente a .NET Core? Las aplicaciones, o subconjuntos de aplicaciones, pueden ver que su lógica de ASP.NET de front-end se ha trasladado para usar ASP.NET Core, al tiempo que se siguen consumiendo .NET Framework bibliotecas para el consumo de infraestructura y lógica empresarial. Este enfoque puede tener sentido cuando hay una capa de interfaz de usuario relativamente delgada sin una gran cantidad de lógica empresarial y un conjunto mucho mayor de funcionalidad en las bibliotecas de clases.

La principal ventaja de trasladar solo el nivel Web front-end a ASP.NET Core 2,1 es que las bibliotecas de clases .NET existentes pueden permanecer tal cual durante la migración inicial. Pueden estar en uso continuado por otras aplicaciones de .NET o simplemente no necesitan estar en el ámbito de la primera iteración de una migración completa planeada a .NET Core. La reducción del ámbito de la migración inicial de las aplicaciones de gran tamaño ayuda a proporcionar objetivos incrementales que actúan como piedras de paso hacia el estado final deseado, que suele ser un puerto completo para .NET Core.

Si tiene una aplicación existente que puede usar esta estrategia, algunas cosas que puede hacer hoy para ayudar a preparar el proceso consisten en trasladar la lógica de negocios, el acceso a los datos y otra lógica que no sea de interfaz de usuario de los proyectos de ASP.NET y a bibliotecas de clases independientes como sea posible. También le ayudará si tiene una cobertura de pruebas automatizada del sistema, de modo que pueda comprobar que el comportamiento permanece coherente antes y después de la migración.

Si su aplicación es tan grande que no puede migrar toda la aplicación web a la vez, y necesita poder implementar la nueva aplicación ASP.NET Core en paralelo con la aplicación ASP.NET existente, existen estrategias de implementación que se pueden usar para lograrlo. Estos se describen en el [capítulo 5: escenarios de implementación](deployment-scenarios.md).

Tenga en cuenta que ASP.NET Core 2,1 es la última versión LTS de .NET Core que admite la ejecución en .NET Framework y consumo de bibliotecas de .NET Framework. Pronto no se admitirá esta versión, pero se admitirán ASP.NET Core 2,1 en .NET Framework, siempre que el .NET Framework (incluso después de que finalice la compatibilidad con .NET Core 2,1). Para obtener más información, vea [ASP.NET Core 2,1 en .NET Framework](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

## <a name="references"></a>Referencias

[Migración de ASP.NET a ASP.NET Core 2,1](/aspnet/core/migration/proper-to-2x/?preserve-view=true&view=aspnetcore-2.1)

>[!div class="step-by-step"]
>[Anterior](migration-considerations.md)
>[Siguiente](choose-net-core-version.md)
