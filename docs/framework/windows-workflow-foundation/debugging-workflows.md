---
title: Depurar flujos de trabajo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 857f227d8541687768f470633e5430aee2171ea8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="debugging-workflows"></a>Depurar flujos de trabajo
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] proporciona varias opciones para depurar los flujos de trabajo en ejecución del entorno de desarrollo. Los flujos de trabajo se pueden depurar en el diseñador, en XAML y en el código.  
  
## <a name="debugging-in-the-workflow-designer"></a>Depuración en el Diseñador de flujo de trabajo  
 Los puntos de interrupción pueden establecerse en actividades en el Diseñador de flujo de trabajo ya sea resaltando la actividad y presionando **F9** o mediante el menú contextual de la actividad. A continuación, la ejecución del flujo de trabajo se interrumpe cuando el host del flujo de trabajo se ejecuta en modo de depuración. En la siguiente captura de pantalla, la ejecución del flujo de trabajo se para momentáneamente en un punto de interrupción. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Depurar flujos de trabajo con el Diseñador de flujo de trabajo](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer).  
  
## <a name="debugging-in-xaml"></a>Depurar en XAML  
 Si un flujo de trabajo se ha detenido momentáneamente en un punto de interrupción en el diseñador, el flujo de trabajo también se puede depurar en XAML. Para ver el punto de ejecución en XAML, seleccione **vista XAML** en el Diseñador de flujo de trabajo cuando se pausa la ejecución de flujo de trabajo. La depuración se puede volver a cambiar en el diseñador mediante la reapertura del flujo de trabajo en el diseñador desde el explorador de soluciones. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Cómo: depurar código XAML con el Diseñador de flujo de trabajo](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer).  
  
## <a name="debugging-in-code"></a>Depurar en el código  
 Los puntos de interrupción de código se pueden usar en [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] del mismo modo que se pueden usar en otras aplicaciones imperativas. Haga clic en el margen izquierdo del panel de código para crear un punto de interrupción de código, o bien presione **F9** para colocar un punto de interrupción en la ubicación del cursor.  
  
## <a name="attaching-to-a-workflow-process"></a>Adjuntar a un proceso de flujo de trabajo  
 La depuración del flujo de trabajo también admite el uso de la infraestructura de Visual Studio para adjuntar a un proceso. De esta forma se permite que el autor del flujo de trabajo depure un flujo de trabajo que se ejecuta en un entorno de host diferente como Internet Information Services (IIS) 7.0.  
  
## <a name="remote-debugging"></a>Depuración remota  
 La depuración remota de [!INCLUDE[wf](../../../includes/wf-md.md)] funciona de la misma forma que la depuración remota de otros componentes de [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]. Para obtener información sobre cómo usar la depuración remota, vea [Cómo: habilitar la depuración remota](http://go.microsoft.com/fwlink/?LinkId=196257).  
  
> [!NOTE]
>  Si la aplicación de flujo de trabajo tiene como destino el x86 arquitectura y se hospeda en un equipo que ejecuta un sistema operativo de 64 bits, la depuración remota no funcionará a menos que [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] esté instalado en el equipo remoto o el destino de la aplicación de flujo de trabajo se cambie para **cualquier CPU**.  
  
## <a name="extending-the-workflow-debugging-service"></a>Extender el servicio de depuración del flujo de trabajo  
 El servicio de depurador de flujo de trabajo es público ahora y se puede usar para crear aplicaciones personalizadas como supervisión, simulación y depuración en un diseñador re-hospedado. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] el tema <xref:System.Activities.Presentation.Debug.DebuggerService>.
