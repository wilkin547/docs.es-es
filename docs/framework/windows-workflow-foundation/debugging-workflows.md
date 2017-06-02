---
title: "Depurar flujos de trabajo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Depurar flujos de trabajo
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] proporciona varias opciones para depurar los flujos de trabajo en ejecución del entorno de desarrollo.  Los flujos de trabajo se pueden depurar en el diseñador, en XAML y en el código.  
  
## Depuración en el Diseñador de flujo de trabajo  
 Los puntos de interrupción se pueden establecer en actividades en el diseñador de flujo de trabajo ya sea resaltando la actividad y presionando **F9** o usando el menú contextual de la actividad.  A continuación, la ejecución del flujo de trabajo se interrumpe cuando el host del flujo de trabajo se ejecuta en modo de depuración.  En la siguiente captura de pantalla, la ejecución del flujo de trabajo se para momentáneamente en un punto de interrupción.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Depurar flujos de trabajo con el Diseñador de flujo de trabajo](../Topic/Debugging%20Workflows%20with%20the%20Workflow%20Designer.md).  
  
## Depurar en XAML  
 Si un flujo de trabajo se ha detenido momentáneamente en un punto de interrupción en el diseñador, el flujo de trabajo también se puede depurar en XAML.  Para ver el punto de ejecución en XAML, seleccione **Vista XAML** en el diseñador de flujo de trabajo cuando se pausa la ejecución del flujo de trabajo.  La depuración se puede volver a cambiar en el diseñador mediante la reapertura del flujo de trabajo en el diseñador desde el explorador de soluciones.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Depurar XAML con el Diseñador de flujo de trabajo](../Topic/How%20to:%20Debug%20XAML%20with%20the%20Workflow%20Designer.md).  
  
## Depurar en el código  
 Los puntos de interrupción de código se pueden usar en [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] del mismo modo que se pueden usar en otras aplicaciones imperativas.  Haga clic en el margen izquierdo del panel de código para crear un punto de interrupción del código o presione **F9** para colocar un punto de interrupción en la ubicación del cursor.  
  
## Adjuntar a un proceso de flujo de trabajo  
 La depuración del flujo de trabajo también admite el uso de la infraestructura de Visual Studio para adjuntar a un proceso.  De esta forma se permite que el autor del flujo de trabajo depure un flujo de trabajo que se ejecuta en un entorno de host diferente como Internet Information Services \(IIS\) 7.0.  
  
## Depuración remota  
 La depuración remota de [!INCLUDE[wf](../../../includes/wf-md.md)] funciona de la misma forma que la depuración remota de otros componentes de [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)].  Para obtener información sobre cómo usar la depuración remota, vea el tema sobre [cómo habilitar la depuración remota](http://go.microsoft.com/fwlink/?LinkId=196257).  
  
> [!NOTE]
>  Si la aplicación de flujo de trabajo tiene como destino la arquitectura x86 y se hospeda en un equipo que ejecuta un sistema operativo de 64 bits, la depuración remota no funcionará a menos que [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] esté instalado en el equipo remoto o el destino de la aplicación de flujo de trabajo se cambie a **Cualquier CPU**.  
  
## Extender el servicio de depuración del flujo de trabajo  
 El servicio de depurador de flujo de trabajo es público ahora y se puede usar para crear aplicaciones personalizadas como supervisión, simulación y depuración en un diseñador re\-hospedado.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] el tema <xref:System.Activities.Presentation.Debug.DebuggerService>.