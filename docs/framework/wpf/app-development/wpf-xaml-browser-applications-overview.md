---
title: Información general sobre las aplicaciones de explorador XAML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XBAP [WPF], XAML browser application
- WPF XAML browser applications (XBAP)
- XAML browser applications (XBAP)
- browser-hosted applications [WPF]
ms.assetid: 3a7a86a8-75d5-4898-96b9-73da151e5e16
ms.openlocfilehash: 825b689dea145d18035344cd902ea1b8a50e82c3
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124213"
---
# <a name="wpf-xaml-browser-applications-overview"></a>Información general sobre las aplicaciones de explorador XAML de WPF
<a name="introduction"></a>Las aplicaciones de explorador XAML (XBAP) combinan características de las aplicaciones web y las aplicaciones cliente enriquecidas. Al igual que las aplicaciones web, las aplicaciones XBAP se pueden implementar en un servidor web e iniciar desde Internet Explorer o Firefox. Al igual que las aplicaciones cliente enriquecidas, las XBAP pueden aprovechar las capacidades de WPF. El desarrollo de aplicaciones XBAP también se parece al desarrollo de clientes enriquecidos. En este tema se proporciona una sencilla introducción de alto nivel al desarrollo de aplicaciones XBAP y se describe en qué se diferencia este del desarrollo estándar de clientes enriquecidos.

 Este tema contiene las siguientes secciones:

- [Creación de una aplicación de explorador XAML (XBAP)](#creating_a_new_xaml_browser_application_xbap)

- [Implementación de una aplicación XBAP](#deploying_a_xbap)

- [Comunicación con la página web host](#communicating_with_the_host_web_page)

- [Consideraciones de seguridad para XBAP](#xbap_security_considerations)

- [Consideraciones sobre el rendimiento de tiempo de inicio de XBAP](#xbap_start_time_performance_considerations)

<a name="creating_a_new_xaml_browser_application_xbap"></a>
## <a name="creating-a-new-xaml-browser-application-xbap"></a>Creación de una aplicación de explorador XAML (XBAP)
 La manera más sencilla de crear un nuevo proyecto de XBAP es con Visual Studio. Al crear un proyecto, seleccione **Aplicación de explorador WPF** en la lista de plantillas. Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de explorador de WPF](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100)).

 Cuando se ejecuta el proyecto de XBAP, se abre en una ventana del explorador en lugar de en una independiente. Al depurar la aplicación XBAP desde Visual Studio, la aplicación se ejecuta con el permiso de zona de Internet y, por tanto, producirá excepciones de seguridad si se superan esos permisos. Para más información, consulte [Seguridad](../security-wpf.md) y [Seguridad de confianza parcial de WPF](../wpf-partial-trust-security.md).

> [!NOTE]
> Si no va a desarrollar con Visual Studio o desea obtener más información sobre los archivos del proyecto, consulte [compilar una aplicación de WPF](building-a-wpf-application-wpf.md).

<a name="deploying_a_xbap"></a>
## <a name="deploying-an-xbap"></a>Implementación de una aplicación XBAP
 Cuando se compila una aplicación XBAP, en la salida se incluyen los tres archivos siguientes:

|Archivo|Descripción|
|----------|-----------------|
|Ejecutable (.exe)|Contiene el código compilado y tiene la extensión .exe.|
|Manifiesto de aplicación (.manifest)|Contiene metadatos asociados con la aplicación y tiene la extensión .manifest.|
|Manifiesto de implementación (.xbap)|Este archivo contiene la información que usa ClickOnce para implementar la aplicación y tiene la extensión. XBAP.|

 Las XBAP se implementan en un servidor Web, por ejemplo, Microsoft Internet Information Services (IIS) 5,0 o versiones posteriores. No es necesario que instale el .NET Framework en el servidor Web, pero tiene que registrar los tipos de extensiones multipropósito de correo Internet (MIME) y las extensiones de nombre de archivo de WPF. Para más información, consulte [Cómo: Configurar IIS 5.0 e IIS 6.0 para implementar aplicaciones WPF](how-to-configure-iis-5-0-and-iis-6-0-to-deploy-wpf-applications.md).

 Para preparar la aplicación XBAP para la implementación, copie el archivo .exe y los manifiestos asociados al servidor web. Cree una página HTML que contenga un hipervínculo para abrir el manifiesto de implementación, que es el archivo con la extensión .xbap. Cuando el usuario hace clic en el vínculo al archivo. XBAP, ClickOnce controla automáticamente los mecanismos de descarga e inicio de la aplicación. En el ejemplo de código siguiente, se muestra una página HTML que contiene un hipervínculo que apunta a una aplicación XBAP.

```html
<html>
    <head></head>
    <body>
        <a href="XbapEx.xbap">Click this link to launch the application</a>
    </body>
</html>
```

 También puede hospedar una aplicación XBAP en el marco de una página web. Cree una página web con uno o varios marcos. Establezca la propiedad de origen de un marco en el archivo de manifiesto de implementación. Si desea usar el mecanismo integrado para la comunicación entre la página web que hospeda y la aplicación XBAP, debe hospedar la aplicación en un marco. En el ejemplo de código siguiente, se muestra una página HTML con dos marcos, donde el origen del segundo marco está establecido en una aplicación XBAP.

```html
<html>
    <head>
        <title>A page with frames</title>
    </head>
    <frameset cols="50%,50%">
        <frame src="introduction.htm">
        <frame src="XbapEx.xbap">
    </frameset>
</html>
```

### <a name="clearing-cached-xbaps"></a>Borrado de las aplicaciones XBAP en caché
 En algunas situaciones, después de volver a compilar e iniciar la aplicación XBAP, es posible que se abra una versión anterior de ella. Por ejemplo, este comportamiento puede producirse cuando el número de versión del ensamblado XBAP es estático y se inicia la aplicación XBAP desde la línea de comandos. En este caso, como no ha cambiado el número de versión entre la versión almacenada en caché (la que se inició previamente) y la nueva versión, no se descarga la nueva versión de la aplicación XBAP. En su lugar, se carga la versión almacenada en caché.

 En estas situaciones, puede quitar la versión almacenada en caché mediante el comando **Mage** (instalado con Visual Studio o el Windows SDK) en el símbolo del sistema. Con el siguiente comando se borra la memoria caché de la aplicación.

 ```console
 Mage.exe -cc
 ```

 Este comando garantiza que se inicie la versión más reciente de la aplicación XBAP. Al depurar la aplicación en Visual Studio, se debe iniciar la versión más reciente de la aplicación XBAP. Por lo general, debería actualizar el número de versión de implementación con cada compilación. Para más información sobre Mage, consulte [Mage.exe (Herramienta de generación y edición de manifiestos)](../../tools/mage-exe-manifest-generation-and-editing-tool.md).

<a name="communicating_with_the_host_web_page"></a>
## <a name="communicating-with-the-host-web-page"></a>Comunicación con la página web host
 Cuando la aplicación se hospeda en un marco HTML, se puede comunicar con la página web que contiene la aplicación XBAP. Para ello, se recupera la propiedad <xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A> de <xref:System.Windows.Interop.BrowserInteropHelper>. Esta propiedad devuelve un objeto de script que representa la ventana HTML. Después, puede acceder a las propiedades, los métodos y los eventos en el [objeto window](https://developer.mozilla.org/en-US/docs/Web/API/Window) mediante la sintaxis con punto normal. También puede acceder a los métodos de script y a las variables globales. En el ejemplo siguiente se muestra cómo recuperar el objeto de script y cerrar el explorador.

 [!code-csharp[XbapBrowserInterop#10](~/samples/snippets/csharp/VS_Snippets_Wpf/xbapbrowserinterop/cs/page1.xaml.cs#10)]
 [!code-vb[XbapBrowserInterop#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/xbapbrowserinterop/vb/page1.xaml.vb#10)]

### <a name="debugging-xbaps-that-use-hostscript"></a>Depuración de aplicaciones XBAP que usan HostScript
 Si su aplicación XBAP usa el objeto <xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A> para comunicarse con la ventana HTML, hay dos opciones que debe especificar para ejecutar y depurar la aplicación en Visual Studio. La aplicación debe tener acceso a su sitio de origen y se debe iniciar la aplicación con la página HTML que contiene la aplicación XBAP. En los pasos siguientes se describe cómo comprobar estas dos configuraciones:

1. En Visual Studio, abra las propiedades del proyecto.

2. En la pestaña **Seguridad**, haga clic en **Opciones avanzadas**.

     Se abre el cuadro de diálogo Configuración de seguridad avanzada.

3. Asegúrese de que la casilla **Conceder a la aplicación acceso al sitio de origen** esté activada y haga clic en **Aceptar**.

4. En la pestaña **Depurar**, seleccione la opción **Iniciar explorador con la dirección URL** y especifique la dirección URL de la página HTML que contiene la aplicación XBAP.

5. En Internet Explorer, haga clic en el botón **Herramientas** y seleccione **Opciones de Internet**.

     Aparecerá el cuadro de diálogo Opciones de Internet.

6. Haga clic en la pestaña **Opciones avanzadas**.

7. En la lista **Configuración**, bajo **Seguridad**, active la casilla **Permitir que el contenido activo se ejecute en los archivos de mi equipo**.

8. Haga clic en **OK**.

     Los cambios surtirán efecto una vez que reinicie Internet Explorer.

> [!CAUTION]
> La habilitación del contenido activo en Internet Explorer puede poner en peligro su equipo. Si no desea cambiar la configuración de seguridad de Internet Explorer, puede iniciar la página HTML desde un servidor y adjuntar el depurador de Visual Studio al proceso.

<a name="xbap_security_considerations"></a>
## <a name="xbap-security-considerations"></a>Consideraciones de seguridad para XBAP
 Las aplicaciones XBAP suelen ejecutarse en un espacio aislado con seguridad de confianza parcial que se restringe al conjunto de permisos de zona de Internet. Por consiguiente, la implementación de debe admitir el subconjunto de elementos de WPF que se admiten en la zona de Internet o debe elevar los permisos de la aplicación. Para obtener más información, consulte [Seguridad](../security-wpf.md).

 Cuando se usa un control de <xref:System.Windows.Controls.WebBrowser> en la aplicación, WPF crea internamente instancias del control ActiveX WebBrowser nativo. Cuando se trata de una aplicación XBAP de confianza parcial que se ejecuta en Internet Explorer, el control ActiveX se ejecuta en un subproceso dedicado del proceso de Internet Explorer. Por tanto, se aplican las siguientes limitaciones:

- El control de <xref:System.Windows.Controls.WebBrowser> debe proporcionar un comportamiento similar al del explorador host, incluidas las restricciones de seguridad. Algunas de estas restricciones de seguridad se pueden controlar mediante la configuración de seguridad de Internet Explorer. Para obtener más información, consulte [Seguridad](../security-wpf.md).

- Se genera una excepción cuando se carga una aplicación XBAP entre dominios en una página HTML.

- La entrada está en un subproceso independiente del <xref:System.Windows.Controls.WebBrowser>de WPF, por lo que no se puede interceptar la entrada de teclado y el estado del IME no se comparte.

- La sincronización o el orden de navegación pueden variar como consecuencia del control ActiveX que se ejecuta en otro subproceso. Por ejemplo, no siempre se cancela la navegación a una página cuando se inicia otra solicitud de navegación.

- Es posible que un control ActiveX personalizado experimente problemas de comunicación porque la aplicación WPF se esté ejecutando en un subproceso independiente.

- <xref:System.Windows.Interop.HwndHost.MessageHook> no se produce porque <xref:System.Windows.Interop.HwndHost> no puede subclaser una ventana que se ejecuta en otro subproceso o proceso.

### <a name="creating-a-full-trust-xbap"></a>Creación de una aplicación XBAP de plena confianza
 Si la aplicación XBAP necesita plena confianza, puede cambiar el proyecto para habilitar este permiso. En los pasos siguientes se describe cómo habilitar la plena confianza:

1. En Visual Studio, abra las propiedades del proyecto.

2. En la pestaña **Seguridad**, seleccione la opción **Aplicación de plena confianza**.

 Esta configuración realiza los cambios siguientes:

- En el archivo de proyecto, el valor del elemento `<TargetZone>` se cambia a `Custom`.

- En el manifiesto de aplicación (App. manifest), se agrega un atributo `Unrestricted="true"` al elemento '<xref:System.Security.PermissionSet>.

    ```xml
    <PermissionSet class="System.Security.PermissionSet"
                   version="1"
                   ID="Custom"
                   SameSite="site"
                   Unrestricted="true" />
    ```

### <a name="deploying-a-full-trust-xbap"></a>Implementación de una aplicación XBAP de plena confianza
 Al implementar una aplicación XBAP de plena confianza que no sigue el modelo de implementación de confianza de ClickOnce, el comportamiento cuando el usuario ejecute la aplicación dependerá de la zona de seguridad. En algunos casos, el usuario recibirá una advertencia al intentar instalarla. El usuario puede elegir continuar o cancelar la instalación. En la tabla siguiente se describe el comportamiento de la aplicación para cada zona de seguridad y qué se debe hacer para que la aplicación reciba plena confianza.

|Zona de seguridad|Comportamiento|Obtener plena confianza|
|-------------------|--------------|------------------------|
|Equipo local|Plena confianza automática|No se requiere ninguna acción.|
|Intranet y sitios de confianza|Pedir plena confianza|Firme la aplicación XBAP con un certificado para que el usuario vea el origen en la petición.|
|Internet|Error: "Confianza no concedida"|Firme XBAP con un certificado.|

> [!NOTE]
> El comportamiento descrito en la tabla anterior es para las aplicaciones XBAP de plena confianza que no sigan el modelo de implementación de confianza de ClickOnce.

 Se recomienda que utilice el modelo de implementación de confianza de ClickOnce para implementar una aplicación XBAP de plena confianza. Este modelo permite que se conceda a la aplicación XBAP plena confianza automáticamente, independientemente de la zona de seguridad, por lo que no hay que pedirla al usuario. Como parte de este modelo, debe firmar la aplicación con un certificado de un editor de confianza. Para más información, consulte [Información general sobre la implementación de aplicaciones de confianza](/visualstudio/deployment/trusted-application-deployment-overview) y [Seguridad](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537361(v=vs.85)).

<a name="xbap_start_time_performance_considerations"></a>
## <a name="xbap-start-time-performance-considerations"></a>Consideraciones sobre el rendimiento de tiempo de inicio de XBAP
 Un aspecto importante del rendimiento de la aplicación XBAP es el tiempo de inicio. Si una aplicación XBAP es la primera aplicación WPF en cargarse, el tiempo de *inicio en frío* puede ser de diez segundos o más. Esto se debe a que WPF representa la página de progreso, y tanto CLR como WPF se deben iniciar en frío para mostrar la aplicación.

 A partir de .NET Framework 3,5 SP1, la hora de inicio en frío de XBAP se mitiga al mostrar una página de progreso no administrada al principio del ciclo de implementación. La página de progreso aparece casi inmediatamente después de iniciarse la aplicación, porque se muestra con código hospedado de forma nativa y se representa en HTML.

 Además, la simultaneidad mejorada de la secuencia de descarga de ClickOnce mejora el tiempo de inicio hasta un diez por ciento. Una vez que ClickOnce descarga y valida los manifiestos, se inicia la descarga de la aplicación y la barra de progreso comienza a actualizarse.

## <a name="see-also"></a>Consulte también

- [Configurar Visual Studio para depurar una aplicación de explorador XAML y llamar a un servicio web](configure-vs-to-debug-a-xaml-browser-to-call-a-web-service.md)
- [Implementar una aplicación WPF](deploying-a-wpf-application-wpf.md)
