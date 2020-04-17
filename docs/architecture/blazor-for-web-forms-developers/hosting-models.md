---
title: Blazor app hosting modelos
description: Aprenda las diferentes formas de hospedar una aplicación Blazor, incluso en el explorador en WebAssembly o en el servidor.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 77a022b01efba01038790c9601ea03f315a28fdf
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607937"
---
# <a name="blazor-app-hosting-models"></a>Blazor app hosting modelos

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Las aplicaciones Blazor se pueden hospedar en IIS al igual que ASP.NET aplicaciones de formularios Web Forms. Las aplicaciones de Blazor también se pueden hospedar de una de las siguientes maneras:

- El lado del cliente en el explorador en WebAssembly.
- Servidor en una aplicación ASP.NET Core.

## <a name="blazor-webassembly-apps"></a>Aplicaciones Blazor WebAssembly

Las aplicaciones Blazor WebAssembly se ejecutan directamente en el explorador en un tiempo de ejecución de .NET basado en WebAssembly. Las aplicaciones Blazor WebAssembly funcionan de forma similar a los marcos de JavaScript front-end como Angular o React. Sin embargo, en lugar de escribir JavaScript, escriba C. El tiempo de ejecución de .NET se descarga con la aplicación junto con el ensamblado de la aplicación y las dependencias necesarias. No se requieren plugins o extensiones del navegador.

Los ensamblados descargados son ensamblados normales de .NET, como usaría en cualquier otra aplicación .NET. Dado que el tiempo de ejecución admite .NET Standard, puede usar bibliotecas de .NET Standard existentes con la aplicación Blazor WebAssembly. Sin embargo, estos ensamblados se seguirán ejecutando en el entorno limitado de seguridad del explorador. Algunas funciones <xref:System.PlatformNotSupportedException>pueden producir un , como intentar acceder al sistema de archivos o abrir conexiones de red arbitrarias.

Cuando se carga la aplicación, el tiempo de ejecución de .NET se inicia y apunta al ensamblado de la aplicación. Se ejecuta la lógica de inicio de la aplicación y se representan los componentes raíz. Blazor calcula las actualizaciones de la interfaz de usuario en función de la salida representada de los componentes. A continuación, se aplican las actualizaciones DE DOM.

![WebAssembly de Blazor](media/hosting-models/blazor-webassembly.png)

Las aplicaciones Blazor WebAssembly se ejecutan puramente en el lado del cliente. Estas aplicaciones se pueden implementar en soluciones de hospedaje de sitios estáticos como Páginas de GitHub o Hosting de sitios web estáticos de Azure. .NET no es necesario en el servidor en absoluto. La vinculación profunda a partes de la aplicación normalmente requiere una solución de enrutamiento en el servidor. La solución de enrutamiento redirige las solicitudes a la raíz de la aplicación. Por ejemplo, esta redirección se puede controlar mediante reglas de reescritura de direcciones URL en IIS.

Para obtener todas las ventajas de Blazor y el desarrollo web de .NET de pila completa, hospede la aplicación Blazor WebAssembly con ASP.NET Core. Mediante el uso de .NET tanto en el cliente como en el servidor, puede compartir fácilmente código y compilar la aplicación mediante un conjunto coherente de lenguajes, marcos y herramientas. Blazor proporciona plantillas convenientes para configurar una solución que contiene una aplicación Blazor WebAssembly y un proyecto host ASP.NET Core. Cuando se compila la solución, los archivos estáticos compilados de la aplicación Blazor se hospedan en la aplicación ASP.NET Core con enrutamiento de reserva ya configurado.

## <a name="blazor-server-apps"></a>Aplicaciones de Blazor Server

Recuerde de la discusión de la [arquitectura Blazor](architecture-comparison.md#blazor) que los componentes de Blazor representan su salida a una abstracción intermedia llamada `RenderTree`un archivo . A continuación, el marco blazor compara lo que se representó con lo que se representó anteriormente. Las diferencias se aplican al DOM. Los componentes blazor se desacoplan de cómo se aplica su salida renderizada. Por lo tanto, los propios componentes no tienen que ejecutarse en el mismo proceso que el proceso de actualización de la interfaz de usuario. De hecho, ni siquiera tienen que funcionar en la misma máquina.

En las aplicaciones de Blazor Server, los componentes se ejecutan en el servidor en lugar del lado cliente en el explorador. Los eventos de interfaz de usuario que se producen en el explorador se envían al servidor a través de una conexión en tiempo real. Los eventos se distribuyen a las instancias de componente correctas. Los componentes se representan y la diferencia de interfaz de usuario calculada se serializa y se envía al explorador donde se aplica al DOM.

![Servidor Blazor](media/hosting-models/blazor-server.png)

El modelo de hospedaje de Blazor Server puede sonar <xref:System.Web.UI.UpdatePanel> familiar si ha utilizado ASP.NET AJAX y el control. El `UpdatePanel` control controla la aplicación de actualizaciones parciales de página en respuesta a eventos de desencadenador en la página. Cuando se `UpdatePanel` desencadena, las solicitudes de una actualización parcial y, a continuación, la aplica sin necesidad de actualizar la página. El estado de la `ViewState`interfaz de usuario se administra mediante . Las aplicaciones de Blazor Server son ligeramente diferentes en que la aplicación requiere una conexión activa con el cliente. Además, todo el estado de la interfaz de usuario se mantiene en el servidor. Aparte de esas diferencias, los dos modelos son conceptualmente similares.

## <a name="how-to-choose-the-right-blazor-hosting-model"></a>Cómo elegir el modelo de alojamiento Blazor adecuado

Como se describe en los documentos del modelo de [alojamiento blazor](/aspnet/core/blazor/hosting-models), los diferentes modelos de alojamiento Blazor tienen diferentes compensaciones.

El modelo de alojamiento Blazor WebAssembly tiene las siguientes ventajas:

- No hay ninguna dependencia del lado servidor de .NET. La aplicación está funcionando completamente después de descargar en el cliente.
- Los recursos y capacidades del cliente se aprovechan al máximo.
- El trabajo se descarga del servidor al cliente.
- No es necesario un servidor web ASP.NET Core para hospedar la aplicación. Los escenarios de implementación sin servidor son posibles (por ejemplo, servir la aplicación desde una red CDN).

Las desventajas del modelo de alojamiento Blazor WebAssembly son:

- Las capacidades del explorador restringen la aplicación.
- Se requiere hardware y software de cliente capaz (por ejemplo, compatibilidad con WebAssembly).
- El tamaño de descarga es mayor y las aplicaciones tardan más en cargarse.
- La compatibilidad con el tiempo de ejecución y las herramientas de .NET es menos madura. Por ejemplo, hay limitaciones en la compatibilidad y depuración de [.NET Standard.](../../standard/net-standard.md)

Por el contrario, el modelo de alojamiento de Blazor Server ofrece las siguientes ventajas:

- El tamaño de descarga es mucho más pequeño que una aplicación del lado cliente, y la aplicación se carga mucho más rápido.
- La aplicación aprovecha al máximo las capacidades del servidor, incluido el uso de cualquier API compatible con .NET Core.
- .NET Core en el servidor se usa para ejecutar la aplicación, por lo que las herramientas de .NET existentes, como la depuración, funcionan según lo esperado.
- Se admiten clientes ligeros. Por ejemplo, las aplicaciones del lado servidor funcionan con exploradores que no admiten WebAssembly y en dispositivos con recursos limitados.
- La base de código de la aplicación en .NET/C, incluido el código de componente de la aplicación, no se sirve a los clientes.

Las desventajas del modelo de alojamiento de Blazor Server son:

- Mayor latencia de la interfaz de usuario. Cada interacción del usuario implica un salto de red.
- No hay soporte fuera de línea. Si se produce un error en la conexión de cliente, la aplicación deja de funcionar.
- La escalabilidad es un reto para las aplicaciones con muchos usuarios. El servidor debe administrar varias conexiones de cliente y controlar el estado del cliente.
- Se requiere un servidor ASP.NET Core para servir la aplicación. Los escenarios de implementación sin servidor no son posibles. Por ejemplo, no puede servir la aplicación desde una red CDN.

La lista anterior de compensaciones puede ser intimidante, pero el modelo de hospedaje se puede cambiar más adelante. Independientemente del modelo de alojamiento de Blazor seleccionado, el modelo de componente es *el mismo*. En principio, los mismos componentes se pueden utilizar con cualquiera de los modelos de hospedaje. El código de la aplicación no cambia; sin embargo, es una buena práctica introducir abstracciones para que sus componentes permanezcan hospedando independientemente del modelo. Las abstracciones permiten que la aplicación adopte más fácilmente un modelo de hospedaje diferente.

## <a name="deploy-your-app"></a>Implementación de la aplicación

ASP.NET aplicaciones de formularios Web Forms normalmente se hospedan en IIS en un equipo o clúster de Windows Server. Las aplicaciones de Blazor también pueden:

- Hospedarse en IIS, ya sea como archivos estáticos o como una aplicación ASP.NET Core.
- Aproveche ASP.NET flexibilidad de Core para hospedarse en varias plataformas e infraestructuras de servidores. Por ejemplo, puede alojar una aplicación Blazor utilizando [Nginx](/aspnet/core/host-and-deploy/linux-nginx) o [Apache](/aspnet/core/host-and-deploy/linux-apache) en Linux. Para obtener más información acerca de cómo publicar e implementar aplicaciones blazor, consulte la documentación de [blazor Hosting e implementación.](/aspnet/core/host-and-deploy/blazor/)

En la siguiente sección, veremos cómo se configuran los proyectos para las aplicaciones Blazor WebAssembly y Blazor Server.

>[!div class="step-by-step"]
>[Anterior](architecture-comparison.md)
>[Siguiente](project-structure.md)
