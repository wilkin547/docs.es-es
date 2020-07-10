---
title: Comparación de arquitectura de formularios Web Forms ASP.NETBlazor
description: Obtenga información sobre cómo se comparan las arquitecturas de formularios Web Forms ASP.NET y Blazor .
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 09/11/2019
ms.openlocfilehash: 51b114c842e131ad9b9a589bf5137a522e135082
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173437"
---
# <a name="architecture-comparison-of-aspnet-web-forms-and-blazor"></a>Comparación de arquitectura de formularios Web Forms ASP.NETBlazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Aunque los formularios Web Forms de ASP.NET y Blazor tienen muchos conceptos similares, existen diferencias en el modo en que funcionan. En este capítulo se examinan los trabajos internos y las arquitecturas de formularios Web Forms de ASP.NET y Blazor .

## <a name="aspnet-web-forms"></a>Formularios Web Forms ASP.NET

El marco de trabajo de formularios Web Forms de ASP.NET se basa en una arquitectura centrada en páginas. Cada solicitud HTTP para una ubicación en la aplicación es una página independiente con la que responde ASP.NET. A medida que se solicitan páginas, el contenido del explorador se reemplaza con los resultados de la página solicitada.

Las páginas se componen de los siguientes componentes:

- Marcado HTML
- Código de C# o Visual Basic
- Una clase de código subyacente que contiene capacidades de control de eventos y lógica
- Controles

Los controles son unidades reutilizables de la interfaz de usuario Web que se pueden colocar e interactuar mediante programación en una página. Las páginas se componen de archivos que terminan en *. aspx* y contienen marcado, controles y código. Las clases de código subyacente se encuentran en archivos con el mismo nombre base y una extensión. *aspx.CS* o *. aspx. VB* , según el lenguaje de programación utilizado. Curiosamente, el servidor Web interpreta el contenido de los archivos *. aspx* y los compila cada vez que cambian. Esta recompilación se produce incluso si el servidor web ya se está ejecutando.

Los controles se pueden compilar con marcado y se proporcionan como controles de usuario. Un control de usuario se deriva de la `UserControl` clase y tiene una estructura similar a la página. El marcado de los controles de usuario se almacena en un archivo *. ascx* . Una clase de código subyacente adjunta se encuentra en un archivo *. ascx.CS* o *. ascx. VB* . Los controles también se pueden compilar completamente con código, heredando de `WebControl` la `CompositeControl` clase base o.

Las páginas también tienen un ciclo de vida de eventos amplio. Cada página genera eventos para los eventos de inicialización, carga, preprocesamiento y descarga que se producen cuando el tiempo de ejecución de ASP.NET ejecuta el código de la página para cada solicitud.

Normalmente, los controles de una página se reenvían a la misma página que presentó el control y llevan una carga de un campo de formulario oculto denominado `ViewState` . El `ViewState` campo contiene información sobre el estado de los controles en el momento en que se representaron y se presentaron en la página, lo que permite que el tiempo de ejecución de ASP.net compare e identifique los cambios en el contenido que se envía al servidor.

## Blazor

Blazores un marco de interfaz de usuario Web del lado cliente similar en naturaleza a las plataformas de front-end de JavaScript como angular o reAct. Blazorcontrola las interacciones del usuario y representa las actualizaciones necesarias de la interfaz de usuario. Blazor*no se* basa en un modelo de solicitud-respuesta. Las interacciones del usuario se controlan como eventos que no están en el contexto de una solicitud HTTP determinada.

Blazorlas aplicaciones constan de uno o más componentes raíz que se representan en una página HTML.

![Blazorcomponentes en HTML](./media/architecture-comparison/blazor-components-in-html.png)

La forma en que el usuario especifica dónde se deben representar los componentes y cómo se conectan los componentes para las interacciones de usuario es específico del [modelo de hospedaje](hosting-models.md) .

Blazor[los componentes](components.md) son clases .net que representan una parte reutilizable de la interfaz de usuario. Cada componente mantiene su propio estado y especifica su propia lógica de representación, que puede incluir la representación de otros componentes. Los componentes de especifican los controladores de eventos para interacciones de usuario específicas para actualizar el estado del componente.

Una vez que un componente controla un evento, Blazor representa el componente y realiza un seguimiento de lo que ha cambiado en la salida representada. Los componentes no se representan directamente en el Document Object Model (DOM). En su lugar, se representan en una representación en memoria del DOM denominada `RenderTree` para que Blazor pueda realizar el seguimiento de los cambios. Blazorcompara la salida recién representada con la salida anterior para calcular una diferencia de interfaz de usuario que, a continuación, se aplica de forma eficaz al DOM.

![BlazorInteracción con DOM](./media/architecture-comparison/blazor-dom-interaction.png)

Los componentes también pueden indicar manualmente que se deben representar si su estado cambia fuera de un evento normal de la interfaz de usuario. Blazor usa un elemento `SynchronizationContext` para aplicar un único subproceso lógico de ejecución. Los métodos de ciclo de vida de un componente y todas las devoluciones de llamada de eventos que Blazor genere se ejecutan en dicho elemento `SynchronizationContext`.

>[!div class="step-by-step"]
>[Anterior](introduction.md)
>[Siguiente](hosting-models.md)
