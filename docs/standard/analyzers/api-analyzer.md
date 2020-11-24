---
title: Analizador de API en .NET
description: Obtenga información sobre cómo el analizador de API de .NET puede ayudar a detectar problemas de compatibilidad de plataforma y de API en desuso.
author: oliag
ms.date: 02/20/2020
ms.openlocfilehash: 47ef2368692aee56ebd3db7803cbde7368d38049
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819609"
---
# <a name="net-api-analyzer"></a>Analizador de API en .NET

El analizador de API de .NET es un analizador Roslyn que detecta posibles riesgos de compatibilidad de API de C# en distintas plataformas y detecta llamadas a API en desuso. Puede ser útil para todos los programadores de C# en cualquier fase de desarrollo.

El analizador de API está disponible como un paquete NuGet [Microsoft.DotNet.Analyzers.Compatibility](https://www.nuget.org/packages/Microsoft.DotNet.Analyzers.Compatibility/). Tras hacer referencia a él en un proyecto, supervisa automáticamente el código e indica el uso de API problemático. También puede obtener sugerencias sobre posibles soluciones; para ello, haga clic en la bombilla. El menú desplegable incluye una opción para suprimir las advertencias.

> [!NOTE]
> El analizador de API de .NET aún está en versión preliminar.

## <a name="prerequisites"></a>Requisitos previos

- Visual Studio 2017 o Visual Studio para Mac (todas las versiones).

## <a name="discover-deprecated-apis"></a>Detección de API en desuso

### <a name="what-are-deprecated-apis"></a>¿Qué son las API en desuso?

La familia de .NET es un conjunto de productos de gran tamaño que se actualizan constantemente para satisfacer mejor las necesidades del cliente. Es natural dejar de utilizar algunas API y sustituirlas por otras nuevas. Se considera que una API está en desuso cuando existen alternativas mejores. Una manera de notificar que una API está en desuso y que no debe utilizarse consiste en marcarla con el atributo <xref:System.ObsoleteAttribute>. El inconveniente de este enfoque es que hay un único identificador de diagnóstico para todas las API en desuso (en C#, [CS0612](../../csharp/misc/cs0612.md)). Esto significa que:

- Es imposible dedicar documentos a cada caso.
- Es imposible suprimir determinadas categorías de advertencias. Puede suprimirlas todas o ninguna.
- Para informar a los usuarios de una nueva degradación, es necesario actualizar un paquete de destino o un ensamblado de referencia.

El analizador de API usa códigos de error específicos de API que empiezan por DE (que significa error de degradación), que permite controlar la visualización de advertencias individuales. Las API en desuso identificadas por el analizador se definen en el repositorio [dotnet/platform-compat](https://github.com/dotnet/platform-compat).

### <a name="add-the-api-analyzer-to-your-project"></a>Adición del analizador de API al proyecto

1. Abra Visual Studio.
2. Abra el proyecto en el que quiera ejecutar el analizador.
3. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**. (Esta opción también está disponible en el menú **Proyecto**).
4. En la pestaña Administrador de paquetes NuGet:
   1. Elija "nuget.org" como origen del paquete.
   2. Vaya a la pestaña **Examinar**.
   3. Seleccione **Incluir versión preliminar**.
   4. Busque **Microsoft.DotNet.Analyzers.Compatibility**.
   5. Seleccione ese paquete de la lista.
   6. Seleccione el botón **Instalar**.
   7. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

### <a name="use-the-api-analyzer"></a>Uso del analizador de API

Cuando una API en desuso, como <xref:System.Net.WebClient>, se utiliza en un código, el analizador de API la destaca con una línea ondulada de color verde. Si mantiene el puntero sobre la llamada API, se muestra una bombilla con información sobre la degradación de la API, como en el ejemplo siguiente:

![Captura de pantalla de WebClient API con una línea ondulada de color verde y una bombilla a la izquierda.](media/api-analyzer/green-squiggle.jpg)

La ventana **Lista de errores** contiene advertencias con un identificador exclusivo por cada API en desuso, como se muestra en el ejemplo siguiente (`DE004`):

![Captura de pantalla de la ventana Lista de errores en la que se muestra el identificador de la advertencia y su descripción.](media/api-analyzer/warnings-id-and-descriptions.jpg "Ventana Lista de errores con advertencias.")

Al hacer clic en el identificador, se le remite a una página web que contiene información detallada sobre la API en desuso y sugerencias sobre las API alternativas que pueden usarse.

Las advertencias pueden suprimirse si se hace clic con el botón derecho del ratón en el miembro resaltado y se selecciona **Suprimir \<diagnostic ID>** . Hay dos maneras de suprimir las advertencias:

- [localmente (en el origen)](#suppress-warnings-locally)
- [globalmente (en un archivo de supresión)](#suppress-warnings-globally); se trata de la opción recomendada

### <a name="suppress-warnings-locally"></a>Supresión de advertencias localmente

Para suprimir advertencias localmente, haga clic con el botón derecho en el miembro del que quiere suprimir las advertencias y luego seleccione **Acciones rápidas y refactorizaciones** > **Suprimir *Id. de diagnóstico*\<diagnostic ID>**  > **en origen**. La directiva del preprocesador de advertencias [#pragma](../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) se agrega al código fuente en el ámbito definido: ![Captura de pantalla encuadrada con la advertencia #pragma deshabilitada.](media/api-analyzer/suppress-in-source.jpg)

### <a name="suppress-warnings-globally"></a>Supresión de advertencias globalmente

Para suprimir advertencias globalmente, haga clic con el botón derecho en el miembro del que quiere suprimir las advertencias y luego seleccione **Acciones rápidas y refactorizaciones** > **Suprimir *Id. de diagnóstico*\<diagnostic ID>**  > **en archivo de supresión**.

![Captura de pantalla del menú contextual en la que se muestran opciones para suprimir una advertencia en Visual Studio.](media/api-analyzer/suppress-in-sup-file.jpg)

Se agrega un archivo *GlobalSuppressions.cs* al proyecto después de su primera supresión. Las nuevas supresiones globales se anexan a este archivo.

![Captura de pantalla del archivo GlobalSuppressions.cs en Explorador de soluciones.](media/api-analyzer/suppression-file.jpg)

La supresión global es el método recomendado para garantizar la coherencia del uso de API en los proyectos.

## <a name="discover-cross-platform-issues"></a>Detección de problemas multiplataforma

> [!NOTE]
> .NET 5.0 presenta el [analizador de compatibilidad de plataformas](platform-compat-analyzer.md) como sustituto de esta característica. El analizador de compatibilidad de plataformas se incluye en el SDK de .NET (no es necesario instalarlo por separado) y está activado de forma predeterminada.

De forma similar a las API en desuso, el analizador identifica todas las API que no son multiplataforma. Por ejemplo, <xref:System.Console.WindowWidth?displayProperty=nameWithType> funciona en Windows, pero no en Linux y macOS. El Id. de diagnóstico se muestra en la ventana **Lista de errores**. Puede suprimir dicha advertencia si hace clic con el botón derecho y selecciona **Acciones rápidas y refactorizaciones**. A diferencia de los casos de degradación donde tiene dos opciones (seguir usando el miembro en desuso y suprimir advertencias o no utilizarlo en absoluto), en este caso, si va a desarrollar el código solo para algunas plataformas, puede suprimir todas las advertencias para todas las demás plataformas en las que no pretende ejecutar el código. Para ello, solo tiene que editar el archivo de proyecto y agregar la propiedad `PlatformCompatIgnore` que enumera todas las plataformas que se deben ignorar. Los valores permitidos son: `Linux`, `macOS` y `Windows`.

```xml
<PropertyGroup>
    <PlatformCompatIgnore>Linux;macOS</PlatformCompatIgnore>
</PropertyGroup>
```

Si el código tiene como destino varias plataformas y desea beneficiarse de una API que no es compatible en algunas de ellas, puede proteger esa parte del código con una instrucción `if`:

```csharp
if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
{
     var w = Console.WindowWidth;
     // More code
}
```

También puede compilar de forma condicional pro sistema operativo/marco de destino, pero actualmente necesita hacerlo [manualmente](../frameworks.md#how-to-specify-a-target-framework).

## <a name="supported-diagnostics"></a>Diagnóstico admitido

Actualmente, el analizador controla los casos siguientes:

- Uso de una API de .NET Standard que genera <xref:System.PlatformNotSupportedException> (PC001).
- Uso de una API de .NET Standard que no está disponible en .NET Framework 4.6.1 (PC002).
- Uso de una API nativa que no existe en UWP (PC003).
- Uso de las API Delegate.BeginInvoke y EndInvoke (PC004).
- Uso de una API que está marcada como en desuso (DEXXXX).

## <a name="ci-machine"></a>Equipo de integración continua

Todos estos diagnósticos están disponibles no solo en el IDE, sino también en la línea de comandos como parte de la creación del proyecto, que incluye el servidor de integración continua.

## <a name="configuration"></a>Configuración

El usuario decide cómo se deben tratar los diagnósticos: como advertencias, errores, sugerencias o estar desactivados. Por ejemplo, como un arquitecto, puede decidir que los problemas de compatibilidad deben tratarse como errores y que las llamadas a algunas API en desuso generen advertencias, mientras que otras solo generan sugerencias. Puede configurar esto por separado por identificador de diagnóstico y por proyecto. Para ello, en el **Explorador de soluciones**, vaya al nodo **Dependencias** del proyecto. Expanda los nodos **Dependencias** > **Analizadores** > **Microsoft.DotNet.Analyzers.Compatibility**. Haga clic con el botón derecho en el identificador de diagnóstico, seleccione **Configurar gravedad del conjunto de reglas** y, después, elija la opción deseada.

![Captura de pantalla del Explorador de soluciones donde se muestran los diagnósticos y el cuadro de diálogo emergente con la gravedad del conjunto de reglas.](media/api-analyzer/disable-notifications.jpg)

## <a name="see-also"></a>Vea también

- Entrada de blog de [introducción al analizador de API](https://devblogs.microsoft.com/dotnet/introducing-api-analyzer/).
- Vídeo de demostración del [analizador de API](https://youtu.be/eeBEahYXGd0) de YouTube.
- [Analizador de compatibilidad de plataformas](platform-compat-analyzer.md)
