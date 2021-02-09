---
description: 'Más información acerca de: Ampliar el modelo de la aplicación de Visual Basic'
title: Ampliar el modelo de la aplicación de Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
ms.openlocfilehash: 3aea2ab77b46976b6f7b220ee0b5811dc97e373c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99775583"
---
# <a name="extending-the-visual-basic-application-model"></a>Ampliar el modelo de la aplicación de Visual Basic

Puede agregar funcionalidad al modelo de aplicación reemplazando los miembros `Overridable` de la clase <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Esta técnica permite personalizar el comportamiento del modelo de aplicación y agregar llamadas a sus propios métodos a medida que la aplicación se inicia y se cierra.

## <a name="visual-overview-of-the-application-model"></a>Introducción visual al modelo de la aplicación

En esta sección se presenta visualmente la secuencia de llamada a función en el modelo de la aplicación de Visual Basic. En la siguiente sección se describe detalladamente el objetivo de cada función.

En el gráfico siguiente se muestra la secuencia de llamada del modelo de la aplicación en una aplicación Windows Forms en Visual Basic normal. La secuencia se inicia cuando el procedimiento `Sub Main` llama al método <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>.

![Diagrama que muestra la secuencia de llamadas del modelo de la aplicación.](./media/extending-the-visual-basic-application-model/application-model-call-sequence.gif)

El modelo de la aplicación de Visual Basic también proporciona los eventos <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> y <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>. Los gráficos siguientes muestran el mecanismo para generar estos eventos.

![Diagrama que muestra el método OnStartupNextInstance que genera el evento StartupNextInstance.](./media/extending-the-visual-basic-application-model/raise-startupnextinstance-event.gif)

![Diagrama que muestra el método OnUnhandledException que genera el evento UnhandledException.](./media/extending-the-visual-basic-application-model/raise-unhandledexception-event.gif)

## <a name="overriding-the-base-methods"></a>Reemplazo de los métodos base

El método <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> define el orden en el que se ejecutan los métodos `Application`. De forma predeterminada, el procedimiento `Sub Main` para una aplicación Windows Forms llama al método <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>.

Si la aplicación es una aplicación normal (aplicación de varias instancias) o la primera instancia de una aplicación de una sola instancia, el método <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> ejecuta los métodos `Overridable` en el orden siguiente:

1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>. De forma predeterminada, este método establece los estilos visuales, los estilos de presentación de texto y la entidad de seguridad actual del subproceso de aplicación principal (si la aplicación usa la autenticación de Windows) y llama a `ShowSplashScreen` si no se utiliza `/nosplash` ni `-nosplash` como argumento de la línea de comandos.

     La secuencia de inicio de la aplicación se cancela si esta función devuelve `False`. Esto puede ser útil si hay circunstancias en las que la aplicación no se debe ejecutar.

     El método <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> llama a los métodos siguientes:

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>. Determina si la aplicación tiene una pantalla de presentación definida y, en caso afirmativo, muestra la pantalla de presentación en un subproceso independiente.

         El método <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> contiene el código que muestra la pantalla de presentación durante al menos el número de milisegundos especificado por la propiedad <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>. Para usar esta funcionalidad, debe agregar la pantalla de presentación a la aplicación mediante el **Diseñador de proyectos** (que establece la propiedad `My.Application.MinimumSplashScreenDisplayTime` en dos segundos) o establecer la propiedad `My.Application.MinimumSplashScreenDisplayTime` en un método que reemplace el método <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> o <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>. Para obtener más información, vea <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>.

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>. Permite a un diseñador emitir código que inicializa la pantalla de presentación.

         De forma predeterminada, este método no hace nada. Si selecciona una pantalla de presentación para la aplicación en el **Diseñador de proyectos** de Visual Basic, el diseñador invalida el método <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> con un método que establece la propiedad <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A> en una nueva instancia del formulario de pantalla de presentación.

2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A>. Proporciona un punto de extensibilidad para generar el evento `Startup`. La secuencia de inicio de la aplicación se detiene si esta función devuelve `False`.

     De forma predeterminada, este método genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>. Si el controlador de eventos establece la propiedad <xref:System.ComponentModel.CancelEventArgs.Cancel> del argumento de evento en `True`, el método devuelve `False` para cancelar el inicio de la aplicación.

3. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A>. Proporciona el punto de partida para cuando la aplicación principal está lista para comenzar a ejecutarse, una vez finalizada la inicialización.

     De forma predeterminada, antes de entrar en el bucle de mensajes de Windows Forms, este método llama a los métodos `OnCreateMainForm` (para crear el formulario principal de la aplicación) y `HideSplashScreen` (para cerrar la pantalla de presentación):

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>. Proporciona una alternativa para que un diseñador emita código que inicialice el formulario principal.

         De forma predeterminada, este método no hace nada. Sin embargo, si se selecciona un formulario principal para la aplicación en el **Diseñador de proyectos** de Visual Basic, el diseñador reemplaza el método <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> por un método que establece la propiedad <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> en una nueva instancia del formulario principal.

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A>. Si la aplicación tiene una pantalla de presentación definida y está abierta, este método cierra la pantalla de presentación.

         De forma predeterminada, este método cierra la pantalla de presentación.

4. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>. Proporciona una manera de personalizar el comportamiento de una aplicación de una sola instancia cuando se inicia otra instancia de la aplicación.

     De forma predeterminada, este método genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>.

5. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A>. Proporciona un punto de extensibilidad para generar el evento `Shutdown`. Este método no se ejecuta si se produce una excepción no controlada en la aplicación principal.

     De forma predeterminada, este método genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>.

6. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A>. Se ejecuta si se produce una excepción no controlada en cualquiera de los métodos enumerados anteriormente.

     De forma predeterminada, este método genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> siempre que no se adjunte un depurador y la aplicación controle el evento `UnhandledException`.

 Si se trata de una aplicación de instancia única y la aplicación ya se está ejecutando, la instancia subsiguiente de la aplicación llama al método <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> en la instancia original de la aplicación y, posteriormente, se cierra.

 El constructor <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance(Microsoft.VisualBasic.ApplicationServices.StartupNextInstanceEventArgs)> llama a la propiedad <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> para determinar qué motor de representación de texto se va a utilizar para los formularios de la aplicación. De forma predeterminada, la propiedad <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> devuelve `False`, que indica que se utilizará el motor de representación de texto GDI, que es el valor predeterminado en Visual Basic 2005 y versiones posteriores. Puede reemplazar la propiedad <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> para que devuelva `True`, que indica que se utilizará el motor de representación de texto GDI+, que es el valor predeterminado en Visual Basic .NET 2002 y Visual Basic .NET 2003.

## <a name="configuring-the-application"></a>Configuración de la aplicación

 Como parte del modelo de aplicación de Visual Basic, la clase <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> proporciona propiedades protegidas que configuran la aplicación. Estas propiedades se deben establecer en el constructor de la clase de implementación.

 En un proyecto de Windows Forms predeterminado, el **Diseñador de proyectos** crea código para establecer las propiedades con la configuración del diseñador. Las propiedades solo se usan cuando se inicia la aplicación; su configuración después de que se inicie la aplicación no tiene ningún efecto.

|Propiedad.|Determina|Opción del panel Aplicación del Diseñador de proyectos|
|---|---|---|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|Si la aplicación se ejecuta como una aplicación de instancia única o de varias instancias.|Casilla de verificación **Crear aplicación de instancia única**|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|Si la aplicación va a usar estilos visuales que coincidan con Windows XP.|Casilla de verificación **Habilitar estilos visuales de XP**|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|Si la aplicación guarda automáticamente los cambios de configuración de usuario de la aplicación cuando se cierra la aplicación.|Casilla de verificación **Guardar My.Settings al apagar**|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|Qué es lo que hace que la aplicación finalice, por ejemplo, cuando el formulario de inicio se cierra o cuando se cierra el último formulario.|Lista **Modo de apagado**|

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- [Información general sobre el modelo de aplicaciones de Visual Basic](../development-with-my/overview-of-the-visual-basic-application-model.md)
- [Página de aplicación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
