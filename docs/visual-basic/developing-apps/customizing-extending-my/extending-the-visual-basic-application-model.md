---
title: Ampliar el modelo de la aplicación de Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
ms.openlocfilehash: 64c175216cf21b7947462cf79e4b88ab6fcd6d86
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245653"
---
# <a name="extending-the-visual-basic-application-model"></a>Ampliar el modelo de la aplicación de Visual Basic
Puede agregar funcionalidad al modelo de aplicación invalidando el `Overridable` los miembros de la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> clase. Esta técnica permite personalizar el comportamiento del modelo de aplicación y agregar llamadas a sus propios métodos como la aplicación se inicia y se cierra.  
  
## <a name="visual-overview-of-the-application-model"></a>Información general visual del modelo de aplicación  
 Esta sección presenta visualmente la secuencia de llamadas de función en el modelo de aplicación de Visual Basic. La siguiente sección describe el propósito de cada función en detalle.  
  
 El gráfico siguiente muestra la secuencia de llamada del modelo de aplicación en una aplicación de formularios Windows Forms de Visual Basic normal. La secuencia inicia cuando el `Sub Main` las llamadas a procedimiento el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> método.  
  
 ![Modelo de aplicación de Visual Basic &#45; &#45; ejecutar](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelrun.gif "VB_ModelRun")  
  
 El modelo de aplicación de Visual Basic también proporciona la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> y <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> eventos. Los gráficos siguientes muestran el mecanismo para generar estos eventos.  
  
 ![Modelo de aplicación de Visual Basic &#45; &#45; después de la instancia](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelnext.gif "VB_ModelNext")  
  
 ![Excepción no controlada del modelo de aplicación de Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_unhandex.gif "VB_UnhandEx")  
  
## <a name="overriding-the-base-methods"></a>Reemplazar los métodos Base  
 El <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> método define el orden en que el `Application` métodos que se ejecute. De forma predeterminada, el `Sub Main` procedimiento para una aplicación Windows Forms se llama a la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> método.  
  
 Si la aplicación es una aplicación normal (aplicación de varias instancias) o la primera instancia de una aplicación de instancia única, el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> método se ejecuta el `Overridable` métodos en el orden siguiente:  
  
1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>. De forma predeterminada, este método establece los estilos visuales, los estilos de presentación de texto y una entidad de seguridad actual para el subproceso principal de la aplicación (si la aplicación utiliza la autenticación de Windows) y las llamadas `ShowSplashScreen` si no `/nosplash` ni `-nosplash` se utiliza como un argumento de línea de comandos.  
  
     La secuencia de inicio de la aplicación se cancela si esta función devuelve `False`. Esto puede ser útil si hay circunstancias en las que no debe ejecutar la aplicación.  
  
     El <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> método llama a los métodos siguientes:  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>. Determina si la aplicación tiene definida una pantalla de presentación y si es así, muestra la pantalla de presentación en un subproceso independiente.  
  
         El <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> método contiene el código que muestra la presentación de pantalla de al menos el número de milisegundos especificados por el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A> propiedad. Para usar esta funcionalidad, debe agregar la pantalla de presentación para la aplicación mediante el **Diseñador de proyectos** (que establece el `My.Application.MinimumSplashScreenDisplayTime` propiedad a dos segundos), o establecer el `My.Application.MinimumSplashScreenDisplayTime` propiedad en un método que reemplaza el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> o <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> método. Para obtener más información, consulta <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>.  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>. Permite que un diseñador emitir código que inicializa la pantalla de presentación.  
  
         De forma predeterminada, este método no hace nada. Si selecciona una pantalla de presentación para su aplicación en Visual Basic **Diseñador de proyectos**, invalida el diseñador la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> método con un método que establece el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A> propiedad a una nueva instancia de la forma de pantalla de presentación .  
  
2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A>. Proporciona un punto de extensibilidad para generar el `Startup` eventos. La secuencia de inicio de la aplicación se detiene si esta función devuelve `False`.  
  
     De forma predeterminada, este método provoca la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> eventos. Si establece el controlador de eventos el <xref:System.ComponentModel.CancelEventArgs.Cancel> propiedad del argumento de evento `True`, el método devuelve `False` para cancelar el inicio de la aplicación.  
  
3.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A>. Proporciona el punto de partida cuando está lista para empezar a ejecutar después de realiza la inicialización de la aplicación principal.  
  
     De forma predeterminada, antes de entrar en el bucle de mensajes de Windows Forms, este método llama a la `OnCreateMainForm` (para crear el formulario principal de la aplicación) y `HideSplashScreen` (para cerrar la pantalla de presentación) métodos:  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>. Proporciona una manera para que un diseñador emitir código que inicializa el formulario principal.  
  
         De forma predeterminada, este método no hace nada. Sin embargo, cuando selecciona un formulario principal de la aplicación en Visual Basic **Diseñador de proyectos**, el diseñador reemplaza el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> método con un método que establece el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> propiedad a una nueva instancia del formulario principal.  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A>. Si la aplicación tiene definida una pantalla de presentación y está abierta, este método cierra la pantalla de presentación.  
  
         De forma predeterminada, este método cierra la pantalla de presentación.  
  
4.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>. Proporciona una manera de personalizar el comportamiento de una aplicación de instancia única cuando se inicia otra instancia de la aplicación.  
  
     De forma predeterminada, este método provoca la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> eventos.  
  
5.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A>. Proporciona un punto de extensibilidad para generar el `Shutdown` eventos. Este método no se ejecuta si se produce una excepción no controlada en la aplicación principal.  
  
     De forma predeterminada, este método provoca la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> eventos.  
  
6.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A>. Se ejecuta si se produce una excepción no controlada en cualquiera de los métodos enumerados anteriormente.  
  
     De forma predeterminada, este método provoca la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> eventos siempre y cuando no se adjunta un depurador y la aplicación está controlando el `UnhandledException` eventos.  
  
 Si la aplicación es una aplicación de instancia única y la aplicación ya se está ejecutando, se llama la instancia subsiguiente de la aplicación la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> método en la instancia original de la aplicación y, a continuación, se cierra.  
 
 El <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance(Microsoft.VisualBasic.ApplicationServices.StartupNextInstanceEventArgs)> constructor llama a la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> propiedad para determinar qué motor de representación de texto que se usará para los formularios de la aplicación. De forma predeterminada, el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> propiedad devuelve `False`, que indica que se usa el motor de representación de texto GDI, que es el valor predeterminado en [!INCLUDE[vbprvblong](~/includes/vbprvblong-md.md)]. Puede invalidar el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> propiedad para devolver `True`, lo que indica que se usa el motor de representación de texto GDI +, que es el valor predeterminado en Visual Basic .NET 2002 y Visual Basic .NET 2003.  
  
## <a name="configuring-the-application"></a>Configuración de la aplicación  
 Como parte del modelo de aplicación de Visual Basic, el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering> clase proporciona propiedades protegidas que configuran la aplicación. Estas propiedades deben establecerse en el constructor de la clase de implementación.  
  
 En un proyecto de Windows Forms de forma predeterminada, el **Diseñador de proyectos** crea código para establecer las propiedades con la configuración del diseñador. Las propiedades se utilizan solo cuando se inicia la aplicación; establecerlas tras iniciar la aplicación no tiene ningún efecto.  
  
|Property|Determina|Configuración en el panel aplicación del Diseñador de proyectos|  
|---|---|---|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|Si la aplicación se ejecuta como una aplicación de instancia única o varias instancias.|**Crear aplicación de instancia única** casilla de verificación|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|Si la aplicación va a usar los estilos visuales que coinciden con Windows XP.|**Habilitar estilos visuales de XP** casilla de verificación|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|Si la aplicación guarda automáticamente los cambios de configuración de usuario de la aplicación cuando se cierra la aplicación.|**Guardar My.Settings al apagar** casilla de verificación|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|¿Qué hace que la aplicación finalice, por ejemplo, cuando se cierra el formulario de inicio o cuando se cierra el último formulario.|**Modo de apagado** lista|  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
 [Información general sobre el modelo de aplicaciones de Visual Basic](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)  
 [Página de aplicación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
