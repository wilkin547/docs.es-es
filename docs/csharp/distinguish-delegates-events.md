---
title: "Distinción de delegados y eventos"
description: "Distinción de delegados y eventos"
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0fdc8629-2fdb-4a7c-a433-5b9d04eaf911
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4020df1a63cbcdeb7e7b5d9d49cfe6444a43655e
ms.lasthandoff: 03/13/2017

---

# <a name="distinguising-delegates-and-events"></a>Distinción de delegados y eventos

[Anterior](modern-events.md)

Los desarrolladores que son nuevos en la plataforma de NET Core a menudo tienen problemas para decidir entre un diseño basado en `delegates` y uno basado en `events`. Este es un concepto difícil, porque las dos características del lenguaje son muy similares. Los eventos incluso se crean con compatibilidad de lenguaje para los delegados. 

Ambos ofrecen un escenario de enlace en tiempo de ejecución: permiten escenarios donde un componente se comunica mediante una llamada a un método que solo se conoce en tiempo de ejecución. Ambos admiten métodos de suscriptor único y múltiple. Puede que se haga referencia a estos términos como compatibilidad con multidifusión o de conversión única. Ambos admiten una sintaxis similar para agregar y quitar controladores. Por último, para generar un evento y llamar a un delegado se usa exactamente la misma sintaxis de llamada de método. Incluso los dos admiten la misma sintaxis del método `Invoke()` para su uso con el operador `?.`.

Con todas estas similitudes, es fácil tener problemas para determinar cuándo usar cada uno.

## <a name="listening-to-events-is-optional"></a>La escucha de eventos es opcional

La consideración más importante para determinar qué característica de lenguaje usar es si debe haber o no un suscriptor adjunto. Si el código debe llamar al código proporcionado por el suscriptor, debe usar un diseño basado en delegados. Si el código puede completar todo su trabajo sin llamar a ningún suscriptor, debe usar un diseño basado en eventos. 

Tenga en cuenta los ejemplos que se crean en esta sección. Al código que ha creado con `List.Sort()` se le debe proporcionar una función de comparador para ordenar los elementos de manera adecuada. Las consultas LINQ deben proporcionarse con delegados para determinar qué elementos se van a devolver. Ambos han usado un diseño creado con delegados.

Considere el evento `Progress`. Notifica el progreso de una tarea.
La tarea continúa haya o no agentes de escucha.
`FileSearcher` es otro ejemplo. Todavía buscaría y encontraría todos los archivos que se han solicitado, incluso sin ningún suscriptor de eventos adjunto.
Los controles de UX todavía funcionan correctamente, incluso cuando no hay ningún suscriptor escuchando los eventos. Ambos usan diseños basados en eventos.

## <a name="return-values-require-delegates"></a>Los valores devueltos necesitan delegados

Otra consideración es el prototipo del método que quiere para el método delegado. Como ha visto, todos los delegados que se han usado para los eventos tienen un tipo de valor devuelto void. También ha visto que hay elementos para crear controladores de eventos que pasan información de nuevo a los orígenes de eventos mediante la modificación de las propiedades del objeto de argumento del evento. Aunque estos elementos funcionan, no son tan naturales como la devolución de un valor de un método.

Tenga en cuenta que estas dos heurísticas pueden estar presentes a menudo: si su método delegado devuelve un valor, probablemente afectará al algoritmo de alguna manera.

## <a name="event-listeners-often-have-longer-lifetimes"></a>Los agentes de escucha de eventos a menudo tienen una vigencia mayor 

Esta es una justificación ligeramente más débil. En cambio, puede encontrar que los diseños basados en eventos son más naturales cuando el origen de eventos generará eventos durante un período de tiempo largo. Puede ver ejemplos de esto para los controles de UX en muchos sistemas. Cuando se suscriba a un evento, el origen de eventos puede generar eventos durante la vigencia del programa.
(Puede anular la suscripción de los eventos cuando ya no los necesite).

Compare eso con muchos diseños basados en delegados, donde un delegado se usa como un argumento para un método, y el delegado no se usa después de que se devuelva ese método.

## <a name="evaluate-carefully"></a>Evaluar cuidadosamente

Las consideraciones anteriores no son reglas rápidas ni estrictas. En su lugar, representan instrucciones que pueden ayudarle a decidir qué opción es mejor para su uso particular. Como son similares, incluso puede crear un prototipo de los dos y considerar con cuál sería más natural trabajar. Ambos controlan escenarios de enlace en tiempo de ejecución correctamente. Use el que comunique mejor su diseño.

