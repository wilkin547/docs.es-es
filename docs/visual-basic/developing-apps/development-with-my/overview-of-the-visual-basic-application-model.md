---
title: "Información general sobre el modelo de aplicación de Visual Basic | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My.Application object, Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
caps.latest.revision: 30
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
ms.openlocfilehash: 0925bb102c148480d82128b91cbf1762de24e7ec
ms.lasthandoff: 03/13/2017

---
# <a name="overview-of-the-visual-basic-application-model"></a>Información general sobre el modelo de aplicaciones de Visual Basic
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Proporciona un modelo bien definido para controlar el comportamiento de aplicaciones de Windows Forms: el [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] modelo de aplicación. Este modelo incluye eventos para controlar la aplicación inicio y cierre, así como eventos para capturar las excepciones no controladas. También se proporciona compatibilidad para desarrollar aplicaciones de instancia única. El modelo de aplicaciones es extensible, por lo que los desarrolladores que necesitan más control pueden personalizar sus métodos reemplazables.  
  
## <a name="uses-for-the-application-model"></a>Utiliza el modelo de aplicaciones de  
 Una aplicación típica necesita realizar tareas cuando se inicia y se cierra. Por ejemplo, cuando se inicia, la aplicación puede mostrar una pantalla de presentación, realizar conexiones de base de datos, cargar un estado guardado y así sucesivamente. Cuando se cierra la aplicación, puede cerrar las conexiones de base de datos, guardar el estado actual y así sucesivamente. Además, la aplicación puede ejecutar código específico cuando se cierra la aplicación hacia abajo de forma inesperada, tales como durante una excepción no controlada.  
  
 El [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] modelo de aplicación facilita la creación de un *instancia única* aplicación. Una aplicación de instancia única difiere de una aplicación normal en que sólo una instancia de la aplicación se puede ejecutar a la vez. Produce un intento de iniciar otra instancia de una aplicación de instancia única en la instancia original que se va a notificar, por medio de la `StartupNextInstance` eventos, que se realiza otro intento de inicio. La notificación incluye los argumentos de línea de comandos de la instancia subsiguiente. A continuación, se cierra la instancia subsiguiente de la aplicación antes de realizar cualquier inicialización.  
  
 Una aplicación de instancia única se inicia y comprueba si es la primera instancia o una posterior de la aplicación:  
  
-   Si es la primera instancia, se inicia como de costumbre.  
  
-   Cada intento posterior de iniciar la aplicación, mientras se ejecuta la primera instancia, produce un comportamiento muy diferente. El intento subsiguiente notifica a la primera instancia acerca de los argumentos de línea de comandos y, a continuación, sale inmediatamente. Los identificadores de la primera instancia del `StartupNextInstance` eventos para determinar qué estaban argumentos de línea de comandos de la instancia subsiguiente y continúa ejecutándose.  
  
     Este diagrama muestra cómo una instancia posterior indica la primera instancia.  
  
     ![Única imagen de aplicación de la instancia](../../../visual-basic/developing-apps/development-with-my/media/singleinstance.gif "SingleInstance")  
  
 Controlando la `StartupNextInstance` eventos, puede controlar cómo se comportará su aplicación de instancia única. Por ejemplo, Microsoft Outlook se ejecuta normalmente como una aplicación de instancia única; Cuando Outlook se ejecuta y se intenta iniciar Outlook nuevo, el foco se desplaza a la instancia original, pero no se abre otra instancia.  
  
## <a name="events-in-the-application-model"></a>Eventos en el modelo de aplicación  
 Los siguientes eventos se encuentran en el modelo de aplicación:  
  
-   **Inicio de la aplicación**. La aplicación se genera la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>eventos cuando se inicia.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> Controlando este evento, puede agregar código que inicializa la aplicación antes de que se carga el formulario principal. El `Startup` también proporciona eventos para cancelar la ejecución de la aplicación durante la fase del proceso de inicio, si lo desea.  
  
     Puede configurar la aplicación para mostrar una pantalla de presentación mientras se ejecuta el código de inicio de la aplicación. De forma predeterminada, el modelo de aplicaciones suprime la presentación de la pantalla cuando ya sea la `/nosplash` o `-nosplash` se utilizan los argumentos de línea de comandos.  
  
-   **Aplicaciones de instancia única**. El <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>evento se desencadena cuando se inicia una instancia subsiguiente de una aplicación de instancia única.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> El evento pasa los argumentos de línea de comandos de la instancia subsiguiente.  
  
-   **Las excepciones no controladas**. Si la aplicación encuentra una excepción no controlada, genera el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>eventos.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> El controlador para ese evento puede examinar la excepción y determinar si debe continuar la ejecución.  
  
     El `UnhandledException` en algunas circunstancias no se produce el evento. Para obtener más información, consulte <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>  
  
-   **Cambios de conectividad de red**. Si cambia la disponibilidad de la red del equipo, la aplicación genera la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>eventos.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
  
     El `NetworkAvailabilityChanged` en algunas circunstancias no se produce el evento. Para obtener más información, consulte <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
  
-   **Cerrar aplicación**. La aplicación proporciona el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>evento señalice cuando va a apagar.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> En ese evento controlador, puede asegurarse de que las operaciones de su aplicación necesita realizar, cerrar y guardar, por ejemplo, se han completado. Puede configurar la aplicación se apague cuando se cierra el formulario principal, o cerrar sólo cuando se cierran todos los formularios.  
  
## <a name="availability"></a>Disponibilidad  
 De forma predeterminada, la [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] modelo de aplicación está disponible para los proyectos de formularios Windows Forms. Si configure la aplicación para utilizar un objeto de inicio diferente, o iniciar el código de aplicación con un personalizado `Sub Main`, a continuación, dicho objeto o clase que necesite proporcionar una implementación de la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>clase para usar el modelo de aplicación.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> Para obtener información acerca de cómo cambiar el objeto de inicio, consulte [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 [Extensión del modelo de la aplicación de Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
