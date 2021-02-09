---
description: 'Más información acerca de: Información general sobre el modelo de aplicaciones de Visual Basic'
title: Información general sobre el modelo de aplicaciones de Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
ms.openlocfilehash: ead4912d3796a5826453945419510088d87c6e90
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797957"
---
# <a name="overview-of-the-visual-basic-application-model"></a>Información general sobre el modelo de aplicaciones de Visual Basic

Visual Basic proporciona un modelo bien definido para controlar el comportamiento de las aplicaciones de Windows Forms: el modelo de aplicación de Visual Basic. Este modelo incluye eventos para controlar el inicio y el cierre de la aplicación, así como eventos para detectar excepciones no controladas. También proporciona compatibilidad para desarrollar aplicaciones de instancia única. El modelo de aplicación es ampliable, por lo que los desarrolladores que necesiten un mayor control pueden personalizar sus métodos reemplazables.  
  
## <a name="uses-for-the-application-model"></a>Usos del modelo de aplicación  

 Una aplicación al uso necesita realizar tareas al iniciarse y al cerrarse. Por ejemplo, cuando se inicia, la aplicación puede mostrar una pantalla de presentación, establecer conexiones con bases de datos, cargar un estado guardado, etc. Y, cuando se cierra, puede finalizar esas conexiones de base de datos, guardar el estado actual, etc. Además, la aplicación puede ejecutar código específico si se cierra de forma inesperada, como durante una excepción no controlada.  
  
 El modelo de aplicación de Visual Basic permite crear una aplicación *de instancia única* fácilmente. Una aplicación de instancia única se distingue de una aplicación normal en que solo se puede ejecutar una instancia de la aplicación a la vez. Cualquier intento de iniciar otra instancia de una aplicación de instancia única dará como resultado el envío de una notificación a la instancia original (por medio del evento `StartupNextInstance`) para indicar que ha habido otro intento de inicio. Esta notificación incluye los argumentos de línea de comandos de la esa instancia posterior. Tras ello, la instancia posterior de la aplicación se cierra antes de que se pueda inicializarse.  
  
 Una aplicación de instancia única se inicia y comprueba si se trata de la primera instancia o de una instancia posterior de la aplicación:  
  
- Si es la primera instancia, se inicia como de costumbre.  
  
- Mientras esta primera instancia se está ejecutando, cualquier intento posterior de iniciar la aplicación da como resultado un comportamiento muy diferente. El siguiente intento notifica a la primera instancia sobre los argumentos de la línea de comandos y, seguidamente, finaliza. La primera instancia controla el evento `StartupNextInstance` para determinar cuáles eran los argumentos de la línea de comandos de la instancia posterior, y sigue ejecutándose.  
  
     En este diagrama se muestra cómo una instancia posterior señala a la primera instancia:  
  
     ![Diagrama que muestra una imagen de una aplicación de instancia única.](./media/overview-of-the-visual-basic-application-model/single-instance-application.gif)  
  
 Al controlar el evento `StartupNextInstance`, se puede controlar el comportamiento de la aplicación de instancia única. Por ejemplo, Microsoft Outlook suele ejecutarse como una aplicación de instancia única. Si Outlook se está ejecutando y se intenta volver a iniciar, el foco se desplaza a la instancia original, pero no se abre otra instancia.  
  
## <a name="events-in-the-application-model"></a>Eventos en el modelo de aplicación  

 En el modelo de aplicación podemos encontrar los siguientes eventos:  
  
- **Inicio de la aplicación**. La aplicación genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> cuando se inicia. Al controlar este evento, se puede agregar código que inicialice la aplicación antes de que el formulario principal se cargue. El evento `Startup` también permite cancelar la ejecución de la aplicación durante esa fase del proceso de inicio, si se quiere.  
  
     La aplicación se puede configurar para mostrar una pantalla de presentación mientras se ejecuta el código de inicio de la aplicación. El modelo de aplicación suprime de forma predeterminada la pantalla de presentación si se usa el argumento de línea de comandos `/nosplash` o `-nosplash`.  
  
- **Aplicaciones de instancia única**. El evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> se genera cuando se inicia una instancia posterior de una aplicación de instancia única. El evento pasa los argumentos de la línea de comandos de esa instancia posterior.  
  
- **Excepciones no controladas**. Si la aplicación detecta una excepción no controlada, genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>. El controlador de ese evento puede examinar la excepción y determinar si la ejecución puede proseguir.  
  
     El evento `UnhandledException` no se genera en algunas circunstancias. Para obtener más información, vea <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  
  
- **Cambios de conectividad de red**. Si la disponibilidad de la red del equipo cambia, la aplicación genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
     El evento `NetworkAvailabilityChanged` no se genera en algunas circunstancias. Para obtener más información, vea <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
- **Cierre de la aplicación**. La aplicación proporciona el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> para indicar cuándo se va a cerrar. Este controlador de eventos permite garantizar que se realicen todas las operaciones que la aplicación debe llevar a cabo (guardar y cerrar, por ejemplo). La aplicación se puede configurar para cerrarse cuando lo haga el formulario principal, o solamente cuando se cierren todos los formularios.  
  
## <a name="availability"></a>Disponibilidad  

 El modelo de aplicación Visual Basic está disponible de forma predeterminada para los proyectos de Windows Forms. Si la aplicación se configura para que use un objeto de inicio distinto o inicie el código de aplicación con un objeto `Sub Main` personalizado, puede que ese objeto o clase deba proporcionar una implementación de la clase <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> para usar el modelo de aplicación. Para más información sobre cómo cambiar el objeto de inicio, vea [Página de aplicación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Extensión del modelo de la aplicación de Visual Basic](../customizing-extending-my/extending-the-visual-basic-application-model.md)
