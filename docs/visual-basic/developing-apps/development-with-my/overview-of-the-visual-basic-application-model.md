---
title: Información general sobre el modelo de aplicaciones de Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
ms.openlocfilehash: aa47304cf2bded93bdb95ffe7dfa35bb37d9a643
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976459"
---
# <a name="overview-of-the-visual-basic-application-model"></a>Información general sobre el modelo de aplicaciones de Visual Basic

Visual Basic proporciona un modelo bien definido para controlar el comportamiento de las aplicaciones de Windows Forms: el modelo de aplicación de Visual Basic. Este modelo incluye eventos para controlar el inicio y el apagado de la aplicación, así como eventos para detectar excepciones no controladas. También proporciona compatibilidad para desarrollar aplicaciones de instancia única. El modelo de aplicación es extensible, por lo que los desarrolladores que necesitan más control pueden personalizar sus métodos reemplazables.  
  
## <a name="uses-for-the-application-model"></a>Usos del modelo de aplicación  

 Una aplicación típica necesita realizar tareas al iniciarse y cerrarse. Por ejemplo, cuando se inicia, la aplicación puede mostrar una pantalla de presentación, establecer conexiones con bases de datos, cargar un estado guardado, etc. Cuando se cierra la aplicación, puede cerrar las conexiones de base de datos, guardar el estado actual, etc. Además, la aplicación puede ejecutar código específico cuando la aplicación se cierra de forma inesperada, como durante una excepción no controlada.  
  
 El modelo de aplicación de Visual Basic facilita la creación de una aplicación *de instancia única* . Una aplicación de instancia única difiere de una aplicación normal en que solo se puede ejecutar una instancia de la aplicación a la vez. Un intento de iniciar otra instancia de una aplicación de una sola instancia da como resultado la notificación de la instancia original (por medio del evento `StartupNextInstance`) que se realizó otro intento de inicio. La notificación incluye los argumentos de línea de comandos de la instancia subsiguiente. A continuación, se cierra la instancia subsiguiente de la aplicación antes de que se pueda realizar cualquier inicialización.  
  
 Se inicia una aplicación de instancia única y comprueba si se trata de la primera instancia o de una instancia posterior de la aplicación:  
  
- Si es la primera instancia, se inicia como de costumbre.  
  
- Cada intento posterior de iniciar la aplicación, mientras se ejecuta la primera instancia, da como resultado un comportamiento muy diferente. El siguiente intento notifica a la primera instancia sobre los argumentos de la línea de comandos y, a continuación, sale inmediatamente. La primera instancia controla el evento `StartupNextInstance` para determinar qué son los argumentos de línea de comandos de la instancia subsiguiente y continúa ejecutándose.  
  
     En este diagrama se muestra cómo una instancia subsiguiente señala la primera instancia:  
  
     ![Diagrama que muestra una imagen de aplicación de una sola instancia.](./media/overview-of-the-visual-basic-application-model/single-instance-application.gif)  
  
 Al controlar el evento `StartupNextInstance`, puede controlar el comportamiento de la aplicación de instancia única. Por ejemplo, Microsoft Outlook normalmente se ejecuta como una aplicación de instancia única. Cuando Outlook se está ejecutando e intenta volver a iniciar Outlook, el enfoque se desplaza a la instancia original, pero no se abre otra instancia.  
  
## <a name="events-in-the-application-model"></a>Eventos en el modelo de aplicación  

 Los siguientes eventos se encuentran en el modelo de aplicación:  
  
- **Inicio**de la aplicación. La aplicación genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> cuando se inicia. Al controlar este evento, puede agregar código que inicialice la aplicación antes de que se cargue el formulario principal. El evento `Startup` también proporciona para cancelar la ejecución de la aplicación durante esa fase del proceso de inicio, si se desea.  
  
     Puede configurar la aplicación para mostrar una pantalla de presentación mientras se ejecuta el código de inicio de la aplicación. De forma predeterminada, el modelo de aplicación suprime la pantalla de presentación cuando se usa el argumento de línea de comandos `/nosplash` o `-nosplash`.  
  
- **Aplicaciones de una sola instancia**. El evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> se genera cuando se inicia una instancia subsiguiente de una aplicación de instancia única. El evento pasa los argumentos de línea de comandos de la instancia subsiguiente.  
  
- **Excepciones no controladas**. Si la aplicación encuentra una excepción no controlada, genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>. El controlador para ese evento puede examinar la excepción y determinar si se va a continuar la ejecución.  
  
     El evento `UnhandledException` no se genera en algunas circunstancias. Para obtener más información, vea <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  
  
- **Cambios de conectividad de red**. Si cambia la disponibilidad de la red del equipo, la aplicación genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
     El evento `NetworkAvailabilityChanged` no se genera en algunas circunstancias. Para obtener más información, vea <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
- **Cierre**de la aplicación. La aplicación proporciona el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> para indicar cuándo está a punto de cerrarse. En ese controlador de eventos, puede asegurarse de que se completan las operaciones que debe realizar la aplicación (cerrando y guardando, por ejemplo). Puede configurar la aplicación para que se cierre cuando se cierre el formulario principal, o para que se cierre solo cuando se cierren todos los formularios.  
  
## <a name="availability"></a>Disponibilidad  

 De forma predeterminada, el modelo de aplicación Visual Basic está disponible para los proyectos de Windows Forms. Si configura la aplicación para que use un objeto de inicio diferente, o inicia el código de aplicación con un `Sub Main`personalizado, ese objeto o clase puede necesitar proporcionar una implementación de la clase <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> para utilizar el modelo de aplicación. Para obtener información sobre cómo cambiar el objeto de inicio, vea [Página de aplicación, diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Extensión del modelo de la aplicación de Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
