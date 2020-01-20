---
title: Información general de Async
description: Obtenga información sobre cómo la programación de Async es una técnica clave que ayuda a controlar las operaciones simultáneas y de E/S de bloqueo en varios núcleos.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: 1e38e9d9-8284-46ee-a15f-199adc4f26f4
ms.openlocfilehash: 1570909b7b416eff81dd90a936ff5ed10aad94f1
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346085"
---
# <a name="async-overview"></a>Información general de Async

No hace tanto tiempo, las aplicaciones funcionaban más rápido simplemente al comprar un PC o servidor nuevo y después se detuvo esa tendencia. De hecho, se ha invertido. Aparecieron teléfonos móviles con chips ARM de núcleo único de 1 GHz y cargas de trabajo de servidor que pasaron a máquinas virtuales. Los usuarios seguían queriendo una interfaz de usuario dinámica y los propietarios de empresas querían servidores que se ajustaran a su negocio. La transición al móvil y a la nube y una población conectada a Internet de más de 3 mil millones de usuarios ha generado un nuevo conjunto de patrones de software. 

- Se espera que las aplicaciones cliente estén siempre activadas y conectadas, y que respondan adecuadamente a la interacción del usuario (p. ej., función táctil) con altas calificaciones en la tienda de aplicaciones.
- Se espera que los servicios controlen los picos de tráfico al escalar y reducir verticalmente con facilidad. 

La programación de Async es una técnica clave que facilita controlar las operaciones simultáneas y de E/S de bloqueo en varios núcleos. .NET proporciona la funcionalidad de que servicios y aplicaciones sean dinámicos y elásticos con modelos de programación asincrónicos de nivel de lenguaje y fáciles de usar en C#, Visual Basic y F#.

## <a name="why-write-async-code"></a>¿Por qué escribir código asincrónico?

Las aplicaciones modernas usan de forma intensiva la E/S de archivos y redes. Tradicionalmente, las API de E/S bloquean de manera predeterminada, lo que da lugar a experiencias de usuario y uso del hardware pobres a menos que quiera aprender y usar patrones exigentes. Las API asincrónicas basadas en tareas y el modelo de programación asincrónico de nivel de lenguaje invierten este modelo, de modo que establecen la ejecución asincrónica como la predeterminada con algunos conceptos nuevos que aprender.

El código asincrónico tiene las siguientes características:

- Controla más solicitudes del servidor al producir subprocesos que controlan más solicitudes mientras esperan a que devuelvan las solicitudes de E/S.
- Permite que las interfaces de usuario sean más dinámicas al ceder subprocesos a la interacción de la interfaz de usuario mientras esperan las solicitudes de E/S y al pasar trabajo de ejecución prolongada a otros núcleos de CPU.
- Muchas de las API de .NET más recientes son asincrónicas.
- Es fácil escribir código asincrónico en .NET.

## <a name="whats-next"></a>Pasos adicionales

Para obtener más información, vea el tema [Async en profundidad](async-in-depth.md).

En el tema [Modelos para la programación asincrónica](asynchronous-programming-patterns/index.md), se proporciona una introducción de los tres modelos de programación asincrónica que se admiten en .NET:  
  
- [Asynchronous Programming Model (APM)](asynchronous-programming-patterns/asynchronous-programming-model-apm.md) [Modelo de programación asincrónica (APM)] (heredado)  
  
- [Event-based Asynchronous Pattern (EAP)](asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) [Modelo asincrónico basado en eventos (EAP)] (heredado)  
  
- [Task-based Asynchronous Pattern (TAP)](asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) [Modelo asincrónico basado en tareas (TAP)] (recomendado para nuevos desarrollos)  

Para obtener más información sobre el modelo de programación basado en tareas recomendado, consulte el tema [Programación asincrónica basada en tareas](parallel-programming/task-based-asynchronous-programming.md).
