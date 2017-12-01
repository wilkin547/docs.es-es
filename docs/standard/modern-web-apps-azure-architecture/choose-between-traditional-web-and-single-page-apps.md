---
title: "Elija entre las aplicaciones web tradicionales y las aplicaciones de página única"
description: "Diseñar aplicaciones web modernas con ASP.NET Core y Microsoft Azure"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 5bae77fc4e0df9d0bc7fecfad25adfcee2419084
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2017
---
# <a name="choose-between-traditional-web-apps-and-single-page-apps-spas"></a>Elija entre las aplicaciones Web tradicionales y las aplicaciones de página única (SPAs)

> "La ley del Atwood: cualquier aplicación que puede escribirse en JavaScript, se escribirá finalmente en JavaScript."  
> _\-Juan Atwood_

## <a name="summary"></a>Resumen

Hay dos enfoques generales para hoy mismo a crear aplicaciones web: aplicaciones web tradicionales que realizan la mayor parte de la lógica de aplicación en el servidor y aplicaciones de una página (SPAs) que realizan la mayor parte de la lógica de la interfaz de usuario en un explorador web, comunicarse con el servidor web principalmente mediante las API web. También es posible un enfoque híbrido, el más sencillo es host uno o más enriquecidas SPA subcarpetas aplicaciones dentro de una aplicación web tradicional más grande.

Debe usar las aplicaciones web tradicionales cuando:

-   Requisitos de la aplicación de cliente son sencillos o incluso de solo lectura.

-   La aplicación necesita funcionar en exploradores que no admiten JavaScript.

-   El equipo no está familiarizado con las técnicas de desarrollo de JavaScript o TypeScript.

Debe usar un SPA cuando:

-   La aplicación debe exponer una interfaz de usuario enriquecida con muchas características.

-   El equipo está familiarizado con el desarrollo de JavaScript o TypeScript.

-   La aplicación ya debe exponer una API para otros clientes (internos o públicos).

Además, los marcos SPA requieren mayor arquitectónicos y consejos de seguridad. Se producen renovación mayor debido a actualizaciones frecuentes y marcos de trabajo nueva que las aplicaciones web tradicionales. Configuración de procesos de compilación e implementación automatizados y utilización de las opciones de implementación como contenedores son más difíciles con aplicaciones de SPA que las aplicaciones web tradicionales.

Mejoras en la experiencia del usuario posibilita el modelo SPA deben ponderarse con estas consideraciones.

## <a name="when-to-choose-traditional-web-apps"></a>Cuándo se debe elegir las aplicaciones web tradicionales

La siguiente es una explicación más detallada de los motivos indicados anteriormente para la selección de las aplicaciones web tradicionales.

**La aplicación tiene requisitos simples, posiblemente de solo lectura y de cliente**

Muchas aplicaciones web se usan principalmente en un modo de solo lectura por la mayoría de los usuarios. Las aplicaciones de solo lectura (o principalmente de solo lectura) tienden a ser mucho más sencillas que las que mantener y manipular una gran cantidad de estado. Por ejemplo, un motor de búsqueda puede consistir en un único punto de entrada con un cuadro de texto y una segunda página para mostrar los resultados de la búsqueda. Los usuarios anónimos pueden realizar fácilmente las solicitudes y no hay poca necesidad de lógica de cliente. Del mismo modo, aplicación de acceso público de un blog o contenido de administración del sistema suele estar compuesto principalmente de contenido con un comportamiento de cliente poco. Dichas aplicaciones fácilmente generadas como aplicaciones web tradicionales basados en servidor que ejecute la lógica en el servidor web y representan HTML que se mostrará en el explorador. El hecho de que cada página del sitio único tiene su propia dirección URL que se marcaron e indexado por motores de búsqueda (de forma predeterminada, sin tener que agregar esto como una característica independiente de la aplicación) también es una ventaja clara en tales escenarios.

**La aplicación necesita para funcionar en exploradores que no admiten JavaScript**

Las aplicaciones Web que necesitan para funcionar en los exploradores con acceso limitado o no se admite JavaScript deben escribirse mediante flujos de trabajo de aplicaciones web tradicionales (o al menos que pueda revertir al comportamiento de este tipo). SPAs requieren JavaScript del lado cliente para poder funcionar; Si no está disponible, SPAs no son una buena elección.

**El equipo no está familiarizado con las técnicas de desarrollo de JavaScript o TypeScript**

Si el equipo no está familiarizado con JavaScript o TypeScript, pero está familiarizado con el desarrollo de aplicaciones de servidor web, probablemente será capaz de ofrecer una aplicación web tradicional más rápidamente que un SPA. A menos que el aprendizaje a programa SPAs es un objetivo o la experiencia del usuario ofrecida un SPA es necesaria, las aplicaciones web tradicionales son una opción más productiva para que los equipos que ya están familiarizados con la creación de ellos.

## <a name="when-to-choose-spas"></a>Cuándo se debe optar SPAs

La siguiente es una explicación más detallada de cuándo se debe elegir un estilo de aplicaciones de una sola página de desarrollo de la aplicación web.

**La aplicación debe exponer una interfaz de usuario enriquecida con muchas características**

SPAs pueden admitir una amplia funcionalidad de cliente que no requiere volver a cargar la página cuando los usuarios realicen acciones o navegar entre las áreas de la aplicación. SPAs pueden cargar más rápidamente, capturar los datos en segundo plano, y las acciones del usuario individual son más sensibles, ya que son poco frecuentes recargas de página completa. SPAs pueden admitir las actualizaciones incrementales, guardar formularios completadas parcialmente o documentos sin que el usuario tiene que hacer clic en un botón para enviar un formulario. SPAs pueden admitir los comportamientos de cliente enriquecidos, como arrastrar y colocar, mucho más fácil que las aplicaciones tradicionales. SPAs pueden diseñarse para que se ejecute en un modo sin conexión, realizar actualizaciones en un modelo de cliente que se sincronizan finalmente al servidor una vez que se restablece una conexión. Debe elegir una aplicación de estilo SPA si los requisitos de la aplicación incluyen amplia funcionalidad que va más allá de lo que ofrecen los formularios HTML típicos.

Tenga en cuenta que con frecuencia SPAs deben implementar características integradas para las aplicaciones web tradicionales, como mostrar una dirección URL significativa en la dirección barra que refleja la operación actual (y que permite a los usuarios de marcador o vínculo profundo a esta dirección URL volver a él). SPAs también deben permitir a los usuarios utilizar el explorador botones Atrás y adelante con resultados que no le sorprende ellos.

**El equipo está familiarizado con el desarrollo de JavaScript o TypeScript**

Escribir SPAs, es necesario estar familiarizado con JavaScript o TypeScript y técnicas de programación de cliente y las bibliotecas. El equipo debería ser competente en escribir JavaScript moderno con un marco SPA como Angular.

> ### <a name="references--spa-frameworks"></a>Referencias: marcos SPA
> - **AngularJS**  
> <https://angularjs.org/>
> - **Comparación de 4 marcos de JavaScript populares**  
> <https://www.developereconomics.com/Feature-Comparison-of-4-popular-js-MV-Frameworks>

**La aplicación ya debe exponer una API para otros clientes (internos o públicos)**

Si ya admite una API web para su uso por otros clientes, puede requerir menos trabajo para crear una implementación de SPA que saque provecho de estas API en lugar de reproducir la lógica del formulario de servidor. SPAs realizar un amplio uso de las API web para consultar y actualizar datos cuando los usuarios interactúan con la aplicación.

## <a name="decision-table--traditional-web-or-spa"></a>Tabla de decisiones: Web tradicionales o SPA

La siguiente tabla resume algunos de los factores básicos a tener en cuenta al elegir entre una aplicación web tradicional y un SPA.

  | **Factor de** | **Aplicación Web tradicional** | **Aplicación de una sola página** |
  |---|---|---|
  | Familiaridad de equipo necesarias con JavaScript o TypeScript | **Mínimo** | **Obligatorio** |
  | Compatibilidad con exploradores sin secuencias de comandos | **Compatible** | **No se admite** |
  | Comportamiento de la aplicación de cliente mínima | **Adecuadas** | **Excesivos** |
  | Requisitos de la interfaz de usuario amplias y complejas | **Limitado** | **Adecuadas** |

>[!div class="step-by-step"]
[Anterior] (moderno-web-aplicaciones-characteristics.md) [siguiente](architectural-principles.md)
