---
title: Determinar la duración de la ejecución del flujo de trabajo mediante seguimiento
ms.date: 03/30/2017
ms.assetid: f04ad0fd-edc7-4cbc-8979-356f2a1131c4
ms.openlocfilehash: c51fdf4543939fc068092b84e02eeb5f52e77d6d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486286"
---
# <a name="determining-workflow-execution-duration-using-tracing"></a>Determinar la duración de la ejecución del flujo de trabajo mediante seguimiento
En este tema se muestra cómo determinar el tiempo que emplea en ejecutarse, usando el seguimiento de flujo de trabajo, un flujo de trabajo correctamente completado y autohospedado.  
  
### <a name="to-determine-workflow-application-execution-duration-by-using-workflow-tracing"></a>Determinar la duración de la ejecución de la aplicación de flujo de trabajo utilizando el seguimiento de flujo de trabajo  
  
1.  Abra [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  Seleccione **archivo**, **nueva**, **proyecto**.  En **C#**, seleccione el **flujo de trabajo** nodo.  Seleccione **aplicación de consola de flujos de trabajo** desde la lista de plantillas.  Asigne al nuevo proyecto `WorkflowDurationTracing` y haga clic en **Aceptar**.  
  
2.  Abra Workflow1.xaml.  Arrastre una actividad <xref:System.Activities.Statements.Delay> a la superficie del diseñador. Asigne el valor 00:00:10 (diez segundos) a la propiedad Duration de la actividad.  
  
3.  Abra el Visor de eventos, haga clic en **iniciar**, **ejecutar**y escriba `eventvwr.exe`.  
  
4.  Si no ha habilitado el seguimiento de flujo de trabajo, expanda **registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **aplicaciones de servidor de aplicaciones** . Seleccione **vista**, **mostrar analítico y depurar registros**. Haga clic en **depurar** y seleccione **Habilitar registro**. Deje abierto el Visor de eventos para que los seguimientos se puedan ver cuando se ejecute el flujo de trabajo.  
  
5.  Ejecute la aplicación de flujo de trabajo presionando CTRL+SHIFT+B.  
  
6.  En Visor de eventos, busque un evento reciente con el identificador 1009 y un mensaje similar al siguiente. Anote la hora en que se registró el mensaje.  
  
 **Primario de actividad '', DisplayName: '', InstanceId: '' secundaria programada actividad 'WorkflowDurationTracking.Workflow1', DisplayName: 'Workflow1', InstanceId: '1'.**  
  
7.  Busque otro evento reciente con identificador 1001 y un mensaje similar al siguiente.  Reste el tiempo del mensaje anterior del valor Logged de este mensaje para determinarla duración de ejecución de flujo de trabajo, que debería ser alrededor de 10 segundos.  
  
 **WorkflowInstance Id: '1bbac57b-3322-498e-9e27-8833fda3a5bf' ha completado en el estado Closed.**  
  
## <a name="see-also"></a>Vea también  
 [Traza de flujos de trabajo](../../../docs/framework/windows-workflow-foundation/workflow-tracing.md)  
 [Supervisión de Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=201273)  
 [Supervisión de aplicaciones con App Fabric](https://go.microsoft.com/fwlink/?LinkId=201275)
