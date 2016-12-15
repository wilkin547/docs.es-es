---
title: "Depurar la aplicaci&#243;n de Visual Basic | Microsoft Docs"
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
  - "depurar [Visual Basic], tareas comunes"
ms.assetid: 904760b8-9fe9-42a7-9d65-d93774253219
caps.latest.revision: 28
caps.handback.revision: 28
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Depurar la aplicaci&#243;n de Visual Basic
[!INCLUDE[vs2017banner](../../csharp/includes/vs2017banner.md)]

Esta página proporciona vínculos a la documentación sobre las características de depuración que están integradas en [!INCLUDE[vsprvs](../../csharp/includes/vsprvs_md.md)].  Por ejemplo, puede encontrar errores semánticos en la aplicación observando su comportamiento en tiempo de ejecución en el propio depurador.  
  
 Con el depurador puede examinar el contenido de las variables de la aplicación sin insertar llamadas adicionales a funciones que lo muestren.  De la misma forma, puede insertar un punto de interrupción en el código para detener la ejecución en el punto que especifique.  
  
## Controlar la ejecución  
 En la tabla siguiente se muestran las tareas de depuración que implican un control de la ejecución y se proporcionan vínculos a las páginas de Ayuda asociadas.  
  
|||  
|-|-|  
|Para|Vea|  
|Empezar a depurar un proyecto de Visual Studio, adjuntarlo a un proceso, interrupción en el código, recorrer el código, ejecutar hasta el cursor, ejecutar a una función en la pila de llamadas, establecer la siguiente instrucción, recorrer por Solo mi código, detener la depuración, reiniciar la depuración, o desasociarla de un proceso depurado.|[Desplazarse por el código con el depurador](/visual-studio/debugger/navigating-through-code-with-the-debugger)|  
|Especificar las configuraciones para las versiones de depuración y lanzamiento de un programa.|[Debug and Release Project Configurations](http://msdn.microsoft.com/es-es/0440b300-0614-4511-901a-105b771b236e)|  
|Establecer las opciones de inicio \(argumentos de la línea de comandos, directorio de trabajo, equipo remoto\)|[NIB: How to: Set Start Options for Application Debugging](http://msdn.microsoft.com/es-es/ce792058-7bac-4dd6-858b-466e872687b8)|  
|Depurar en tiempo de diseño.|[Tutorial: Depurar en tiempo de diseño](../Topic/Walkthrough:%20Debugging%20at%20Design%20Time.md)|  
|Habilitar la depuración Just\-In\-Time, que inicia el depurador de Visual Studio cuando un programa que se ejecuta fuera de Visual Studio se encuentra con un error irrecuperable.|[Depuración Just\-In\-Time](/visual-studio/debugger/just-in-time-debugging-in-visual-studio)|  
|Establezca puntos de interrupción de las líneas de código fuente, instrucciones de ensamblado y la función de la pila de llamadas.  Especificar las condiciones, los números de llamadas y la ubicación de la ejecución.|[Usar puntos de interrupción](/visual-studio/debugger/using-breakpoints)|  
  
## Controlar las excepciones  
 La tabla siguiente muestra las tareas de depuración que implican control de excepciones y señala las páginas de Ayuda asociadas.  
  
|||  
|-|-|  
|Para|Vea|  
|Interrumpir en excepciones no controladas.|[Cómo: Interrumpir en las excepciones no controladas por el usuario](../Topic/How%20to:%20Break%20on%20User-Unhandled%20Exceptions.md)|  
|Interrumpir cuando se produce una excepción.|[Cómo: Interrumpir cuando se produce una excepción](../Topic/How%20to:%20Break%20When%20an%20Exception%20is%20Thrown.md)|  
|Interrumpir en excepciones de primera oportunidad.|[Cómo: Interrumpir cuando se produce una excepción](../Topic/How%20to:%20Break%20When%20an%20Exception%20is%20Thrown.md)|  
|Utilizar el asistente de excepciones.|[How to: Correct Run\-Time Errors with the Exception Assistant](../Topic/How%20to:%20Correct%20Run-Time%20Errors%20with%20the%20Exception%20Assistant.md)|  
|Agregar una nueva excepción.|[Cómo: Agregar nuevas excepciones](../Topic/How%20to:%20Add%20New%20Exceptions.md)|  
|Continuar la ejecución después de que se ha producido una excepción.|[Continuar la ejecución después de una excepción](/visual-studio/debugger/continuing-execution-after-an-exception)|  
  
## Editar y continuar  
 La tabla siguiente muestra las tareas de depuración que implican Editar y continuar y señala las páginas de Ayuda asociadas.  
  
|||  
|-|-|  
|Para|Vea|  
|Activar y desactivar Editar y continuar.|[Cómo: Habilitar y deshabilitar Editar y continuar](../Topic/How%20to:%20Enable%20and%20Disable%20Edit%20and%20Continue.md)|  
|Impedir que Editar y continuar aplique cambios de código.|[Cómo: Detener cambios en el código](../Topic/How%20to:%20Stop%20Code%20Changes.md)|  
|Aplicar ediciones en modo de interrupción.|[Cómo: Aplicar tareas de edición en modo de interrupción con Editar y continuar](../Topic/How%20to:%20Apply%20Edits%20in%20Break%20Mode%20with%20Edit%20and%20Continue.md)|  
  
## Examinar datos de depuración  
 La tabla siguiente muestra las tareas de depuración que implican la consulta de datos de depuración y señala las páginas de Ayuda asociadas.  
  
|||  
|-|-|  
|Para|Vea|  
|Utilizar la ventana **Registros** para ver el contenido de los registros.|[Cómo: Utilizar la ventana Registros](../Topic/How%20to:%20Use%20the%20Registers%20Window.md)|  
|Utilizar la ventana **Pila de llamadas** para ver llamadas a funciones o procedimientos que están actualmente en la pila.|[Cómo: Utilizar la ventana Pila de llamadas](../Topic/How%20to:%20Use%20the%20Call%20Stack%20Window.md)|  
|Utilizar la ventana **Desensamblado** para ver el código ensamblador correspondiente a las instrucciones creadas por el compilador.|[Cómo: Utilizar la ventana Desensamblado](../Topic/How%20to:%20Use%20the%20Disassembly%20Window.md)|  
|Utilizar la ventana **Módulos** para mostrar y describir los módulos que utiliza el programa.|[Cómo: Utilizar la ventana Módulos](../Topic/How%20to:%20Use%20the%20Modules%20Window.md)|  
|Utilizar la ventana **Explorador de scripts** para mostrar archivos de script cargados actualmente en el programa.|[Cómo: Ver documentos de script](../Topic/How%20to:%20View%20Script%20Documents.md)|  
|Utilizar la ventana **Subprocesos** para examinar y controlar los subprocesos del programa.|[Cómo: Utilizar la ventana Subprocesos](../Topic/How%20to:%20Use%20the%20Threads%20Window.md)|  
  
## Vea también  
 [Tutorial: Depurar Windows Forms](../Topic/Walkthrough:%20Debugging%20a%20Windows%20Form.md)   
 [Depurar código administrado](/visual-studio/debugger/debugging-managed-code)   
 [Depuración de código nativo](/visual-studio/debugger/debugging-native-code)   
 [Depurar script y aplicaciones web](/visual-studio/debugger/debugging-web-applications-and-script)   
 [Depuración: referencia de la interfaz de usuario](/visual-studio/debugger/debugging-user-interface-reference)   
 [Preparación y configuración de la depuración](/visual-studio/debugger/debugger-settings-and-preparation)   
 [Conceptos básicos del depurador](/visual-studio/debugger/debugger-basics)   
 [Desplazarse por el código con el depurador](/visual-studio/debugger/navigating-through-code-with-the-debugger)   
 [Uso de IntelliTrace](/visual-studio/debugger/intellitrace)   
 [Tipos de proyectos de C\#, F\# y Visual Basic](../Topic/Debugging%20Preparation:%20C%23,%20F%23,%20and%20Visual%20Basic%20Project%20Types.md)   
 [Cómo: Aplicar tareas de edición en modo de interrupción con Editar y continuar](../Topic/How%20to:%20Apply%20Edits%20in%20Break%20Mode%20with%20Edit%20and%20Continue.md)