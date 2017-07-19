---
title: "Determinar la duraci&#243;n de la ejecuci&#243;n del flujo de trabajo mediante seguimiento | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f04ad0fd-edc7-4cbc-8979-356f2a1131c4
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Determinar la duraci&#243;n de la ejecuci&#243;n del flujo de trabajo mediante seguimiento
En este tema se muestra cómo determinar el tiempo que emplea en ejecutarse, usando el seguimiento de flujo de trabajo, un flujo de trabajo correctamente completado y autohospedado.  
  
### Determinar la duración de la ejecución de la aplicación de flujo de trabajo utilizando el seguimiento de flujo de trabajo  
  
1.  Abra [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].Seleccione **Archivo**, **Nuevo**, **Proyecto**.Bajo **C\#**, seleccione el nodo **Flujo de trabajo**.Seleccione **Aplicación de consola de flujos de trabajo** en la lista de plantillas.Asigne al nuevo proyecto el nombre `WorkflowDurationTracing` y haga clic en **Aceptar**.  
  
2.  Abra Workflow1.xaml.Arrastre una actividad <xref:System.Activities.Statements.Delay> a la superficie del diseñador.Asigne el valor 00:00:10 \(diez segundos\) a la propiedad Duration de la actividad.  
  
3.  Abra el Visor de eventos; para ello, haga clic en **Inicio** y en **Ejecutar**, y escriba `eventvwr.exe`.  
  
4.  Si no ha habilitado el seguimiento del flujo de trabajo, expanda **Registros de aplicaciones y servicios**, **Microsoft**, **Windows** y **Servidor de aplicaciones\-Aplicaciones**Seleccione **Ver**, **Mostrar registros analíticos y de depuración**.Haga clic con el botón secundario en **Depuración** y seleccione **Habilitar registro**.Deje abierto el Visor de eventos para que los seguimientos se puedan ver cuando se ejecute el flujo de trabajo.  
  
5.  Ejecute la aplicación de flujo de trabajo presionando CTRL\+SHIFT\+B.  
  
6.  En Visor de eventos, busque un evento reciente con el identificador 1009 y un mensaje similar al siguiente.Anote la hora en que se registró el mensaje.  
  
 **Parent Activity '', DisplayName: '', InstanceId: '' scheduled child Activity 'WorkflowDurationTracking.Workflow1', DisplayName: 'Workflow1', InstanceId: '1'.**  
  
7.  Busque otro evento reciente con identificador 1001 y un mensaje similar al siguiente.Reste el tiempo del mensaje anterior del valor Logged de este mensaje para determinarla duración de ejecución de flujo de trabajo, que debería ser alrededor de 10 segundos.  
  
 **WorkflowInstance Id: '1bbac57b\-3322\-498e\-9e27\-8833fda3a5bf' has completed in the Closed state.**  
  
## Vea también  
 [Traza del flujo de trabajo](../../../docs/framework/windows-workflow-foundation//workflow-tracing.md)   
 [Supervisión de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201273)   
 [Supervisión de aplicaciones con App Fabric](http://go.microsoft.com/fwlink/?LinkId=201275)