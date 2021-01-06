---
title: Migración de Windows 10
description: Profundice en las características de Windows 10 como el empaquetado y las islas XAML.
ms.date: 09/16/2019
ms.openlocfilehash: cd17088b086a32fd3bb37e617d3a1047acedde0e
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "97866672"
---
# <a name="windows-10-migration"></a>Migración de Windows 10

Tenga en cuenta la situación siguiente: tiene una aplicación de escritorio de trabajo desarrollada en Windows 7 días. Está usando la tecnología de WPF disponible en ese momento y funciona bien, pero tiene una interfaz de usuario y comportamientos obsoletos cuando se ejecuta en Windows 10. Es como cuando vea una película futurista como una matriz y verá neo con el dispositivo Nokia 8110. La película funciona bien después de 20 años, pero se beneficiaría de la modernización de un dispositivo.

Con el lanzamiento de Windows 10, Microsoft presentó muchas innovaciones para admitir escenarios como tabletas y dispositivos táctiles, y para proporcionar la mejor experiencia para los usuarios de un sistema operativo de Microsoft. Por ejemplo, puede:

- Inicie sesión con su esfera con Windows Hello.
- Use un lápiz para dibujar o escribir a mano texto que se reconozca y digitale automáticamente.
- Ejecute modelos de inteligencia artificial personalizados localmente basados en la nube con WinML.

Todas estas características están habilitadas para los desarrolladores de Windows a través de bibliotecas de Windows Runtime (WinRT). Puede aprovechar estas características en sus aplicaciones de escritorio existentes, ya que las bibliotecas se exponen también en el .NET Framework y .NET Core. Incluso puede modernizar la interfaz de usuario con el uso de islas XAML y mejorar los objetos visuales y el comportamiento de las aplicaciones de acuerdo con las horas.

Una cuestión importante que hay que tener en cuenta es que no es necesario abandonar .NET Framework tecnología para seguir esta ruta de modernización. Puede permanecer de forma segura y tener todas las ventajas de Windows 10 sin la presión de migrar a .NET Core. Por lo tanto, se obtiene la potencia y la flexibilidad para elegir la ruta de modernización.

## <a name="winrt-apis"></a>API de WinRT

Las API de WinRT son interfaces de programación de aplicaciones (API) bien estructuradas y orientadas a objetos que proporcionan a los desarrolladores de Windows 10 acceso a todo lo que el sistema operativo tiene que ofrecer. A través de las API de WinRT, puede integrar funcionalidades como notificaciones de envío, API de dispositivos, Microsoft Ink y WinML, entre otras en sus aplicaciones de escritorio.

En general, se puede llamar a las API de WinRT desde una aplicación de escritorio clásica. Sin embargo, dos áreas principales presentan una excepción a esta regla:

* API que requieren una identidad de paquete.
* API que requieren visualización como XAML o composición.

### <a name="universal-windows-platform-uwp-packages"></a>Paquetes de Plataforma universal de Windows (UWP)

#### <a name="application-package-identity"></a>Identidad de paquete de aplicación

Las aplicaciones UWP tienen un sistema de implementación en el que el sistema operativo administra la instalación y desinstalación de la aplicación. Esto requiere que la instalación sea declarativa, lo que significa que no se ejecuta ningún código de usuario durante la instalación. En su lugar, todo lo que la aplicación desea integrar con el sistema, como los protocolos, los tipos de archivo y las extensiones, se declara en el manifiesto de aplicación. En el momento de la implementación, la canalización de implementación configura esos puntos de integración. La única forma para que el sistema operativo administre toda esta funcionalidad y realice un seguimiento de ella es que cada "paquete" tenga una identidad, un identificador único para la aplicación.

Algunas API de WinRT requieren que esta identidad de paquete funcione según lo previsto. Sin embargo, las aplicaciones de escritorio clásicas como las aplicaciones nativas de C++ o .NET usan sistemas de implementación diferentes que no requieren una identidad de paquete. Si desea usar estas API de WinRT en la aplicación de escritorio, debe proporcionarles una identidad de paquete.

Una manera de proceder es crear un proyecto de empaquetado adicional. Dentro del proyecto de empaquetado, seleccione el proyecto de código fuente original y especifique la información de identidad que desea proporcionar.Si instala el paquete y ejecuta la aplicación instalada, obtendrá automáticamente una identificación habilitando el código para llamar a todas las API de WinRT que requieren identidad.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Package xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
         xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10">
    <Identity Name="YOUR-APP-GUID "
              Publisher="CN=YOUR COMPANY"
              Version="1.x.x.x" />
</Package>
```

Puede comprobar qué API necesitan una identidad de aplicación empaquetada si inspecciona si el tipo que contiene la API está marcado con el atributo [DualApiPartition](xref:Windows.Foundation.Metadata.DualApiPartitionAttribute) .Si es así, puede llamar a si desde una aplicación de escritorio tradicional desempaquetada. De lo contrario, debe convertir la aplicación de escritorio clásica en una UWP con la ayuda de un proyecto de empaquetado.

<https://docs.microsoft.com/windows/desktop/apiindex/uwp-apis-callable-from-a-classic-desktop-app>

#### <a name="benefits-of-packaging"></a>Ventajas del empaquetado

Además de tener acceso a estas API, obtendrá algunas ventajas adicionales mediante la creación de un paquete de aplicación de Windows para la aplicación de escritorio, entre los que se incluyen:

* **Implementación simplificada**. Las aplicaciones tienen una excelente experiencia de implementación, lo que garantiza que los usuarios puedan instalar una aplicación con confianza y actualizarla. Si un usuario decide desinstalar la aplicación, se quitará por completo y no se deja ningún seguimiento tras evitar el problema de la Rot de Windows.

* **Actualizaciones automáticas y licencias**. La aplicación puede participar en las herramientas integradas de licencias y actualizaciones automáticas de Microsoft Store. La actualización automática es un mecanismo muy confiable y eficaz, ya que solo se descargan las partes modificadas de los archivos.

* **Mayor alcance y monetización simplificada**. Quizás no sea su caso, pero si decide distribuir la aplicación a través del Microsoft Store llega a millones de usuarios de Windows 10.

* **Incorporación de características de UWP**. Puede agregar características de UWP al paquete de la aplicación a su propio ritmo.

#### <a name="prepare-for-packaging"></a>Preparar el empaquetado

Antes de empezar a empaquetar la aplicación de escritorio, hay algunos puntos que debe abordar antes de iniciar el proceso. La aplicación debe respetar cualquiera de las reglas y directivas de Microsoft Store y ejecutarse en el modelo de aplicación de UWP. Por ejemplo, tiene que ejecutarse en el .NET Framework 4.6.2 o posterior y las escrituras en el `HKEY_CURRENT_USER` subárbol del registro y las carpetas AppData se virtualizarán en una ubicación local de la aplicación específica del usuario.

El objetivo de diseño para empaquetar es separar el estado de la aplicación del estado del sistema y mantener la compatibilidad con otras aplicaciones. Windows 10 logra este objetivo colocando la aplicación dentro de un paquete de UWP. Detecta y redirige algunos cambios en el sistema de archivos y el registro en tiempo de ejecución para satisfacer la promesa de un comportamiento de instalación y desinstalación limpio y de confianza de una aplicación proporcionada por el empaquetado.

Los paquetes que crea para la aplicación de escritorio son aplicaciones de plena confianza que no están en un espacio aislado, aunque se aplica la virtualización ligera a la aplicación para escribir en `HKCU` y `AppData` . Esta virtualización les permite interactuar con otras aplicaciones de la misma manera que las aplicaciones de escritorio clásicas.

##### <a name="installation"></a>Instalación

Los paquetes de la aplicación se instalan en *% ProgramFiles% \\ WindowsApps \\ package_name*, con el archivo ejecutable titulado  `app_name.exe` . Cada carpeta de paquete contiene un manifiesto (llamado `AppxManifest.xml` ) que contiene un espacio de nombres XML especial para aplicaciones empaquetadas. Dentro de ese archivo de manifiesto hay un  `<EntryPoint>`   elemento, que hace referencia a la aplicación de plena confianza. Cuando se inicia la aplicación, no se ejecuta dentro de un contenedor de la aplicación, sino que se ejecuta como el usuario como lo haría normalmente.

Después de la implementación, el sistema operativo marca los archivos del paquete como de solo lectura y los bloquea completamente. Windows evita que las aplicaciones se inicien en caso de que se manipulen estos archivos.

##### <a name="file-system"></a>Sistema de archivos

El sistema operativo admite distintos niveles de operaciones del sistema de archivos para las aplicaciones de escritorio empaquetadas, en función de la ubicación de la carpeta.

Al intentar obtener acceso a la carpeta *AppData* del usuario, el sistema crea una ubicación privada por usuario y por aplicación en segundo plano. Esto crea la ilusión de que la aplicación empaquetada está editando la *AppData* real cuando realmente está modificando una copia privada. Al redireccionar las escrituras de este modo, el sistema puede realizar un seguimiento de todas las modificaciones de archivos que realiza la aplicación. A continuación, puede limpiar todos los archivos al desinstalar la reducción del sistema "rot" y proporcionar una mejor experiencia de eliminación de aplicaciones para el usuario.

##### <a name="registry"></a>Registro

Los paquetes de aplicaciones contienen un archivo Registry. dat, que actúa como el equivalente lógico de  `HKLM\Software`   en el registro real. En tiempo de ejecución, este Registro virtual combina el contenido de este subárbol en el subárbol del sistema nativo para proporcionar una vista especial de ambos.

Todas las escrituras se conservan durante la actualización del paquete y solo se eliminan cuando se desinstala la aplicación.

##### <a name="uninstallation"></a>Desinstalación

Cuando el usuario desinstala un paquete, se quitan todos los archivos y carpetas ubicados en  `C:\Program Files\WindowsApps\package_name` , así como las escrituras redirigidas a AppData o el registro que se capturaron durante el proceso.

Para obtener más información sobre cómo una aplicación empaquetada controla la instalación, el acceso a archivos, el registro y la desinstalación, vea <https://docs.microsoft.com/windows/msix/desktop/desktop-to-uwp-behind-the-scenes> .

Puede obtener una lista completa de los elementos que se deben comprobar <https://docs.microsoft.com/windows/msix/desktop/desktop-to-uwp-prepare> .

## <a name="how-to-add-winrt-apis-to-your-desktop-project"></a>Cómo agregar API de WinRT al proyecto de escritorio

En esta sección, puede encontrar un tutorial sobre cómo integrar las notificaciones del sistema en una aplicación de WPF existente. Aunque es sencilla desde la perspectiva del código, ayuda a ilustrar todo el proceso. Las notificaciones son una de las muchas API de WinRT disponibles que puede usar en la aplicación .NET. En este caso, la API requiere una identidad de paquete. Este proceso es más sencillo si las API no requieren la identidad del paquete.

Vamos a tomar una aplicación de ejemplo de WPF existente que lee archivos y muestra su contenido en la pantalla. El objetivo es mostrar una notificación del sistema cuando se inicia la aplicación.

![Captura de pantalla de la aplicación de ejemplo en ejecución](./media/windows-migration/sample-application.png)

En primer lugar, debe proteger el siguiente vínculo si la API de Windows 10 que usará requiere una identidad de paquete:

<https://docs.microsoft.com/windows/apps/desktop/modernize/desktop-to-uwp-supported-api>

Nuestro ejemplo usará la <xref:Windows.UI.Notifications.Notification?displayProperty=nameWithType> API que requiere una identidad empaquetada:

![Clase de notificación en la documentación de Microsoft](./media/windows-migration/notification-class-documentation.png)

Para acceder a la API de WinRT, agregue una referencia al `Microsoft.Windows.SDK.Contracts`   paquete de NuGet y este paquete hará la magia en segundo plano (vea los detalles en <https://blogs.windows.com/windowsdeveloper/2019/04/30/calling-windows-10-apis-from-a-desktop-application-just-got-easier/> ).

Ahora está preparado para empezar a agregar código.

Cree un `ShowToastNotification` método al que se llamará en el inicio de la aplicación. Solo se compila una notificación del sistema a partir de un patrón XML:

```csharp
private void ShowNotification(string title, string content, string image)
{
    string xmlString = $@"<toast><visual><binding template = 'ToastGeneric'><text>{title}</text><text>{content}</text><image src=>'{image}'</image></binding></visual></toast>";
    XmlDocument toastXml = new XmlDocument();
    toastXml.LoadXml(xmlString);
    ToastNotification toast = new ToastNotification(toastXml);
    ToastNotificationManager.CreateToastNotifier().Show(toast);
}
```

Aunque el proyecto se compila, hay errores porque la API de notificaciones requiere una identidad de paquete y no se ha proporcionado. Si agrega un proyecto de empaquetado de Windows a la solución, se solucionará el problema:

![Captura de pantalla del cuadro de diálogo Agregar nuevo proyecto en Visual Studio](./media/windows-migration/add-packaging-project.png)

Seleccione la versión mínima de Windows que desea admitir y la versión de destino. No todas las API de WinRT se admiten en todas las versiones de Windows 10. Cada actualización de Windows 10 agrega nuevas API que solo están disponibles en esta versión; la compatibilidad de nivel inferior no está disponible.

![Seleccionar la versión mínima de Windows](./media/windows-migration/select-versions.png)

El siguiente paso consiste en agregar la aplicación WPF al proyecto de empaquetado de Windows mediante la adición de una referencia de proyecto:

![Agregar una aplicación WPF al proyecto de empaquetado de Windows](./media/windows-migration/add-application.png)

![Administrador de referencias](./media/windows-migration/reference-manager.png)

Un proyecto de empaquetado de Windows puede empaquetar varias aplicaciones, por lo que debe establecer cuál es el punto de entrada:

![Establecer el punto de entrada](./media/windows-migration/set-entry-point.png)

El siguiente paso consiste en establecer el proyecto de WPF como proyecto de inicio en la configuración de la solución. Puede presionar F5 para compilar y compilar y ver los resultados.

![Aplicación de ejemplo que se ejecuta y muestra los resultados](./media/windows-migration/sample-app-result.png)

Vamos a generar el paquete para que pueda instalar la aplicación. Haga clic con el botón derecho en **tienda**  >  **crear paquetes de aplicaciones**.

![Cuadro de diálogo crear paquetes de aplicaciones](./media/windows-migration/create-app-packages.png)

Seleccione la opción instalación de prueba para implementar la aplicación desde el equipo:

![Seleccionar la opción de instalación de prueba](./media/windows-migration/select-sideloading-option.png)

Seleccione la arquitectura de aplicación de la aplicación:

![Seleccionar la arquitectura de la aplicación](./media/windows-migration/select-app-architecture.png)

Finalmente, haga clic en **crear** para crear el paquete.

## <a name="xaml-islands"></a>Islas XAML

Las islas XAML son un conjunto de componentes que permiten a los desarrolladores de escritorio de Windows usar controles XAML de UWP en sus aplicaciones Win32 existentes, como Windows Forms y WPF.

![Estructura de islas XAML](./media/windows-migration/xaml-islands.png)

Puede crear una imagen de la aplicación Win32 con sus controles estándar y entre ellos una "isla" de la interfaz de usuario de UWP que contiene controles del mundo moderno. El concepto es similar a tener un iFrame dentro de una página web que muestra el contenido de un `different page.`

Además de agregar funcionalidad desde las API de Windows 10, puede agregar elementos de XAML de UWP dentro de la aplicación mediante islas XAML.

Windows 10 1903 Update incluye un conjunto de API que permite hospedar contenido XAML de UWP en ventanas de Win32. Solo las aplicaciones que se ejecutan en Windows 10 1903 pueden usar islas XAML.

### <a name="the-road-to-xaml-islands"></a>El camino a las islas XAML

La ruta a las islas XAML comenzó en 2012 cuando Microsoft presentó las API de WinRT como un marco para modernizar las aplicaciones Win32 (Windows Forms, WPF y aplicaciones nativas de Win32). Sin embargo, los nuevos controles de IU dentro de WinRT estaban disponibles para las nuevas aplicaciones, pero no para los existentes.

En 2015, junto con Windows 10, se nació UWP. UWP le permite crear aplicaciones que funcionan en dispositivos Windows como XBox, Mobile y Desktop. Un año después, Microsoft anunció Desktop Bridge (antes conocido como Project Centennial). Puente de escritorio es un conjunto de herramientas que permiten a los desarrolladores traer sus aplicaciones Win32 existentes al Microsoft Store. Se han agregado más funcionalidades en 2017, lo que permite a los desarrolladores mejorar sus aplicaciones Win32 aprovechando algunas de las nuevas API de Windows 10, como iconos dinámicos y notificaciones en el centro de actividades. Pero todavía no hay nuevos controles de interfaz de usuario.

En la compilación 2018, Microsoft anunció una manera para que los desarrolladores usen los nuevos controles XAML de Windows 10 en sus aplicaciones de Win32 actuales, sin migrar completamente sus aplicaciones a UWP. Se marca como islas XAML de UWP.

### <a name="how-it-works"></a>Cómo funciona

La actualización de Windows 10 1903 presenta varias API de hospedaje de XAML. Dos de ellos son `WindowsXamlManager`   y  `DesktopWindowXamlSource` .

La  `WindowsXamlManager`   clase controla el marco XAML de UWP. Su `InitializeForCurrentThread` método carga el marco XAML de UWP dentro del subproceso actual de la aplicación Win32.

 `DesktopWindowXamlSource`   Es la instancia del contenido de la isla XAML. Tiene la `Content` propiedad, que es responsable de la creación de instancias y la configuración de. El `DesktopWindowXamlSource`   representa y obtiene la entrada de un HWND. Debe saber a qué otro HWND adjuntará el de la isla XAML y será responsable de ajustar el tamaño y la posición del HWND del elemento primario.

Los desarrolladores de WPF o Windows Forms no suelen tratar con HWND dentro de su código, por lo que puede ser difícil comprender y controlar punteros HWND y los contenidos de cableado subyacentes para comunicar los mundos de Win32 y UWP.

#### <a name="the-xaml-islands-net-wrappers"></a>Contenedores .NET de islas XAML

El kit de herramientas de la comunidad de Windows tiene un conjunto de los contenedores .NET de las islas XAML para WPF o Windows Forms que facilitan el uso de las islas XAML. Estos contenedores administran el HWND, la administración de enfoque, entre otras cosas. Los desarrolladores de Windows Forms y WPF deben usar estos contenedores.

El kit de herramientas de la comunidad de Windows ofrece dos tipos de controles: controles ajustados y controles de hospedaje.

##### <a name="wrapped-controls"></a>Controles ajustados

Estos controles ajustados ajustan algunos controles de UWP en Windows Forms o controles de WPF, ocultando los conceptos de UWP para esos desarrolladores. Estos controles son:

* WebView y WebViewCompatible
* InkCanvas e InkToolbar
* MediaPlayerElement
* MapControl

Agregue el `Microsoft.Toolkit.Wpf.UI.Controls` paquete al proyecto, incluya la referencia al espacio de nombres y empiece a usarlos.

```xml
<Window
        ...
        xmlns:uwpControls="clr-namespace:Microsoft.Toolkit.Wpf.UI.Controls;assembly=Microsoft.Toolkit.Wpf.UI.Controls">
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="Auto"/>
        <RowDefinition Height="\*"/>
    </Grid.RowDefinitions>
    <uwpControls:InkToolbar TargetInkCanvas="{x:Reference Name=inkCanvas}"/>
    <uwpControls:InkCanvas Grid.Row="1" x:Name="inkCanvas" />
</Grid>
```

##### <a name="hosting-controls"></a>Hospedar controles

La eficacia de las islas XAML se extiende a la mayoría de los controles de primera parte, controles de terceros y controles personalizados desarrollados para UWP, que se pueden integrar en Windows Forms y WPF como "islas" con la interfaz de usuario totalmente funcional. El `WindowsXamlHost` control para WPF y Windows Forms permite hacerlo.

Por ejemplo, para usar el `WindowsXamlHost` control en WPF, agregue una referencia al `Microsoft.Toolkit.Wpf.UI.XamlHost` paquete proporcionado por el kit de herramientas de la comunidad de Windows.

Una vez que haya colocado `WindowsXamlHost` en el código de la interfaz de usuario, especifique el tipo de UWP que quiere cargar. Puede optar por usar un control ajustado como un `Button` o un más complejo compuesto por varios controles distintos, que son un control UWP personalizado.

En el ejemplo siguiente se muestra cómo agregar un UWP `Button` :

```xml
<Window
        ...
        xmlns:xamlhost="clr-namespace:Microsoft.Toolkit.Wpf.UI.XamlHost;assembly=Microsoft.Toolkit.Wpf.UI.XamlHost">

<xamlhost:WindowsXamlHost x:Name="myUwpButton"
                          InitialTypeName="Windows.UI.Xaml.Controls.Button" />
```

Hay una recomendación clara sobre cómo enfocar esto y es mejor tener una isla XAML única y más grande que contenga un control compuesto personalizado que tener varias islas con un control en cada una.

Una de las características principales de XAML es el enlace y funciona entre el código Win32 y la isla. Por lo tanto, puede enlazar, por ejemplo, un Win32 `Textbox` con un UWP `Textbox` . Es importante tener en cuenta que estos enlaces son enlaces unidireccionales, de UWP a Win32, por lo que si actualiza `Textbox` dentro de la isla XAML, el cuadro de texto Win32 se actualizará, pero no al revés.

Para ver un tutorial sobre cómo usar las islas XAML, consulte:

<https://docs.microsoft.com/windows/apps/desktop/modernize/host-standard-control-with-xaml-islands>

#### <a name="adding-uwp-xaml-custom-controls"></a>Agregar controles personalizados XAML de UWP

Un control personalizado XAML es un control (o control de usuario) creado por usted o por terceros (incluidos los controles WinUI 2. x). Para hospedar un control personalizado de UWP en una aplicación Windows Forms o WPF, necesitará:

- Para usar el `WindowsXamlHost` control UWP en la aplicación .net Core 3. x.
- Para crear un proyecto de aplicación para UWP que define un `XamlApplication` objeto.

El proyecto de WPF o Windows Forms debe tener acceso a una instancia de la `Microsoft.Toolkit.Win32.UI.XamlHost.XamlApplication` clase proporcionada por el kit de herramientas de la comunidad de Windows. Este objeto actúa como proveedor de metadatos raíz para cargar los metadatos de los tipos XAML de UWP personalizados en los ensamblados en el directorio actual de la aplicación. La manera recomendada de hacerlo es agregar un proyecto de aplicación vacía (Windows universal) a la misma solución que el proyecto de WPF o Windows Forms y revisar la clase de aplicación predeterminada en este proyecto.

El control XAML de UWP personalizado se puede incluir en esta aplicación para UWP o en un proyecto de biblioteca de clases de UWP independiente al que haga referencia en la misma solución que el proyecto de WPF o Windows Forms.

Puede consultar una descripción detallada del proceso paso a paso en:

<https://docs.microsoft.com/windows/apps/desktop/modernize/host-custom-control-with-xaml-islands>

#### <a name="the-windows-ui-library-winui-2"></a>La biblioteca de la interfaz de usuario de Windows (WinUI 2)

Además de los controles de bandeja de entrada de Windows 10 que vienen con el sistema operativo, el mismo equipo XAML de UWP también proporciona controles adicionales en la biblioteca de la interfaz de usuario de Windows (**WinUI 2**). WinUI 2 proporciona controles de interfaz de usuario nativos de Microsoft y características para las aplicaciones UWP de Windows y estos controles se pueden usar dentro de las islas XAML.

WinUI 2 es de código abierto y puede encontrar información en <https://github.com/microsoft/microsoft-ui-xaml> .

En el siguiente artículo se muestra cómo hospedar un control XAML de UWP de la biblioteca WinUI 2: <https://docs.microsoft.com/windows/apps/desktop/modernize/host-custom-control-with-xaml-islands>

### <a name="do-you-need-xaml-islands"></a>¿Necesita islas XAML?

Las islas XAML están pensadas para las aplicaciones Win32 existentes que quieren mejorar su experiencia de usuario aprovechando los nuevos controles y comportamientos de UWP sin necesidad de volver a escribir la aplicación. Ya puede [aprovechar las API de Windows 10](/windows/uwp/porting/desktop-to-uwp-enhance), pero hasta las islas XAML, solo las API relacionadas con la interfaz de usuario.

Si está desarrollando una nueva aplicación de Windows, [](/windows/uwp/get-started/universal-application-platform-guide)   es probable que una aplicación de UWP sea el enfoque correcto.

### <a name="the-road-ahead-xaml-islands-winui-30"></a>Islas XAML de la carretera anterior: WinUI 3,0

Desde Windows 8, la plataforma de la interfaz de usuario de Windows, incluido el marco de interfaz de usuario XAML, el nivel de composición visual y el procesamiento de entrada se ha enviado como parte integral de Windows. Esto significa que, para beneficiarse de las mejoras más recientes en las tecnologías de interfaz de usuario, debe actualizar a la versión más reciente de la interfaz de usuario, lo que ralentiza el ritmo de innovación al desarrollar sus aplicaciones. Para desacoplar estos dos ciclos de evolución y fomentar la innovación, Microsoft está trabajando activamente en el proyecto WinUI.

A partir de WinUI 2 en 2018, Microsoft comenzó a enviar algunos nuevos controles y características de la interfaz de usuario XAML como paquetes NuGet independientes que se basan en el SDK de UWP.

![Estructura de WinUI 2,0](./media/windows-migration/winui2.png)

WinUI 3 está en desarrollo activo y expandirá en gran medida el ámbito de WinUI para incluir la plataforma completa de la interfaz de usuario, que estará totalmente desacoplada del SDK de UWP:

![Estructura de WinUI 3,0](./media/windows-migration/winui3.png)

El marco XAML ahora se desarrollará en GitHub y se enviará fuera de banda como paquetes [NuGet](/nuget/what-is-nuget)   .

Las API de XAML de UWP existentes que se incluyen como parte del sistema operativo ya no recibirán nuevas actualizaciones de las características. Seguirán recibiendo actualizaciones de seguridad y correcciones críticas según el ciclo de vida de soporte técnico de Windows 10.

El Plataforma universal de Windows contiene algo más que solo el marco XAML (por ejemplo, la aplicación y el modelo de seguridad, la canalización multimedia, las integraciones de Shell de Xbox y Windows 10, la amplia compatibilidad con dispositivos) y continuará evolucionando. Todas las nuevas características XAML se desarrollarán y se enviarán como parte de WinUI en su lugar.

#### <a name="winui-3-in-desktop-app-and-winui-xaml-islands"></a>WinUI 3 en la aplicación de escritorio y islas XAML de WinUI

Como puede ver, WinUI 3 es la evolución del XAML de UWP y funciona de forma natural en el modelo de aplicación de UWP y en todos sus requisitos (identificador empaquetado de MSIX, espacio aislado, CoreWindow, etc.). Para usar simplemente WinUI 3 en un modelo de aplicación de Win32, el contenido de WinUI debe estar hospedado por otro marco de interfaz de usuario (Windows Forms, WPF, etc.) mediante **islas XAML de WinUI**. Esta es la ruta de acceso correcta si desea desarrollar la aplicación y mezclar tecnologías. Sin embargo, si desea reemplazar toda la interfaz de usuario antigua de WinUI, la aplicación no debe cargar marcos de interfaz de usuario para hospedar únicamente WinUI.

WinUI 3 abordará esta información crítica agregando **WinUI en aplicaciones de escritorio**. Esto permitirá que las aplicaciones Win32 puedan usar WinUI 3 como marco de interfaz de usuario independiente. no es necesario cargar Windows Forms o WPF.

Dentro de esta agregación, WinUI 3 permitirá a los desarrolladores combinar y encontrar fácilmente la combinación correcta de:

* Modelo de aplicación: UWP, Win32
* Plataforma: .NET Core o nativo
* Lenguaje: .NET (C \# , Visual Basic), C++ estándar
* Empaquetado: MSIX, AppX para el Microsoft Store, desempaquetado
* Interop: Use WinUI 3 para ampliar las aplicaciones existentes de WPF, WinForms y MFC con islas XAML de WinUI.

Si desea conocer más detalles, Microsoft está compartiendo esta guía básica en <https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md> .

>[!div class="step-by-step"]
>[Anterior](migrate-modern-applications.md)
>[Siguiente](example-migration-core.md)
