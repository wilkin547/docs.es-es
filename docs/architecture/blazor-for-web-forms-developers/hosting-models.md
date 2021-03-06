---
title: Blazor modelos de hospedaje de aplicaciones
description: Obtenga información sobre las distintas formas de hospedar una Blazor aplicación, incluida en el explorador en WebAssembly o en el servidor.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- WebAssembly
ms.date: 11/20/2020
ms.openlocfilehash: 18258c54cffdc538ddd11ec1393639216f86f85a
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255462"
---
# <a name="blazor-app-hosting-models"></a>Blazor modelos de hospedaje de aplicaciones

Blazor las aplicaciones se pueden hospedar de una de las siguientes maneras:

- En el lado cliente en el explorador de WebAssembly .
- Del lado servidor en una aplicación ASP.NET Core.

## <a name="blazor-webassembly-apps"></a>BlazorWebAssemblyaplicaciones de

BlazorWebAssemblylas aplicaciones se ejecutan directamente en el explorador en un entorno de WebAssembly tiempo de ejecución .net basado en. Blazorlas WebAssembly aplicaciones funcionan de una manera similar a los marcos de trabajo de JavaScript de front-end, como angular o reAct. Sin embargo, en lugar de escribir JavaScript, escriba C#. El tiempo de ejecución de .NET se descarga con la aplicación junto con el ensamblado de la aplicación y las dependencias necesarias. No se requiere ningún complemento o extensión de explorador.

Los ensamblados descargados son ensamblados .NET normales, como se usaría en cualquier otra aplicación de .NET. Dado que el tiempo de ejecución admite .NET Standard, puede usar las bibliotecas de .NET Standard existentes con su Blazor WebAssembly aplicación. Sin embargo, estos ensamblados se seguirán ejecutando en el espacio aislado de seguridad del explorador. Algunas funciones pueden producir un <xref:System.PlatformNotSupportedException> , como intentar tener acceso al sistema de archivos o abrir conexiones de red arbitrarias.

Cuando se carga la aplicación, se inicia el tiempo de ejecución de .NET y apunta al ensamblado de la aplicación. La lógica de inicio de la aplicación se ejecuta y se representan los componentes raíz. Blazor calcula las actualizaciones de la interfaz de usuario basadas en la salida representada de los componentes. Después se aplican las actualizaciones del DOM.

![::: no-LOC (increíble):::::: no-LOC (webassembly):::](media/hosting-models/blazor-webassembly.png)

Blazorlas WebAssembly aplicaciones se ejecutan exclusivamente en el lado cliente. Estas aplicaciones pueden implementarse en soluciones de hospedaje de sitios estáticos, como páginas de GitHub o el hospedaje de sitios web estáticos de Azure. .NET no es necesario en el servidor. La vinculación profunda a partes de la aplicación normalmente requiere una solución de enrutamiento en el servidor. La solución de enrutamiento redirige las solicitudes a la raíz de la aplicación. Por ejemplo, esta redirección se puede controlar mediante reglas de reescritura de URL en IIS.

Para obtener todas las ventajas de Blazor y el desarrollo web de .net de pila completa, hospede su Blazor WebAssembly aplicación con ASP.net Core. Con .NET en el cliente y el servidor, puede compartir código fácilmente y compilar la aplicación con un conjunto coherente de lenguajes, marcos y herramientas. Blazor proporciona plantillas convenientes para configurar una solución que contiene una Blazor WebAssembly aplicación y un proyecto de host ASP.net Core. Cuando se compila la solución, los archivos estáticos compilados de la Blazor aplicación se hospedan en la aplicación ASP.net Core con el enrutamiento de reserva ya configurado.

## <a name="blazor-server-apps"></a>Blazor Aplicaciones de servidor

Recuerde en la descripción de la [ Blazor arquitectura](architecture-comparison.md#blazor) que Blazor los componentes representan su salida en una abstracción intermedia denominada `RenderTree` . BlazorA continuación, el marco de trabajo compara lo que se representó con lo que se representó previamente. Las diferencias se aplican al DOM. Blazor los componentes se desacoplan de la manera en que se aplica la salida representada. Por lo tanto, los propios componentes no tienen que ejecutarse en el mismo proceso que el proceso de actualización de la interfaz de usuario. De hecho, ni siquiera tienen que ejecutarse en el mismo equipo.

En las Blazor aplicaciones de servidor, los componentes se ejecutan en el servidor en lugar de en el lado cliente en el explorador. Los eventos de interfaz de usuario que se producen en el explorador se envían al servidor a través de una conexión en tiempo real. Los eventos se envían a las instancias de componente correctas. Los componentes se representan y la diferencia de IU calculada se serializa y se envía al explorador donde se aplica al DOM.

![::: no-LOC (increíble)::: Server](media/hosting-models/blazor-server.png)

El Blazor modelo de hospedaje del servidor puede resultar más familiar si ha usado ASP.NET AJAX y el <xref:System.Web.UI.UpdatePanel> control. El `UpdatePanel` control administra la aplicación de actualizaciones parciales de página en respuesta a eventos desencadenadores en la página. Cuando se desencadena, `UpdatePanel` solicita una actualización parcial y, a continuación, la aplica sin necesidad de actualizar la página. El estado de la interfaz de usuario se administra mediante `ViewState` . Blazor Las aplicaciones de servidor son ligeramente diferentes en que la aplicación requiere una conexión activa con el cliente. Además, todo el estado de la interfaz de usuario se mantiene en el servidor. Aparte de estas diferencias, los dos modelos son conceptualmente similares.

## <a name="how-to-choose-the-right-blazor-hosting-model"></a>Cómo elegir el modelo de Blazor hospedaje adecuado

Tal y como se describe en los [ Blazor documentos del modelo de hospedaje](/aspnet/core/blazor/hosting-models), los distintos modelos de Blazor Hospedaje tienen diferentes inconvenientes.

El Blazor WebAssembly modelo de hospedaje tiene las siguientes ventajas:

- No hay ninguna dependencia del lado servidor .NET. La aplicación funciona totalmente después de descargarla en el cliente.
- Los recursos y capacidades del cliente se aprovechan completamente.
- El trabajo se descarga del servidor al cliente.
- No es necesario un servidor web ASP.NET Core para hospedar la aplicación. Los escenarios de implementación sin servidor son posibles (por ejemplo, para servir a la aplicación desde una red CDN).

Las desventajas del Blazor WebAssembly modelo de hospedaje son:

- Las funcionalidades del explorador restringen la aplicación.
- Se requiere hardware y software de cliente compatible (por ejemplo, WebAssembly soporte técnico).
- El tamaño de descarga es mayor y las aplicaciones tardan más tiempo en cargarse.
- La compatibilidad con las herramientas y el tiempo de ejecución de .NET está menos desarrollada. Por ejemplo, existen limitaciones en la compatibilidad con [.net Standard](../../standard/net-standard.md) y la depuración.

Por el contrario, el Blazor modelo de hospedaje del servidor ofrece las siguientes ventajas:

- El tamaño de la descarga es mucho menor que el de una aplicación del lado cliente y la aplicación se carga mucho más rápido.
- La aplicación aprovecha al máximo las funcionalidades del servidor, incluido el uso de cualquier API compatible con .NET.
- .NET en el servidor se usa para ejecutar la aplicación, por lo que las herramientas de .NET existentes, como la depuración, funcionan según lo esperado.
- Se admiten clientes ligeros. Por ejemplo, las aplicaciones del lado servidor funcionan con los exploradores que no admiten WebAssembly y en los dispositivos con restricción de recursos.
- La base del código de la aplicación .NET/C#, incluido el código de componente de la aplicación, no se sirve a los clientes.

Las desventajas del Blazor modelo de hospedaje de servidor son:

- Mayor latencia de la interfaz de usuario. Cada interacción del usuario implica un salto de red.
- No hay soporte técnico sin conexión. Si se produce un error en la conexión del cliente, la aplicación deja de funcionar.
- En el caso de aplicaciones con muchos usuarios, la escalabilidad supone un reto. El servidor debe administrar varias conexiones de cliente y controlar el estado del cliente.
- Se necesita un servidor ASP.NET Core para atender la aplicación. No es posible realizar escenarios de implementación sin servidor. Por ejemplo, no puede dar servicio a la aplicación desde una red CDN.

La lista anterior de compensaciones puede estar intimidando, pero el modelo de hospedaje se puede cambiar más adelante. Independientemente del Blazor modelo de hospedaje seleccionado, el modelo de componentes es *el mismo*. En principio, se pueden usar los mismos componentes con cualquier modelo de hospedaje. El código de la aplicación no cambia. sin embargo, se recomienda introducir abstracciones para que los componentes sigan hospedando el modelo independiente. Las abstracciones permiten a la aplicación adoptar más fácilmente un modelo de hospedaje diferente.

## <a name="deploy-your-app"></a>Implementación de la aplicación

Las aplicaciones de formularios Web Forms ASP.NET normalmente se hospedan en IIS en un clúster o un equipo con Windows Server. Blazor las aplicaciones también pueden:

- Estar hospedado en IIS, ya sea como archivos estáticos o como una aplicación ASP.NET Core.
- Aproveche la flexibilidad de ASP.NET Core para hospedarse en varias plataformas e infraestructuras de servidores. Por ejemplo, puede hospedar una Blazor aplicación con [nginx](/aspnet/core/host-and-deploy/linux-nginx) o [Apache](/aspnet/core/host-and-deploy/linux-apache) en Linux. Para obtener más información sobre cómo publicar e implementar Blazor aplicaciones, consulte la Blazor documentación de [hospedaje e implementación](/aspnet/core/host-and-deploy/blazor/) .

En la siguiente sección, veremos cómo Blazor WebAssembly se configuran los proyectos de y las Blazor aplicaciones de servidor.

>[!div class="step-by-step"]
>[Anterior](architecture-comparison.md)
>[Siguiente](project-structure.md)
