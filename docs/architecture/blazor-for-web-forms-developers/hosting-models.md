---
title: Modelos de hospedaje de aplicaciones increíbles
description: Obtenga información sobre las distintas formas de hospedar una aplicación increíblemente, incluida en el explorador en webassembly o en el servidor.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 5bf55fa686691acc25508d3d9a6dfaf8aca321ca
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841952"
---
# <a name="blazor-app-hosting-models"></a>Modelos de hospedaje de aplicaciones increíbles

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Las aplicaciones increíbles se pueden hospedar en IIS, al igual que las aplicaciones de formularios Web Forms de ASP.NET. Las aplicaciones increíbles también se pueden hospedar de una de las siguientes maneras:

- Del lado cliente en el explorador en webassembly.
- Del lado servidor en una aplicación ASP.NET Core.

## <a name="blazor-webassembly-apps"></a>Aplicaciones webassembly increíblemente

Las aplicaciones de webassembly extraordinarias se ejecutan directamente en el explorador en un entorno de tiempo de ejecución .NET basado en webassembly. Las aplicaciones de webassembly increíbles funcionan de manera similar a los marcos de trabajo de JavaScript de front-end, como angular o reAct. Sin embargo, en lugar de escribir JavaScript, C#escriba. El tiempo de ejecución de .NET se descarga con la aplicación junto con el ensamblado de la aplicación y las dependencias necesarias. No se requiere ningún complemento o extensión de explorador.

Los ensamblados descargados son ensamblados .NET normales, como se usaría en cualquier otra aplicación de .NET. Dado que el tiempo de ejecución admite .NET Standard, puede usar las bibliotecas de .NET Standard existentes con la aplicación webassembly más brillante. Sin embargo, estos ensamblados se seguirán ejecutando en el espacio aislado de seguridad del explorador. Algunas funciones pueden producir una <xref:System.PlatformNotSupportedException>, como intentar tener acceso al sistema de archivos o abrir conexiones de red arbitrarias.

Cuando se carga la aplicación, se inicia el tiempo de ejecución de .NET y apunta al ensamblado de la aplicación. La lógica de inicio de la aplicación se ejecuta y se representan los componentes raíz. El increíbles calcula las actualizaciones de la interfaz de usuario basadas en la salida representada de los componentes. Después se aplican las actualizaciones del DOM.

![WebAssembly de Blazor](media/hosting-models/blazor-webassembly.png)

Las aplicaciones de webassembly extraordinarias se ejecutan exclusivamente en el lado cliente. Estas aplicaciones pueden implementarse en soluciones de hospedaje de sitios estáticos, como páginas de GitHub o el hospedaje de sitios web estáticos de Azure. .NET no es necesario en el servidor. La vinculación profunda a partes de la aplicación normalmente requiere una solución de enrutamiento en el servidor. La solución de enrutamiento redirige las solicitudes a la raíz de la aplicación. Por ejemplo, esta redirección se puede controlar mediante reglas de reescritura de URL en IIS.

Para obtener todas las ventajas de un desarrollo web de .NET de pila completa y más rápido, hospede su aplicación de webassembler más brillante con ASP.NET Core. Con .NET en el cliente y el servidor, puede compartir código fácilmente y compilar la aplicación con un conjunto coherente de lenguajes, marcos y herramientas. Extraordinariamente proporciona plantillas útiles para configurar una solución que contenga una aplicación webassembly más ligera y un proyecto host ASP.NET Core. Cuando se compila la solución, los archivos estáticos compilados de la aplicación increíblemente se hospedan en la aplicación ASP.NET Core con enrutamiento de reserva ya configurado.

## <a name="blazor-server-apps"></a>Aplicaciones de servidor increíbles

Recuerde que la descripción de la [arquitectura](architecture-comparison.md#blazor) es más increíble que los componentes increíbles representan su salida en una abstracción intermedia denominada `RenderTree`. A continuación, el marco más rápido compara lo que se representó con lo que se representó previamente. Las diferencias se aplican al DOM. Los componentes increíbles se desacoplan de la manera en que se aplica la salida representada. Por lo tanto, los propios componentes no tienen que ejecutarse en el mismo proceso que el proceso de actualización de la interfaz de usuario. De hecho, ni siquiera tienen que ejecutarse en el mismo equipo.

En las aplicaciones de servidor increíbles, los componentes se ejecutan en el servidor en lugar de en el lado cliente en el explorador. Los eventos de interfaz de usuario que se producen en el explorador se envían al servidor a través de una conexión en tiempo real. Los eventos se envían a las instancias de componente correctas. Los componentes se representan y la diferencia de IU calculada se serializa y se envía al explorador donde se aplica al DOM.

![Servidor Blazor](media/hosting-models/blazor-server.png)

Es posible que el modelo de hospedaje del servidor más rápido le resulte familiar si ha usado ASP.NET AJAX y el control <xref:System.Web.UI.UpdatePanel>. El control `UpdatePanel` controla la aplicación de actualizaciones parciales de página en respuesta a eventos desencadenadores en la página. Cuando se desencadena, el `UpdatePanel` solicita una actualización parcial y, a continuación, la aplica sin necesidad de actualizar la página. El estado de la interfaz de usuario se administra mediante `ViewState`. Las aplicaciones de servidor increíbles son ligeramente diferentes en que la aplicación requiere una conexión activa con el cliente. Además, todo el estado de la interfaz de usuario se mantiene en el servidor. Aparte de estas diferencias, los dos modelos son conceptualmente similares.

## <a name="how-to-choose-the-right-blazor-hosting-model"></a>Cómo elegir el modelo de hospedaje increíblemente adecuado

Tal y como se describe en los [documentos del modelo de hospedaje de extraordinarias](https://docs.microsoft.com/aspnet/core/blazor/hosting-models#server-side), los diferentes modelos de hospedaje increíbles tienen diferentes compromisos.

El modelo de hospedaje de webassembly de extraordinarias tiene las siguientes ventajas:

- No hay ninguna dependencia de servidor .NET. La aplicación funciona totalmente después de descargarla en el cliente.
- Los recursos de cliente y las capacidades se aprovechan por completo.
- El trabajo se descarga del servidor al cliente.
- No es necesario un servidor Web ASP.NET Core para hospedar la aplicación. Los escenarios de implementación sin servidor son posibles (por ejemplo, para dar servicio a la aplicación desde una red CDN).

Las desventajas del modelo de hospedaje de webassembly de increíbles son:

- Las funcionalidades del explorador restringen la aplicación.
- Se requiere hardware y software de cliente compatible (por ejemplo, compatibilidad con webassembly).
- El tamaño de descarga es mayor y las aplicaciones tardan más tiempo en cargarse.
- La compatibilidad con las herramientas y el tiempo de ejecución de .NET es menos madura. Por ejemplo, existen limitaciones en la compatibilidad con [.net Standard](../../standard/net-standard.md) y la depuración.

Por el contrario, el modelo de hospedaje del servidor más rápido ofrece las siguientes ventajas:

- El tamaño de la descarga es mucho menor que el de una aplicación del lado cliente y la aplicación se carga mucho más rápido.
- La aplicación aprovecha al máximo las funcionalidades del servidor, incluido el uso de cualquier API compatible con .NET Core.
- .NET Core en el servidor se usa para ejecutar la aplicación, por lo que las herramientas de .NET existentes, como la depuración, funcionan según lo previsto.
- Se admiten clientes ligeros. Por ejemplo, las aplicaciones del lado servidor funcionan con los exploradores que no admiten webassembly y en los dispositivos con restricción de recursos.
- La base de .NET/C# Code de la aplicación, incluido el código de componente de la aplicación, no se sirve a los clientes.

Los inconvenientes para el modelo de hospedaje del servidor increíblemente bajo son:

- Mayor latencia de la interfaz de usuario. Cada interacción del usuario implica un salto de red.
- No hay compatibilidad sin conexión. Si se produce un error en la conexión de cliente, la aplicación deja de funcionar.
- La escalabilidad es desafiante para aplicaciones con muchos usuarios. El servidor debe administrar varias conexiones de cliente y controlar el estado del cliente.
- Se requiere un servidor ASP.NET Core para atender la aplicación. No es posible realizar escenarios de implementación sin servidor. Por ejemplo, no puede dar servicio a la aplicación desde una red CDN.

La lista anterior de compensaciones puede estar intimidando, pero el modelo de hospedaje se puede cambiar más adelante. Independientemente del modelo de hospedaje increíblemente seleccionado, el modelo de componentes es *el mismo*. En principio, se pueden usar los mismos componentes con cualquier modelo de hospedaje. El código de la aplicación no cambia. sin embargo, se recomienda introducir abstracciones para que los componentes sigan hospedando el modelo independiente. Las abstracciones permiten a la aplicación adoptar más fácilmente un modelo de hospedaje diferente.

## <a name="deploy-your-app"></a>Implementar la aplicación

Las aplicaciones de formularios Web Forms ASP.NET normalmente se hospedan en IIS en un clúster o un equipo con Windows Server. Las aplicaciones increíbles también pueden:

- Estar hospedado en IIS, ya sea como archivos estáticos o como una aplicación ASP.NET Core.
- Aproveche la flexibilidad de ASP.NET Core para hospedarse en varias plataformas e infraestructuras de servidores. Por ejemplo, puede hospedar una aplicación increíblemente con [nginx](/aspnet/core/host-and-deploy/linux-nginx) o [Apache](/aspnet/core/host-and-deploy/linux-apache) en Linux. Para obtener más información acerca de cómo publicar e implementar aplicaciones increíbles, consulte la documentación de [hospedaje y de implementación](/aspnet/core/host-and-deploy/blazor/) de increíbles.

En la siguiente sección, veremos cómo se configuran los proyectos de las aplicaciones de servidor de webassembler y increíbles.

>[!div class="step-by-step"]
>[Anterior](architecture-comparison.md)
>[Siguiente](project-structure.md)
