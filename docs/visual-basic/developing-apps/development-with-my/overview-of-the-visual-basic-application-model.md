---
title: Información general sobre el modelo de aplicaciones de Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
ms.openlocfilehash: 02cc71dbda47d078284d9a2ec07538dfa063ac75
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62014151"
---
# <a name="overview-of-the-visual-basic-application-model"></a>Información general sobre el modelo de aplicaciones de Visual Basic
Visual Basic ofrece un modelo bien definido para controlar el comportamiento de las aplicaciones de Windows Forms: el modelo de aplicación de Visual Basic. Este modelo incluye eventos para controlar la aplicación inicio y apagado, así como eventos para detectar las excepciones no controladas. También se proporciona soporte técnico para el desarrollo de aplicaciones de instancia única. El modelo de aplicación es extensible, por lo que los desarrolladores que necesitan más control pueden personalizar sus métodos reemplazables.  
  
## <a name="uses-for-the-application-model"></a>Usa para el modelo de aplicación  
 Debe realizar las tareas cuando se inicia y se cierra una aplicación típica. Por ejemplo, cuando se inicia, la aplicación puede mostrar una pantalla de presentación, establecer conexiones de base de datos, cargar un estado guardado y así sucesivamente. Cuando se cierra la aplicación, puede cerrar las conexiones de base de datos, guardar el estado actual y así sucesivamente. Además, la aplicación puede ejecutar código específico cuando se cierra la aplicación hacia abajo de forma inesperada, por ejemplo, como durante una excepción no controlada.  
  
 El modelo de aplicación de Visual Basic facilita la creación de un *instancia única* aplicación. Una aplicación de instancia única difiere de una aplicación normal en que se puede ejecutar solo una instancia de la aplicación a la vez. Da como resultado un intento de iniciar otra instancia de una aplicación de instancia única en la instancia original que se va a notificar, por medio de la `StartupNextInstance` eventos, que se realiza otro intento de inicio. La notificación incluye argumentos de línea de comandos de la instancia subsiguiente. A continuación, se cierra la instancia subsiguiente de la aplicación pueda llevar a cabo cualquier inicialización.  
  
 Una aplicación de instancia única se inicia y comprueba si es la primera instancia o una instancia subsiguiente de la aplicación:  
  
- Si es la primera instancia, se inicia como de costumbre.  
  
- Cada intento posterior para iniciar la aplicación, mientras se ejecuta la primera instancia, da como resultado un comportamiento muy diferente. El intento subsiguiente notifica a la primera instancia acerca de los argumentos de línea de comandos y, a continuación, sale inmediatamente. Los identificadores de la primera instancia el `StartupNextInstance` eventos para determinar qué argumentos de línea de comandos de la instancia subsiguiente estaban y continúa ejecutándose.  
  
     Este diagrama muestra cómo una instancia subsiguiente señala la primera instancia:  
  
     ![Diagrama que muestra una imagen de la aplicación de instancia única.](./media/overview-of-the-visual-basic-application-model/single-instance-application.gif)  
  
 Controlando la `StartupNextInstance` eventos, puede controlar cómo se comporta su aplicación de instancia única. Por ejemplo, Microsoft Outlook se ejecuta normalmente como una aplicación de instancia única; Cuando Outlook se ejecuta y se intenta iniciar Outlook nuevo, éste se desplaza a la instancia original pero no se abre otra instancia.  
  
## <a name="events-in-the-application-model"></a>Eventos en el modelo de aplicación  
 Los siguientes eventos se encuentran en el modelo de aplicación:  
  
- **Inicio de la aplicación**. La aplicación genera el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> evento cuando se inicia. Al controlar este evento, puede agregar código que inicializa la aplicación antes de carga el formulario principal. El `Startup` también proporciona eventos para cancelar la ejecución de la aplicación durante la fase del proceso de inicio, si lo desea.  
  
     Puede configurar la aplicación para mostrar una pantalla de presentación mientras se ejecuta el código de inicio de la aplicación. De forma predeterminada, el modelo de aplicación suprime la presentación de pantalla cuando tanto el `/nosplash` o `-nosplash` se usa el argumento de línea de comandos.  
  
- **Aplicaciones de instancia única**. El <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> evento se desencadena cuando se inicia una instancia subsiguiente de una aplicación de instancia única. El evento pasa los argumentos de línea de comandos de la instancia subsiguiente.  
  
- **Las excepciones no controladas**. Si la aplicación detecta una excepción no controlada, genera el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> eventos. El controlador para ese evento puede examinar la excepción y determinar si debe continuar la ejecución.  
  
     El `UnhandledException` en algunas circunstancias no provoca el evento. Para obtener más información, consulta <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  
  
- **Cambios de conectividad de red**. Si cambia la disponibilidad de la red del equipo, la aplicación genera el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged> eventos.  
  
     El `NetworkAvailabilityChanged` en algunas circunstancias no provoca el evento. Para obtener más información, consulta <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
- **Cerrar aplicación**. La aplicación proporciona el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> evento para indicar cuándo está a punto de apagar. En ese caso el controlador, puede asegurarse de que las operaciones de la aplicación necesita realizar, cerrar y guardar, por ejemplo, se han completado. Puede configurar la aplicación se cierre cuando se cierra el formulario principal, o apagar solo cuando se cierran todos los formularios.  
  
## <a name="availability"></a>Disponibilidad  
 De forma predeterminada, el modelo de aplicación de Visual Basic está disponible para los proyectos de Windows Forms. Si configurar la aplicación para usar un objeto de inicio diferente, o iniciar el código de aplicación con una personalizada `Sub Main`, a continuación, dicho objeto o clase que deba proporcionar una implementación de la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> clase se debe utilizar el modelo de aplicación. Para obtener información acerca de cómo cambiar el objeto de inicio, consulte [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Extensión del modelo de la aplicación de Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
