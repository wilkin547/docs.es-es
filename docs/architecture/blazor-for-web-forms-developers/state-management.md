---
title: Administración de estado
description: Obtenga información sobre los distintos enfoques para administrar el estado en los formularios Web Forms de ASP.NET y el increíble.
author: csharpfritz
ms.author: jefritz
ms.date: 05/15/2020
ms.openlocfilehash: 2ca811f886c6a245ac16c2bd66a68ff16e5bfc44
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267729"
---
# <a name="state-management"></a>Administración de estado

La administración de Estados es un concepto clave de las aplicaciones de formularios Web Forms, que facilitan el estado de vista, el estado de la sesión, el estado de la aplicación y las características de postback. Estas características con estado de Framework ayudaron a ocultar la administración de Estados necesaria para una aplicación y permitir a los desarrolladores de aplicaciones centrarse en la entrega de su funcionalidad. Con ASP.NET Core y extraordinaria, algunas de estas características se han reubicado y algunas se han quitado por completo. En este capítulo se describe cómo mantener el estado y ofrecer la misma funcionalidad con las nuevas características de extraordinarias.

## <a name="request-state-management-with-viewstate"></a>Solicitar la administración de Estados con ViewState

Al hablar sobre la administración de Estados en una aplicación de formularios Web Forms, muchos desarrolladores se compensarán inmediatamente de ViewState. En los formularios Web Forms, ViewState administra el estado del contenido entre las solicitudes HTTP mediante el envío de un bloque de texto codificado grande hacia atrás y hacia delante al explorador. El campo ViewState podría saturarse con el contenido de una página que contiene muchos elementos, lo que puede llegar a tener un tamaño de varios megabytes.

Con un servidor más impresionante, la aplicación mantiene una conexión continua con el servidor. El estado de la aplicación, denominado *circuito*, se mantiene en la memoria del servidor mientras la conexión se considera activa. El estado solo se eliminará cuando el usuario navegue fuera de la aplicación o de una página determinada de la aplicación. Todos los miembros de los componentes activos están disponibles entre las interacciones con el servidor.

Hay varias ventajas de esta característica:

- El estado del componente está disponible fácilmente y no se vuelve a generar entre las interacciones.
- El estado no se transmite al explorador.

Sin embargo, hay algunas desventajas de la persistencia del estado del componente en memoria que debe tener en cuenta:

- Si el servidor se reinicia entre las solicitudes, el estado se pierde.
- La solución de equilibrio de carga del servidor Web de la aplicación debe incluir sesiones permanentes para asegurarse de que todas las solicitudes del mismo explorador vuelvan al mismo servidor. Si una solicitud va a un servidor diferente, se perderá el estado.
- La persistencia del estado del componente en el servidor puede provocar la presión de memoria en el servidor Web.

Por los motivos anteriores, no confíe solo en el estado del componente para que resida en memoria en el servidor. La aplicación también debe incluir algún almacén de datos de respaldo para los datos entre las solicitudes. Algunos ejemplos sencillos de esta estrategia son:

- En una aplicación de carro de la compra, conserve el contenido de los nuevos elementos agregados al carro en un registro de base de datos. Si se pierde el estado en el servidor, puede reconstituirlo a partir de los registros de la base de datos.
- En un formulario web de varias partes, los usuarios esperarán que la aplicación Recuerde valores entre cada solicitud. Escriba los datos entre cada una de las entradas del usuario en un almacén de datos para que se puedan capturar y ensamblar en la estructura de respuesta de formulario final cuando se complete el formulario de varias partes.

Para obtener más información sobre cómo administrar el estado en las aplicaciones de extraordinarias, consulte [ASP.net Core la administración de Estados de increíbles](/aspnet/core/blazor/state-management).

## <a name="maintain-state-with-session"></a>Mantener el estado con la sesión

Los desarrolladores de formularios Web Forms pueden mantener información sobre el usuario que actualmente actúa con el <xref:Microsoft.AspNetCore.Http.ISession?displayProperty=nameWithType> objeto de diccionario. Es bastante fácil agregar un objeto con una clave de cadena a la `Session` , y dicho objeto estará disponible en otro momento durante las interacciones del usuario con la aplicación. En un intento de eliminar la administración de la interacción con HTTP, el `Session` objeto hace que sea fácil mantener el estado.

La firma del objeto .NET Framework `Session` no es igual que la ASP.net Core `Session` objeto. Tenga en cuenta [la documentación de la nueva sesión de ASP.net Core](/dotnet/api/microsoft.aspnetcore.http.isession) antes de decidir si migrar y usar la nueva característica de estado de sesión.

La sesión está disponible en ASP.NET Core y en un servidor más rápido, pero no se recomienda su uso en favor del almacenamiento de datos en un repositorio de datos de forma adecuada. El estado de sesión tampoco es funcional si los visitantes rechazan el uso de cookies HTTP en la aplicación debido a problemas de privacidad.

La configuración de ASP.NET Core y el estado de sesión está disponible en el [artículo administración de la sesión y el estado en ASP.net Core](/aspnet/core/fundamentals/app-state#session-state).

## <a name="application-state"></a>Estado de la aplicación

El `Application` objeto en el marco de trabajo de formularios Web Forms proporciona un repositorio masivo de solicitudes cruzadas para interactuar con la configuración y el estado del ámbito de la aplicación. El estado de la aplicación era un lugar ideal para almacenar varias propiedades de configuración de la aplicación a las que se haría referencia en todas las solicitudes, independientemente del usuario que realiza la solicitud. El problema con el `Application` objeto era que los datos no se conservaban entre varios servidores. El estado del objeto de aplicación se perdió entre reinicios.

Al igual que con `Session` , se recomienda que los datos se muevan a una memoria auxiliar persistente a la que puedan tener acceso varias instancias de servidor. Si hay datos volátiles a los que desea poder tener acceso a través de solicitudes y usuarios, puede almacenarlos fácilmente en un servicio singleton que se puede insertar en componentes que requieran esta información o interacción.

La construcción de un objeto para mantener el estado de la aplicación y su consumo podría ser similar a la siguiente implementación:

```csharp
public class MyApplicationState
{
    public int VisitorCounter { get; private set; } = 0;

    public void IncrementCounter() => VisitorCounter += 1;
}
```

```csharp
app.AddSingleton<MyApplicationState>();
```

```razor
@inject MyApplicationState AppState

<label>Total Visitors: @AppState.VisitorCounter</label>
```

El `MyApplicationState` objeto se crea solo una vez en el servidor, y el valor `VisitorCounter` se captura y se genera en la etiqueta del componente. El `VisitorCounter` valor se debe conservar y recuperar de un almacén de datos de respaldo para la durabilidad y la escalabilidad.

## <a name="in-the-browser"></a>En el explorador

Los datos de la aplicación también se pueden almacenar en el lado cliente en el dispositivo del usuario para que esté disponible más adelante. Hay dos características del explorador que permiten la persistencia de los datos en diferentes ámbitos del explorador del usuario:

- `localStorage` -ámbito en el explorador completo del usuario. Si se vuelve a cargar la página, el explorador se cierra y se vuelve a abrir, o bien se abre otra pestaña con la misma dirección URL, el `localStorage` Explorador lo proporciona
- `sessionStorage` -ámbito de la pestaña del explorador actual del usuario. Si se vuelve a cargar la pestaña, el estado persiste. Sin embargo, si el usuario abre otra pestaña en la aplicación o cierra y vuelve a abrir el explorador, se pierde el estado.

Puede escribir código JavaScript personalizado para interactuar con estas características, o hay una serie de paquetes de NuGet que puede usar para proporcionar esta funcionalidad. Uno de estos paquetes es [Microsoft. AspNetCore. ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.ProtectedBrowserStorage).

Para obtener instrucciones sobre el uso de este paquete para interactuar con `localStorage` y `sessionStorage` , consulte el artículo sobre la [Administración de Estados de increíbles](/aspnet/core/blazor/state-management#protected-browser-storage-experimental-package) .

>[!div class="step-by-step"]
>[Anterior](pages-routing-layouts.md)
>[Siguiente](forms-validation.md)
