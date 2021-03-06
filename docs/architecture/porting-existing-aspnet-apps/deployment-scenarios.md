---
title: Escenarios de implementación al migrar a ASP.NET Core
description: Información general de los distintos enfoques de implementación que se pueden usar para migrar de ASP.NET a ASP.NET Core, permitiendo migraciones en paralelo y por fases.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 589acd8c66baacc3aef5833dfaa24e2dcc5c1ee5
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401773"
---
# <a name="deployment-scenarios-when-migrating-to-aspnet-core"></a>Escenarios de implementación al migrar a ASP.NET Core

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Las aplicaciones de ASP.NET MVC y Web API existentes se ejecutan en IIS y Windows. Las aplicaciones de gran tamaño pueden requerir un enfoque por fases o en paralelo al migrar a ASP.NET Core. En los capítulos anteriores, aprendió varias estrategias para migrar aplicaciones de gran .NET Framework a ASP.NET Core en fases. En este capítulo, verá cómo se pueden lograr distintos escenarios de implementación cuando se necesita mantener la aplicación original en producción durante la migración de partes de ella.

## <a name="split-a-large-web-app"></a>División de una aplicación web grande

Considere el escenario común de una aplicación web grande que actualmente se hospeda en IIS en un único sitio Web. Dentro de la aplicación de gran tamaño, la funcionalidad se segmenta en rutas y/o directorios diferentes. La aplicación es una combinación de vistas de MVC y puntos de conexión de API. Las rutas MVC incluyen muchas rutas de acceso diferentes en función de la funcionalidad y se inician desde la raíz de la aplicación con la `/{controller}/{action}/{id?}` plantilla de ruta estándar. Los puntos de conexión de la API siguen un patrón similar, pero se encuentran en una `/api` raíz.

Suponiendo que la tarea de portabilidad de la aplicación se divide de forma que la funcionalidad MVC o la funcionalidad de la API se migren a ASP.NET Core en primer lugar, ¿cómo seguirá funcionando sin problemas el sitio original con la nueva aplicación ASP.NET Core que se ejecuta en alguna otra parte? Los usuarios del sistema deben seguir viendo las mismas direcciones URL que antes de la migración, a menos que sea absolutamente necesario cambiarlos.

Afortunadamente, IIS es un servidor Web con muchas características y dos características que ha tenido durante algún tiempo son el módulo de [reescritura de direcciones URL y el enrutamiento de solicitudes de aplicaciones](/iis/extensions/url-rewrite-module/reverse-proxy-with-url-rewrite-v2-and-application-request-routing). Con estas características, IIS puede actuar como un [proxy inverso](/iis/extensions/url-rewrite-module/reverse-proxy-with-url-rewrite-v2-and-application-request-routing)y enrutar las solicitudes de cliente a la aplicación Web de back-end adecuada. Para configurar IIS como un proxy inverso, active la casilla **Habilitar Proxy** en la característica de enrutamiento de solicitud de aplicación y, a continuación, agregue una regla de reescritura de URL como esta:

```xml
<rule name="NetCoreProxy">
  <match url="(.*)> />
  <action type="Rewrite" url="http://servername/{R:1}" />
</rule>
```

Como proxy inverso, IIS puede enrutar el tráfico que coincide con determinados patrones a aplicaciones completamente independientes, potencialmente en servidores diferentes.

Con solo el módulo de reescritura de direcciones URL (quizás combinado con encabezados de host), IIS puede admitir fácilmente varios sitios web, cada uno de los cuales ejecutará versiones diferentes de .NET. Una aplicación Web de gran tamaño podría implementarse como una colección de sitios individuales, cada uno de los cuales responde a diferentes direcciones IP o encabezados de host, o como un único sitio web con una o más subaplicacións en él que responde a determinadas rutas de dirección URL (lo que no requiere reescritura de direcciones URL).

> [!IMPORTANT]
> Normalmente, los subdominios hacen referencia a la parte de un dominio que precede a los dos niveles superiores. Por ejemplo, en el dominio `api.contoso.com` , `api` es un subdominio del `contoso.com` dominio (que se compone del `contoso` nombre de dominio y el dominio de `.com` nivel superior o TLD). Las rutas de dirección URL hacen referencia a la parte de la dirección URL que sigue al nombre de dominio, empezando por `/` . La dirección URL `https://contoso.com/api` tiene una ruta de acceso de `/api` .

Existen ventajas y desventajas en el uso de los mismos subdominios (y dominios) o diferentes para hospedar una sola aplicación. Características como las cookies y la comunicación entre aplicaciones mediante mecanismos como [CORS](/aspnet/core/security/cors) pueden requerir más configuración para funcionar correctamente en las aplicaciones distribuidas. Sin embargo, las aplicaciones que usan subdominios diferentes pueden usar más fácilmente DNS para enrutar las solicitudes a destinos de red completamente diferentes, por lo que se pueden implementar más fácilmente en muchos servidores diferentes (virtuales o de otro tipo) sin necesidad de que IIS actúe como un proxy inverso.

En el ejemplo descrito anteriormente, supongamos que los puntos de conexión de la API se designan como la primera parte de la aplicación que se va a trasladar a ASP.NET Core. En este caso, se crea una nueva aplicación de ASP.NET Core y se hospeda en IIS como una *aplicación* web independiente en el *sitio* Web de ASP.NET MVC existente. Dado que se agregará como un elemento secundario del sitio web original y se denominará *API*, su ruta predeterminada ya no debe comenzar `api/` . Si se mantiene esto, se hará que coincida con las direcciones URL del formulario `/api/api/endpoint` .

En la figura 5-1 se muestra cómo aparece la aplicación de *api* ASP.net Core 2,1 en el administrador de IIS como parte del sitio *DotNetMvcApp* existente.

![Administrador de IIS que muestra la aplicación de API en .NET Framework sitio](./media/Figure5-1.png)

**Figura 5-1**. .NET Framework sitio con la aplicación .NET Core en IIS.

El sitio *DotNetMvcApp* se hospeda como una aplicación MVC 5 que se ejecuta en .NET Framework 4.7.2. Tiene su propio grupo de aplicaciones de IIS configurado en modo integrado y ejecutando .NET CLR versión 4.0.30319. La aplicación de *API* es una aplicación ASP.net Core que se ejecuta en .NET Framework 4.6.1 ( `net461` ). Se agregó a *DotNetMvcApp* como una nueva aplicación de IIS y se configuró para usar su propio grupo de aplicaciones. Su grupo de aplicaciones también se está ejecutando en modo integrado pero está configurado con una versión de .NET CLR de **sin código administrado** , ya que se ejecutará mediante el [módulo de ASP.net Core](/aspnet/core/host-and-deploy/aspnet-core-module?preserve-view=true&view=aspnetcore-2.1). La versión de la aplicación ASP.NET Core es solo un ejemplo. También se puede configurar para que se ejecute en .NET Core 3,1 o .NET 5,0. Sin embargo, en ese momento, ya no podrá tener como destino bibliotecas .NET Framework (consulte [elección de la versión correcta de .net Core).](choose-net-core-version.md)

Configurado de esta manera, el único cambio que se debe realizar para que las API de la aplicación ASP.NET Core se enruten correctamente es cambiar su plantilla de ruta predeterminada de `[Route("[api/controller]")]` a `[Route("[controller]")]` .

Como alternativa, la aplicación ASP.NET Core puede ser otro sitio web de nivel superior en IIS. En este caso, puede configurar el sitio original para que use una regla de reescritura (con [reescritura de URL](https://www.iis.net/downloads/microsoft/url-rewrite)) que se redirigirá a la otra aplicación si la ruta de acceso comienza con `/api` . La aplicación ASP.NET Core puede usar un encabezado de host diferente para su ruta, de modo que no esté en conflicto con la aplicación principal, pero puede seguir respondiendo a las solicitudes mediante rutas basadas en la raíz.

Por ejemplo, la misma aplicación ASP.NET Core que se usa en la figura 5-1 se puede implementar en otra carpeta configurada como un sitio web de IIS. El sitio debe usar un grupo de aplicaciones configurado igual que antes, **sin código administrado**. Configure los enlaces para que respondan a un nombre de host único en el servidor, como `api.contoso.com` . Para configurar la reescritura de direcciones URL para reescribir solicitudes que coincidan `/api` , basta con agregar una nueva regla de entrada en el nivel de servidor IIS (o sitio individual). Coincide con el patrón `^/api(.*)` y especifica un tipo de acción `Rewrite` y una dirección URL de reescritura de `api.contoso.com/{R:1}` . La combinación de using `(.*)` en el patrón de coincidencia y `{R:1}` en la dirección URL de reescritura garantizará que el resto de la ruta de acceso se usa con la nueva dirección URL. Una vez hecho esto, los sitios independientes en el mismo servidor IIS pueden coexistir en la ejecución de versiones independientes de .NET, pero se pueden hacer que aparezcan en Internet como una aplicación Web. En la figura 5-2 se muestra la regla de reescritura tal como está configurada en IIS con el sitio web independiente.

![Administrador de IIS que muestra la regla de reescritura de direcciones URL para enrutar las solicitudes de subcarpetas a un sitio web independiente](./media/Figure5-2.png)

**Figura 5-2**. Vuelva a escribir la regla para volver a escribir las solicitudes de subcarpeta en otro sitio Web.

Si su aplicación requiere un inicio de sesión único entre diferentes sitios o aplicaciones en IIS, consulte la documentación sobre [Cómo compartir cookies de autenticación entre aplicaciones de ASP.net](/aspnet/core/host-and-deploy/iis/) para obtener instrucciones detalladas sobre cómo admitir este escenario.

## <a name="summary"></a>Resumen

Un enfoque común para portar aplicaciones de gran tamaño de .NET Framework a ASP.NET Core es elegir partes individuales de la aplicación para migrar una por una. A medida que se portan todos los elementos de la aplicación, toda la aplicación permanece en ejecución y se puede usar, y algunas partes del mismo se ejecutan en su configuración original y en otras que se ejecutan en alguna versión de .NET Core. Al seguir este enfoque, se puede realizar una migración de aplicaciones de gran tamaño de forma incremental. Este enfoque da como resultado la limitación del riesgo al proporcionar comentarios más rápidos y reducir el área expuesta total implicada en las pruebas. También permite la obtención más rápida de las ventajas de .NET Core, como el aumento del rendimiento. Aunque ya no es necesario que las aplicaciones de ASP.NET Core se hospeden en IIS, IIS sigue siendo un servidor web muy flexible y eficaz que puede configurarse para admitir una variedad de escenarios de hospedaje que impliquen tanto aplicaciones .NET Framework como ASP.NET Core en la misma instancia de IIS o incluso hospedadas en servidores diferentes.

## <a name="references"></a>Referencias

- [Hospedaje de ASP.NET Core en Windows con IIS](/aspnet/core/host-and-deploy/iis/)
- [Módulo de reescritura de URL y enrutamiento de solicitud de aplicación](/iis/extensions/url-rewrite-module/reverse-proxy-with-url-rewrite-v2-and-application-request-routing)
- [Reescritura de URL](https://www.iis.net/downloads/microsoft/url-rewrite)
- [Módulo ASP.NET Core](/aspnet/core/host-and-deploy/aspnet-core-module?preserve-view=true&view=aspnetcore-2.1)
- [Compartir cookies de autenticación entre aplicaciones ASP.NET](/aspnet/core/host-and-deploy/iis/)
- [Ejemplos usados en esta sección](https://github.com/ardalis/MigrateDotNetWithIIS)

>[!div class="step-by-step"]
>[Anterior](more-migration-scenarios.md)
>[Siguiente](summary.md)
