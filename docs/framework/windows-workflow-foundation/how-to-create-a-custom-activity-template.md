---
title: "C&#243;mo: Crear una plantilla de actividad personalizada | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# C&#243;mo: Crear una plantilla de actividad personalizada
Las plantillas de actividad personalizadas se utilizan para personalizar la configuración de actividades, incluidas las actividades compuestas personalizadas, para que los usuarios no tengan que crear cada actividad de forma individual y configurar propiedades y otros valores manualmente.Se puede hacer que estas plantillas personalizadas estén disponibles en el **Cuadro de herramientas** en [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] o desde un diseñador rehospedado, desde el que los usuarios pueden arrastrarlas hasta la superficie de diseño preconfigurada.[!INCLUDE[wfd2](../../../includes/wfd2-md.md)] se entrega con buenos ejemplos de esas plantillas: [Diseñador de plantillas SendAndReceiveReply](../Topic/SendAndReceiveReply%20Template%20Designer.md) y [Diseñador de plantillas ReceiveAndSendReply](../Topic/ReceiveAndSendReply%20Template%20Designer.md) en la categoría [Diseñadores de actividades de mensajería](../Topic/Messaging%20Activity%20Designers.md).  
  
 El primer procedimiento de este tema describe cómo crear una plantilla de actividad personalizada para una actividad **Delay** y el segundo procedimiento describe brevemente cómo ponerla a disposición de los usuarios en un [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] para comprobar que la plantilla personalizada funciona.  
  
 Las plantillas de actividad personalizadas deben implementar la <xref:System.Activities.Presentation.IActivityTemplateFactory>.La interfaz tiene un método <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> único con el que puede crear y configurar las instancias de actividad utilizadas en la plantilla.  
  
### Para crear una plantilla para la actividad Delay  
  
1.  Inicie [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  En el menú **Archivo**, elija **Nuevo** y después seleccione **Proyecto**.  
  
     Aparece el cuadro de diálogo **Nuevo proyecto**.  
  
3.  En el panel **Tipos de proyecto**, seleccione **Flujo de trabajo** en los proyectos **Visual C\#** o en las agrupaciones **Visual Basic** en función del lenguaje preferido.  
  
4.  En el panel **Plantillas**, seleccione **Biblioteca de actividades**.  
  
5.  En el cuadro **Nombre**, escriba `DelayActivityTemplate`.  
  
6.  Acepte los valores predeterminados de los cuadros de texto **Ubicación** y **Nombre de la solución** y, a continuación, haga clic en **Aceptar**.  
  
7.  Haga clic con el botón secundario en el directorio Referencias del proyecto DelayActivityTemplate en el **Explorador de soluciones** y elija **Agregar referencia** para abrir el **Agregar referencia**.  
  
8.  Vaya a la pestaña **.NET**, seleccione **PresentationFramework** en la columna **Nombre de componente** de la izquierda y haga clic en **Aceptar** para agregar una referencia al archivo PresentationFramework.dll.  
  
9. Repita este procedimiento para agregar referencias a los archivos System.Activities.Presentation.dll y WindowsBase.dll.  
  
10. Haga clic con el botón secundario en el proyecto DelayActivityTemplate en el **Explorador de soluciones** y elija **Agregar** y a continuación **Nuevo elemento** para abrir el cuadro de diálogo **Agregar nuevo elemento**.  
  
11. Seleccione la plantilla **Clase**, denomínela MyDelayTemplate y, a continuación, haga clic en **Aceptar**.  
  
12. Abra el archivo MyDelayTemplate.cs y agregue las siguientes instrucciones.  
  
    ```  
  
    //Namespaces added  
    using System.Activities;  
    using System.Activities.Statements;  
    using System.Activities.Presentation;  
    using System.Windows;  
  
    ```  
  
13. Implemente la interfaz <xref:System.Activities.Presentation.IActivityTemplateFactory> con la clase `MyDelayActivity` mediante el código siguiente.De esta manera configura el retraso para una duración de 10 segundos.  
  
    ```  
  
    public sealed class MyDelayActivity : IActivityTemplateFactory  
    {  
        public Activity Create(System.Windows.DependencyObject target)  
        {  
            return new System.Activities.Statements.Delay  
            {  
                DisplayName = "DelayActivityTemplate",  
                Duration = new TimeSpan(0, 0, 10)  
  
            };  
        }  
    }  
  
    ```  
  
14. Seleccione **Compilar solución** en el menú **Compilar** para generar el archivo DelayActivityTemplate.dll.  
  
### Para que la plantilla esté disponible en un Diseñador de flujo de trabajo  
  
1.  Haga clic con el botón secundario en la solución DelayActivityTemplate en el **Explorador de soluciones** y elija **Agregar** y a continuación **Nuevo proyecto** para abrir el cuadro de diálogo **Agregar nuevo proyecto**.  
  
2.  Seleccione la plantilla **Aplicación de consolas de flujo de trabajo**, denomínela `CustomActivityTemplateApp` y, a continuación, haga clic en **Aceptar**.  
  
3.  Haga clic con el botón secundario en el directorio Referencias del proyecto CustomActivityTemplateApp en el **Explorador de soluciones** y elija **Agregar referencia** para abrir el **Agregar referencia**.  
  
4.  Vaya a la pestaña **Proyectos**, seleccione **DelayActivityTemplate** en la columna **Nombre del proyecto** de la izquierda y haga clic en **Aceptar** para agregar una referencia al archivo DelayActivityTemplate.dll que creó en el primer procedimiento.  
  
5.  Haga clic con el botón secundario en el proyecto CustomActivityTemplateApp en el **Explorador de soluciones** y elija **Compilar** para compilar la aplicación.  
  
6.  En el **Explorador de soluciones**, haga clic con el botón secundario en el proyecto CustomActivityTemplateApp y elija **Establecer como proyecto de inicio**.  
  
7.  Seleccione **Iniciar sin depurar** en el menú **Depurar** y presione cualquier tecla para continuar cuando se pida confirmación en la ventana de cmd.exe.  
  
8.  Abra el archivo Workflow1.xaml y abra el **Cuadro de herramientas**.  
  
9. Busque la plantilla **MyDelayActivity** en la categoría **DelayActivityTemplate**.Arrástrela a la superficie de diseño.Confirme en la ventana **Propiedades** que la propiedad `Duration` se ha establecido en 10 segundos.  
  
## Ejemplo  
 El archivo MyDelayActivity.cs debería contener el siguiente código.  
  
```  
  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
//Namespaces added  
using System.Activities;  
using System.Activities.Statements;  
using System.Activities.Presentation;  
using System.Windows;  
  
namespace DelayActivityTemplate  
{  
    public sealed class MyDelayActivity : IActivityTemplateFactory  
    {  
        public Activity Create(System.Windows.DependencyObject target)  
        {  
            return new System.Activities.Statements.Delay  
            {  
                DisplayName = "DelayActivityTemplate",  
                Duration = new TimeSpan(0, 0, 10)  
  
            };  
        }  
    }  
}  
  
```  
  
## Vea también  
 <xref:System.Activities.Presentation.IActivityTemplateFactory>   
 [Personalizar la experiencia de diseño del flujo de trabajo](../../../docs/framework/windows-workflow-foundation//customizing-the-workflow-design-experience.md)