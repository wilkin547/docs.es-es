---
description: 'Más información sobre: Depurar flujos de trabajo'
title: Depurar flujos de trabajo
ms.date: 03/30/2017
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
ms.openlocfilehash: 9de65e580d47395a9528f4672014ceb491b09230
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742568"
---
# <a name="debugging-workflows"></a>Depurar flujos de trabajo

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] proporciona varias opciones para depurar los flujos de trabajo en ejecución del entorno de desarrollo. Los flujos de trabajo se pueden depurar en el diseñador, en XAML y en el código.

## <a name="debugging-in-the-workflow-designer"></a>Depuración en el Diseñador de flujo de trabajo

Los puntos de interrupción se pueden establecer en las actividades del diseñador de flujo de trabajo resaltando la actividad y presionando <kbd>F9</kbd> o utilizando el menú contextual de la actividad. A continuación, la ejecución del flujo de trabajo se interrumpe cuando el host del flujo de trabajo se ejecuta en modo de depuración. En la siguiente captura de pantalla, la ejecución del flujo de trabajo se para momentáneamente en un punto de interrupción. Para obtener más información, vea [Depurar flujos de trabajo con el diseñador de flujo de trabajo](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer).

## <a name="debugging-in-xaml"></a>Depurar en XAML

Si un flujo de trabajo se ha detenido momentáneamente en un punto de interrupción en el diseñador, el flujo de trabajo también se puede depurar en XAML. Para ver el punto de ejecución en XAML, seleccione **vista XAML** en el diseñador de flujo de trabajo cuando la ejecución del flujo de trabajo esté en pausa. La depuración se puede volver a cambiar en el diseñador mediante la reapertura del flujo de trabajo en el diseñador desde el explorador de soluciones. Para obtener más información, vea [Cómo: depurar XAML con el diseñador de flujo de trabajo](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer).

## <a name="debugging-in-code"></a>Depurar en el código

Para establecer un punto de interrupción, haga clic en el margen izquierdo del panel de código o presione <kbd>F9</kbd> con el cursor en la línea donde desea establecerlo.

## <a name="attaching-to-a-workflow-process"></a>Adjuntar a un proceso de flujo de trabajo

La depuración del flujo de trabajo también admite el uso de la infraestructura de Visual Studio para adjuntar a un proceso. De esta forma se permite que el autor del flujo de trabajo depure un flujo de trabajo que se ejecuta en un entorno de host diferente como Internet Information Services (IIS) 7.0.

## <a name="remote-debugging"></a>Depuración remota

La depuración remota de Windows Workflow Foundation (WF) es igual que la depuración remota de otros componentes de Visual Studio. Para obtener información sobre cómo usar la depuración remota, vea [Cómo: habilitar la depuración remota](/previous-versions/visualstudio/visual-studio-2010/febz73k0(v=vs.100)).

> [!NOTE]
> Si la aplicación de flujo de trabajo tiene como destino la arquitectura x86 y se hospeda en un equipo que ejecuta un sistema operativo de 64 bits, la depuración remota no funcionará a menos que Visual Studio esté instalado en el equipo remoto o el destino de la aplicación de flujo de trabajo se cambie a **cualquier CPU**.

## <a name="extending-the-workflow-debugging-service"></a>Extender el servicio de depuración del flujo de trabajo

El servicio de depurador de flujo de trabajo es público ahora y se puede usar para crear aplicaciones personalizadas como supervisión, simulación y depuración en un diseñador re-hospedado. Para obtener más información, vea el artículo <xref:System.Activities.Presentation.Debug.DebuggerService>.
