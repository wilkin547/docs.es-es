---
title: "Informaci&#243;n general sobre el modelo de aplicaciones de Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Application (objeto), modelo de aplicación de Visual Basic"
  - "modelo de aplicación de Visual Basic"
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
caps.latest.revision: 30
caps.handback.revision: 30
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Informaci&#243;n general sobre el modelo de aplicaciones de Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona un modelo bien definido para controlar el comportamiento de aplicaciones de Windows Forms: el modelo de aplicaciones de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  Este modelo incluye eventos para controlar el inicio de la aplicación y su cierre, así como eventos para detectar las excepciones no controladas.  También proporciona compatibilidad para desarrollar aplicaciones de instancia única.  El modelo de aplicaciones es extensible, por lo que los desarrolladores que necesitan un mayor control pueden personalizar sus métodos reemplazables.  
  
## Usos del modelo de aplicaciones  
 Una aplicación típica necesita realizar tareas cuando se inicia y se cierra.  Por ejemplo, cuando se inicia, la aplicación puede mostrar una pantalla de presentación, realizar conexiones a bases de datos, cargar un estado guardado, etc.  Cuando la aplicación se cierra, puede cerrar las conexiones a bases de datos, guardar el estado actual, etc.  Además, la aplicación puede ejecutar el código específico cuando se cierra inesperadamente, como por ejemplo durante una excepción no controlada.  
  
 El modelo de aplicaciones de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] facilita la creación de aplicaciones de *instancia única*.  Una aplicación de instancia única se diferencia de una aplicación normal en que sólo se puede ejecutar una instancia de la aplicación en un momento dado.  Al intentar iniciar otra instancia de una aplicación de instancia única se notifica a la instancia original \(por medio del evento `StartupNextInstance`\) que se ha intentado iniciar otra instancia de la aplicación.  La notificación incluye los argumentos de la línea de comandos de la instancia subsiguiente.  Entonces se cierra la instancia subsiguiente de la aplicación antes de que se pueda producir ninguna inicialización.  
  
 Se inicia una aplicación de instancia única y comprueba si es la primera instancia o una posterior de la aplicación:  
  
-   Si es la primera instancia, se inicia como de costumbre.  
  
-   Cada intento posterior de iniciar la aplicación, mientras está en ejecución la primera instancia, produce un comportamiento muy diferente.  El intento subsiguiente notifica a la primera instancia los argumentos de la línea de comandos y, a continuación, la cierra inmediatamente.  La primera instancia controla el evento `StartupNextInstance` para determinar cuáles eran los argumentos de línea de comandos de la instancia subsiguiente y continúa ejecutándose.  
  
     Este diagrama muestra cómo se señala una instancia subsiguiente a la primera instancia.  
  
     ![Imagen de aplicación de instancia única](../../../visual-basic/developing-apps/development-with-my/media/singleinstance.gif "SingleInstance")  
  
 Controlando el evento `StartupNextInstance` puede controlar el comportamiento de su aplicación de instancia única.  Por ejemplo, Microsoft Outlook se ejecuta normalmente como una aplicación de instancia única; cuando Outlook está en ejecución e intenta iniciar Outlook de nuevo, el foco pasa a la instancia original pero no se abre otra instancia.  
  
## Eventos del modelo de aplicaciones  
 En el modelo de aplicación se encuentran los eventos siguientes:  
  
-   **Inicio de la aplicación**.  La aplicación genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> cuando se inicia.  Controlando este evento, puede agregar código que inicialice la aplicación antes de que se cargue el formulario principal.  El evento `Startup` también sirve para cancelar la ejecución de la aplicación durante la fase del proceso de inicio, si así lo desea.  
  
     Puede configurar la aplicación para mostrar una pantalla de presentación mientras se ejecuta el código de inicio de la aplicación.  De manera predeterminada, el modelo de aplicaciones suprime la pantalla de presentación cuando se utilizan los argumentos de línea de comandos `/nosplash` o `-nosplash`.  
  
-   **Aplicaciones de instancia única**.  El evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> se genera cuando se inicia una instancia posterior de una aplicación de instancia única.  El evento pasa los argumentos de la línea de comandos de la instancia subsiguiente.  
  
-   **Excepciones no controladas**.  Si la aplicación encuentra una excepción no controlada, genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  Su controlador para ese evento puede examinar la excepción y determinar si se debe continuar la ejecución.  
  
     El evento `UnhandledException` no se provoca en determinadas circunstancias.  Para obtener más información, vea <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  
  
-   **Cambios en la conectividad de red**.  Si la disponibilidad de red del equipo cambia, la aplicación genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
     El evento `NetworkAvailabilityChanged` no se genera en determinadas circunstancias.  Para obtener más información, vea <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
-   **Cierre de la aplicación**.  La aplicación proporciona el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> para indicar cuándo está a punto de cerrarse.  En ese controlador de eventos, puede asegurarse de que se llevan a cabo las operaciones que debe realizar su aplicación \(cerrar y guardar, por ejemplo\).  Puede configurar su aplicación para que se cierre cuando se cierra el formulario principal, o que sólo se cierre cuando se hayan cerrado todos los formularios.  
  
## Disponibilidad  
 De forma predeterminada, el modelo de aplicaciones de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] está disponible para los proyectos de Windows Forms.  Si configura la aplicación para que utilice un objeto de inicio distinto, o para que inicie el código de la aplicación con un procedimiento `Sub Main` personalizado, puede que sea necesario que ese objeto o clase proporcione una implementación de la base <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> para utilizar el modelo de aplicaciones.  Para obtener información sobre cómo cambiar el objeto de inicio, vea [Aplicación \(Página, Diseñador de proyectos\) \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 [Ampliar el modelo de la aplicación de Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)