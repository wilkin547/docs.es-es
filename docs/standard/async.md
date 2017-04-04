---
title: "Información general de Async"
description: "Información general de Async"
keywords: .NET, .NET Core
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 1e38e9d9-8284-46ee-a15f-199adc4f26f4
translationtype: Human Translation
ms.sourcegitcommit: b967d8e55347f44a012e4ad8e916440ae228c8ec
ms.openlocfilehash: db4c9721381a9675b06f0fc6b5381d987816e9a4
ms.lasthandoff: 03/10/2017

---

# <a name="async-overview"></a>Información general de Async

No hace tanto tiempo, las aplicaciones funcionaban más rápido simplemente al comprar un PC o servidor nuevo y después se detuvo esa tendencia. De hecho, se ha invertido. Aparecieron teléfonos móviles con chips ARM de núcleo único de 1 GHz y cargas de trabajo de servidor que pasaron a máquinas virtuales. Los usuarios seguían queriendo una interfaz de usuario dinámica y los propietarios de empresas querían servidores que se ajustaran a su negocio. La transición al móvil y a la nube y una población conectada a Internet de más de 3 mil millones de usuarios ha generado un nuevo conjunto de patrones de software. 

* Se espera que las aplicaciones cliente estén siempre activadas y conectadas, y que respondan adecuadamente a la interacción del usuario (p. ej., función táctil) con altas calificaciones en la tienda de aplicaciones.
* Se espera que los servicios controlen los picos de tráfico al escalar y reducir verticalmente con facilidad. 

La programación de Async es una técnica clave que facilita controlar las operaciones simultáneas y de E/S de bloqueo en varios núcleos. .NET proporciona a servicios y aplicaciones la capacidad de ser dinámicos y elásticos con modelos de programación asincrónicos de nivel de lenguaje y fáciles de usar en C#, VB y F#.

## <a name="why-write-async-code"></a>¿Por qué escribir código asincrónico?

Las aplicaciones modernas usan de forma intensiva la E/S de archivos y redes. Tradicionalmente, las API de E/S bloquean de manera predeterminada, lo que da lugar a experiencias de usuario y uso del hardware pobres a menos que quiera aprender y usar patrones exigentes. Las API de Async y el modelo de programación asincrónico de nivel de lenguaje invierten este modelo, de modo que establecen la ejecución de Async como la predeterminada con algunos conceptos nuevos que aprender.

El código de Async tiene las siguientes características:

* Controla más solicitudes del servidor al producir subprocesos que controlan más solicitudes mientras esperan a que devuelvan las solicitudes de E/S.
* Permite que las interfaces de usuario sean más dinámicas al ceder subprocesos a la interacción de la interfaz de usuario mientras esperan las solicitudes de E/S y al pasar trabajo de ejecución prolongada a otros núcleos de CPU.
* Muchas de las API de .NET más recientes son asincrónicas.
* Es muy fácil escribir código asincrónico en .NET.

## <a name="whats-next"></a>Pasos adicionales

Para profundizar en los conceptos y programación de Async, consulte [Async en profundidad](async-in-depth.md).


