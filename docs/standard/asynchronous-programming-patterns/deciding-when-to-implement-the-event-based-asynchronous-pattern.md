---
title: Decidir cuándo implementar el modelo asincrónico basado en eventos
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: a00046aa-785d-4f7f-a8e5-d06475ea50da
ms.openlocfilehash: c235a838504889a105ef98df47f7373a145503da
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289452"
---
# <a name="deciding-when-to-implement-the-event-based-asynchronous-pattern"></a>Decidir cuándo implementar el modelo asincrónico basado en eventos

El modelo asincrónico basado en eventos proporciona un modelo para exponer el comportamiento asincrónico de una clase. Con la incorporación de este patrón, .NET Framework define dos modelos para exponer el comportamiento asincrónico: el modelo asincrónico basado en la interfaz <xref:System.IAsyncResult?displayProperty=nameWithType> y el modelo basado en eventos. En este tema se describe cuándo es adecuado permitirle implementar ambos modelos.

Para obtener más información sobre la programación asincrónica con la interfaz <xref:System.IAsyncResult>, vea [Modelo de programación asincrónica (APM)](asynchronous-programming-model-apm.md).

## <a name="general-principles"></a>Principios generales

En general, se deben exponer las características asincrónicas mediante el modelo asincrónico basado en eventos siempre que sea posible. Sin embargo, hay algunos requisitos que el modelo basado en eventos no puede cumplir. En esos casos, puede que necesite implementar el modelo <xref:System.IAsyncResult> además del modelo basado en eventos.

> [!NOTE]
> Es raro que el modelo <xref:System.IAsyncResult> se implemente sin haber implementado el modelo basado en eventos.

## <a name="guidelines"></a>Instrucciones

En la lista siguiente se describen las instrucciones sobre cuándo implementar el modelo asincrónico basado en eventos:

- Utilice el modelo basado en eventos como la API predeterminada para exponer el comportamiento asincrónico para la clase.

- No exponga el modelo <xref:System.IAsyncResult> cuando la clase se utiliza principalmente en una aplicación cliente, por ejemplo, Windows Forms.

- Exponga el modelo <xref:System.IAsyncResult> solo cuando sea necesario para satisfacer sus requisitos. Por ejemplo, la compatibilidad con una API existente puede requerir que se exponga el modelo <xref:System.IAsyncResult>.

- No exponga el modelo <xref:System.IAsyncResult> sin exponer también el modelo basado en eventos.

- Si debe exponer el modelo <xref:System.IAsyncResult>, hágalo como una opción avanzada. Por ejemplo, si genera un objeto proxy, genere el modelo basado en eventos de forma predeterminada, con una opción para generar el modelo <xref:System.IAsyncResult>.

- Compile su implementación del modelo basado en eventos en la implementación del modelo <xref:System.IAsyncResult>.

- Evite exponer tanto el modelo basado en eventos como el modelo <xref:System.IAsyncResult> en la misma clase. Exponga el modelo basado en eventos en las clases de "nivel superior" y el modelo <xref:System.IAsyncResult> en las clases de "nivel inferior". Por ejemplo, compare el modelo basado en eventos del componente <xref:System.Net.WebClient> con el modelo <xref:System.IAsyncResult> de la clase <xref:System.Web.HttpRequest>.

  - Exponga el modelo basado en eventos y el modelo <xref:System.IAsyncResult> en la misma clase cuando lo requiera la compatibilidad. Por ejemplo, si ya ha publicado una API que usa el modelo <xref:System.IAsyncResult>, quizá necesite conservar el modelo <xref:System.IAsyncResult> por compatibilidad con versiones anteriores.

  - Exponga el modelo basado en eventos y el modelo <xref:System.IAsyncResult> en la misma clase si la complejidad del modelo de objetos resultante supera la ventaja de separar las implementaciones. Es mejor exponer ambos modelos en una sola clase que evitar exponer el modelo basado en eventos.

  - Si debe exponer tanto el modelo basado en eventos como el modelo <xref:System.IAsyncResult> en una sola clase, use <xref:System.ComponentModel.EditorBrowsableAttribute> establecido en <xref:System.ComponentModel.EditorBrowsableState.Advanced> para marcar la implementación del modelo <xref:System.IAsyncResult> como una característica avanzada. Esto indica a los entornos de diseño, como IntelliSense en Visual Studio, que no muestren las propiedades y los métodos de <xref:System.IAsyncResult>. Estas propiedades y métodos todavía son totalmente utilizables, pero el desarrollador que trabaja con IntelliSense tiene una visión más clara de la API.

## <a name="criteria-for-exposing-the-iasyncresult-pattern-in-addition-to-the-event-based-pattern"></a>Criterios para exponer el modelo IAsyncResult además del modelo basado en eventos

Aunque el modelo asincrónico basado en eventos tiene muchas ventajas en los escenarios mencionados anteriormente, también tiene algunas desventajas, que debe tener en cuenta si el rendimiento es el requisito más importante.

Hay tres escenarios que no se abordan con el modelo basado en eventos ni con el modelo <xref:System.IAsyncResult>:

- Espera bloqueada en un objeto <xref:System.IAsyncResult>

- Espera bloqueada en muchos objetos <xref:System.IAsyncResult>

- Sondeo de la finalización del objeto <xref:System.IAsyncResult>

Puede resolver estos escenarios con el modelo basado en eventos, pero es más complicado que usar el modelo <xref:System.IAsyncResult>.

Los desarrolladores suelen utilizar el modelo <xref:System.IAsyncResult> para los servicios que normalmente tienen requisitos de muy alto rendimiento. Por ejemplo, el sondeo para el escenario de finalización es una técnica de servidor de alto rendimiento.

Además, el modelo basado en eventos es menos eficaz que el modelo <xref:System.IAsyncResult> porque crea más objetos, especialmente <xref:System.EventArgs>, y debido a que se sincroniza entre subprocesos.

En la lista siguiente se indican algunas recomendaciones que deben seguirse si decide utilizar el modelo <xref:System.IAsyncResult>:

- Solo exponga el modelo <xref:System.IAsyncResult> si necesita compatibilidad específica para los objetos <xref:System.Threading.WaitHandle> o <xref:System.IAsyncResult>.

- Solo exponga el modelo <xref:System.IAsyncResult> si tiene una API existente que usa el modelo <xref:System.IAsyncResult>.

- Si tiene una API existente basada en el modelo <xref:System.IAsyncResult>, considere también la posibilidad de exponer el modelo basado en eventos en la próxima versión.

- Solo exponga el modelo <xref:System.IAsyncResult> si tiene requisitos de alto rendimiento que haya comprobado que no se pueden satisfacer con el modelo basado en eventos, pero sí con el modelo <xref:System.IAsyncResult>.

## <a name="see-also"></a>Vea también

- [Implementar un componente que admita el modelo asincrónico basado en eventos](component-that-supports-the-event-based-asynchronous-pattern.md)
- [Modelo asincrónico basado en eventos (EAP)](event-based-asynchronous-pattern-eap.md)
- [Implementación del modelo asincrónico basado en eventos](implementing-the-event-based-asynchronous-pattern.md)
- [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [Event-based Asynchronous Pattern Overview](event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)
