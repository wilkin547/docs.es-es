---
title: "Ampliar el modelo de aplicación de Visual Basic | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9752cdfa79d3db4c8b07daa95aea2c842e06cc36
ms.lasthandoff: 03/13/2017

---
# <a name="extending-the-visual-basic-application-model"></a>Ampliar el modelo de la aplicación de Visual Basic
Puede agregar funcionalidad al modelo de aplicación reemplazando la `Overridable` los miembros de la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>clase.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> Esta técnica le permite personalizar el comportamiento del modelo de aplicación y agregar llamadas a sus propios métodos como la aplicación se inicia y se cierra.  
  
## <a name="visual-overview-of-the-application-model"></a>Información general visual del modelo de aplicación  
 Esta sección presenta visualmente la secuencia de llamadas de función en el modelo de aplicaciones de Visual Basic. La siguiente sección describe el propósito de cada función en detalle.  
  
 El gráfico siguiente muestra la secuencia de llamada de modelo de aplicación en una aplicación de formularios Windows Forms de Visual Basic normal. La secuencia inicia cuando la `Sub Main` las llamadas a procedimiento el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>método.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>  
  
 ![Modelo de aplicación de Visual Basic--Ejecutar](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelrun.gif "VB_ModelRun")  
  
 El modelo de aplicación de Visual Basic también proporciona el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>y <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>eventos.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> Los gráficos siguientes muestran el mecanismo para provocar estos eventos.  
  
 ![Modelo de aplicación de Visual Basic--Siguiente instancia](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelnext.gif "VB_ModelNext")  
  
 ![Excepción no controlada del modelo de aplicación de Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_unhandex.gif "VB_UnhandEx")  
  
## <a name="overriding-the-base-methods"></a>Reemplazar los métodos Base  
 El <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>método define el orden en el que el `Application` métodos ejecutar.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> De forma predeterminada, el `Sub Main` procedimiento para una aplicación de Windows Forms llama el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>método.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>  
  
 Si la aplicación es una aplicación normal (aplicación de varias instancias) o la primera instancia de una aplicación de instancia única, la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>método ejecuta el `Overridable` métodos en el orden siguiente:</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>  
  
1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> De forma predeterminada, este método establece los estilos visuales, estilos de presentación de texto y una entidad de seguridad actual del subproceso de aplicación principal (si la aplicación utiliza la autenticación de Windows) y las llamadas `ShowSplashScreen` si no `/nosplash` ni `-nosplash` se utiliza como un argumento de línea de comandos.  
  
     La secuencia de inicio de la aplicación se cancela si esta función devuelve `False`. Esto puede ser útil si hay circunstancias en las que no debe ejecutar la aplicación.  
  
     El <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>método llama a los métodos siguientes:</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> Determina si la aplicación tiene definida una pantalla de presentación y si es así, muestra la pantalla de presentación en un subproceso independiente.  
  
         El <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>método contiene el código que muestra la presentación de pantalla de al menos el número de milisegundos especificado por el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>propiedad.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> Para utilizar esta funcionalidad, debe agregar la pantalla de presentación a la aplicación mediante el **Diseñador de proyectos** (que establece la `My.Application.MinimumSplashScreenDisplayTime` propiedad en dos segundos), o establecer el `My.Application.MinimumSplashScreenDisplayTime` propiedad en un método que reemplaza el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>o <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>método.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> Para obtener más información, consulte <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> Permite a un diseñador emitir código que inicializa la pantalla de presentación.  
  
         De forma predeterminada, este método no hace nada. Si se selecciona una pantalla de presentación para la aplicación en la [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] **Diseñador de proyectos**, el diseñador reemplaza el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>método con un método que establece la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>propiedad a una nueva instancia del formulario de pantalla de presentación.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>  
  
2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A> Proporciona un punto de extensibilidad para generar el `Startup` eventos. La secuencia de inicio de la aplicación se detiene si esta función devuelve `False`.  
  
     De forma predeterminada, este método provoca el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>eventos.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> Si el controlador de eventos establece el @System.ComponentModel.CancelEventArgs.Cancel propiedad del argumento del evento a `True`, el método devuelve `False` para cancelar el inicio de la aplicación.  
  
3.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A> Proporciona el punto de partida cuando está lista para empezar a ejecutarse una vez finalizada la inicialización de la aplicación principal.  
  
     De forma predeterminada, antes de entrar en el bucle de mensajes de formularios Windows Forms, este método llama a la `OnCreateMainForm` (para crear el formulario principal de la aplicación) y `HideSplashScreen` (para cerrar la pantalla de presentación) métodos:  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> Proporciona una manera para que un diseñador emitir código que inicializa el formulario principal.  
  
         De forma predeterminada, este método no hace nada. Sin embargo, cuando se selecciona un formulario principal para la aplicación en la [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] **Diseñador de proyectos**, el diseñador reemplaza el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>método con un método que establece la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>propiedad a una nueva instancia del formulario principal.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A> Si la aplicación tiene definida una pantalla de presentación y está abierta, este método cierra la pantalla de presentación.  
  
         De forma predeterminada, este método cierra la pantalla de presentación.  
  
4.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> Proporciona una manera de personalizar el comportamiento de una aplicación de instancia única cuando se inicia otra instancia de la aplicación.  
  
     De forma predeterminada, este método provoca el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>eventos.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>  
  
5.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A> Proporciona un punto de extensibilidad para generar el `Shutdown` eventos. Este método no se ejecuta si se produce una excepción no controlada en la aplicación principal.  
  
     De forma predeterminada, este método provoca el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>eventos.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>  
  
6.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A> Se ejecuta si se produce una excepción no controlada en cualquiera de los métodos enumerados anteriormente.  
  
     De forma predeterminada, este método provoca el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>eventos siempre y cuando no hay un depurador asociado y la aplicación está controlando el `UnhandledException` eventos.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>  
  
 Si la aplicación es una aplicación de instancia única y la aplicación ya se está ejecutando, llama a la instancia subsiguiente de la aplicación la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>método en la instancia original de la aplicación y, a continuación, sale.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>  
  
 El <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>llamadas al constructor el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>propiedad para determinar qué motor de representación de texto que se utilizará para los formularios de la aplicación.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> De forma predeterminada, el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>devuelve `False`, que indica que se utiliza el motor de representación de texto GDI, que es el valor predeterminado en [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)].</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> Puede invalidar el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>para devolver `True`, que indica que se usa el motor de representación de texto GDI +, que es el valor predeterminado en Visual Basic .NET 2002 y Visual Basic .NET 2003.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>  
  
## <a name="configuring-the-application"></a>Configuración de la aplicación  
 Como parte de la [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] modelo de aplicación, la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>clase suministra propiedades protegidas que configuran la aplicación.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> Estas propiedades se deben establecer en el constructor de la clase de implementación.  
  
 En un proyecto de formularios Windows Forms de forma predeterminada, el **Project Designer** crea código para establecer las propiedades con la configuración del diseñador. Las propiedades se utilizan únicamente cuando se está iniciando la aplicación; establecerlas después de iniciarse la aplicación no tiene ningún efecto.  
  
|Propiedad|Determina|Configuración en el panel aplicación del Diseñador de proyectos|  
|---|---|---|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|Si la aplicación se ejecuta como una aplicación de instancia única o varias instancias.|**Convertir aplicación de instancia única** casilla de verificación|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|Si la aplicación utilizará los estilos visuales que coinciden con Windows XP.|**Habilitar estilos visuales de XP** casilla de verificación|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|Si la aplicación guarda automáticamente los cambios de configuración de usuario de la aplicación cuando se cierra la aplicación.|**Guardar My.Settings al cerrar** casilla de verificación|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|¿Qué hace que la aplicación finalice, por ejemplo, cuando se cierra el formulario de inicio o cuando se cierra el último formulario.|**Modo de apagado** lista|  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 [Información general sobre el modelo de aplicación de Visual Basic](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)   
 [Página de aplicación, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)
