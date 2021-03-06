---
title: Estrategias para migrar con la ejecución en producción
description: Es posible que no se tenable migrar una aplicación grande desde ASP.NET MVC a ASP.NET Core todas a la vez. Aprenda algunas estrategias para migrar una aplicación a ASP.NET Core mientras se mantiene en ejecución y en producción para los usuarios existentes.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 4910984cb281139493aa5424809ba3eedab776e9
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401692"
---
# <a name="strategies-for-migrating-while-running-in-production"></a>Estrategias para migrar con la ejecución en producción

Muchos equipos tienen .NET Framework aplicaciones que planean migrar a .NET Core, pero la aplicación es tan grande que la migración requiere una cantidad de tiempo considerable para completarse. La aplicación original debe vivir mientras la migración se realiza por parte. Debe haber una manera de que las versiones antiguas y nuevas de la aplicación funcionen juntas en paralelo, o para que la versión anterior se migre en contexto, al menos parte del proceso, sin interrumpirla. Los equipos pueden emplear muchas estrategias distintas para admitir estos objetivos.

## <a name="refactor-the-net-framework-solution"></a>Refactorizar la solución .NET Framework

Un buen punto de partida si tiene previsto migrar una aplicación .NET Framework a .NET Core es refactorizarla para que funcione mejor con .NET Core. Esto significa actualizar bibliotecas de clases individuales a .NET Standard de destino y mover la lógica de sus proyectos de MVC de ASP.NET y a estas bibliotecas de clases. Cualquier código que tenga en .NET Standard bibliotecas debe moverse de .NET Framework a .NET Core.

Al refactorizar, asegúrese de seguir los buenos aspectos básicos de refactorización. Por ejemplo, cree pruebas que comprueben lo que hace el sistema antes de iniciar la refactorización. Ejecute estas pruebas cuando haya terminado de confirmar que no ha cambiado el comportamiento del sistema. Es posible que tenga que agregar pruebas de caracterización al sistema si aún no tiene un buen conjunto de pruebas automatizadas de las que puede confiar.

## <a name="extract-front-end-assets-to-a-cdn"></a>Extraer recursos de front-end a una red CDN

Si las aplicaciones .NET Framework incluyen muchos recursos estáticos, como scripts, archivos CSS o imágenes, es posible que pueda migrarlos a una red CDN independiente. A continuación, actualice la aplicación existente para que haga referencia a los vínculos de la red CDN para estos recursos. Al migrar la aplicación a .NET Core, estos archivos estáticos no formarán parte de la migración y simplemente seguirá haciendo referencia a ellos desde la red CDN en la aplicación ASP.NET Core.

## <a name="extract-and-migrate-individual-microservices"></a>Extraer y migrar microservicios individuales

Es posible que las aplicaciones de gran .NET Framework ya consten de sistemas front-end independientes que se pueden migrar de forma individual. O bien, pueden ser candidatas para la migración a una arquitectura de microservicios, con algunas partes de las aplicaciones de ASP.NET MVC existentes que se extraen en nuevas implementaciones de microservicios de ASP.NET Core. Puede obtener más información sobre los microservicios en el libro electrónico asociado, [microservicios de .net: arquitectura para aplicaciones .net en contenedor](https://aka.ms/microservicesebook).

Por ejemplo, la aplicación existente podría tener un conjunto de características que usa relacionado con el registro y el inicio de sesión de usuario. Se pueden migrar a un microservicio independiente, que podría compilarse e implementarse mediante ASP.NET Core y, a continuación, integrarse en la aplicación de .NET Framework heredada. A continuación, la aplicación podría tener algunas páginas dedicadas a realizar el seguimiento del carro de la compra del usuario individual. Estas páginas también se podrían extraer en su propio microservicio independiente y volver a integrarse en la aplicación existente. De esta manera, la aplicación de .NET Framework original continúa ejecutándose en producción, pero con más y más características procedentes de microservicios de .NET Core modernizados.

## <a name="deploy-multiple-versions-of-the-app-side-by-side-in-iis"></a>Implementar varias versiones de la aplicación en paralelo en IIS

Mediante una combinación de encabezados y redirecciones de host, se puede configurar una aplicación ASP.NET MVC existente para que se ejecute en paralelo con una aplicación ASP.NET Core en el mismo servidor IIS. Como los elementos de funcionalidad, como los controladores individuales, se trasladan a ASP.NET Core, sus rutas y direcciones URL se asignan en IIS para tener como destino el ASP.NET Core sitio web o la subaplicación (no se admiten los directorios virtuales de IIS con ASP.NET Core aplicaciones). Se puede hospedar una aplicación ASP.NET Core como una subaplicación IIS. La ruta de acceso de la subaplicación se convierte en parte de la dirección URL de la aplicación raíz.

## <a name="apply-the-strangler-pattern"></a>Aplicar el patrón STRANGLER

Las aplicaciones grandes de ASP.NET MVC se pueden reemplazar gradualmente por una nueva ASP.NET Core aplicación mediante la migración incremental de partes de la funcionalidad. Un enfoque a esto se denomina [patrón STRANGLER](/azure/architecture/patterns/strangler), denominado para STRANGLER Vines que Strangle y que finalmente anulan árboles. Este enfoque se basa en la primera implementación de una capa de fachada en la parte superior de la solución existente. Esta fachada debe compilarse con el nuevo enfoque del problema o con una solución de uso como, por ejemplo, una puerta de enlace de API.

Una vez que la fachada está en su lugar, puede redirigirla a una nueva ASP.NET Core aplicación. Al trasladar más la aplicación de .NET Framework original a .NET Core, sigue actualizando la capa de fachada en consecuencia, enviando más de la funcionalidad total de façade's al nuevo sistema. En la figura 3-5 se muestra la progresión del patrón STRANGLER a lo largo del tiempo.

## <a name="multi-targeting-approaches"></a>Enfoques de compatibilidad con múltiples versiones

Las aplicaciones de gran tamaño que tienen como destino .NET Framework se pueden migrar a ASP.NET Core con el tiempo mediante la compatibilidad con múltiples versiones y rutas de acceso de código independientes para cada marco. Por ejemplo, el código que se debe ejecutar en ambos entornos podría modificarse con directivas de [preprocesador `#if` ](../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) para implementar una funcionalidad diferente o usar diferentes dependencias cuando se ejecuten en .NET Framework frente a .net Core. Otra opción consiste en modificar los archivos de proyecto para incluir diferentes conjuntos de archivos en función de la plataforma de destino. Los archivos de proyecto pueden usar diferentes patrones de comodines, como `*.core.cs` , para incluir diferentes conjuntos de archivos de código fuente en función del marco de destino.

Estas técnicas permiten que se mantenga un solo código base común mientras se agrega una nueva funcionalidad y (parte de) la aplicación se transporta para usar .NET Core.

![Figura 3-5](media/Figure3-5.png)

**Figura 3-5.** Patrón STRANGLER a lo largo del tiempo.

Finalmente, la capa de fachada completa corresponde a la nueva implementación moderna. En este momento, se pueden retirar tanto el sistema heredado como la capa de caras.

## <a name="summary"></a>Resumen

Con frecuencia, las aplicaciones de API de web y MVC de gran tamaño de ASP.NET no se trasladarán a una sola vez, sino ASP.NET Core que se migrarán de forma incremental a lo largo del tiempo. En esta sección se ofrecen varias estrategias para realizar esta migración incremental. Elija el que mejor se adapte a su organización y aplicación.

## <a name="references"></a>Referencias

- [Microservicios de .NET: arquitectura para aplicaciones .NET en contenedor](https://aka.ms/microservicesebook)
- [Aplicación de microservicios de referencia de eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers)
- [Hospedaje de ASP.NET Core en Windows con IIS](/aspnet/core/host-and-deploy/iis/)
- [Patrón Strangler](/azure/architecture/patterns/strangler)

>[!div class="step-by-step"]
>[Anterior](understand-update-dependencies.md)
>[Siguiente](example-migration-eshop.md)
