---
title: "BackgroundWorker (Componente) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "modelo asincrónico"
  - "operaciones en segundo plano"
  - "tareas en segundo plano"
  - "BackgroundWorker (componente)"
  - "componentes [Windows Forms], asincrónico"
  - "formularios, operaciones en segundo plano"
  - "formularios, multithreading"
  - "subprocesamiento [Windows Forms], operaciones en segundo plano"
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# BackgroundWorker (Componente)
El componente `BackgroundWorker` permite que el formulario o control ejecute operaciones de forma asincrónica.  
  
## En esta sección  
 [Información general sobre el componente BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 Describe el componente `BackgroundWorker`, que proporciona la posibilidad de ejecutar operaciones que llevan mucho tiempo de forma asincrónica \("en segundo plano"\), en un subproceso distinto del subproceso de la IU principal de la aplicación.  
  
 [Tutorial: Ejecutar una operación en segundo plano](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 Muestra cómo utilizar el componente `BackgroundWorker` en el diseñador para ejecutar operaciones que llevan mucho tiempo en un subproceso independiente.  
  
 [Cómo: Ejecutar una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 Muestra cómo utilizar el componente `BackgroundWorker` para ejecutar operaciones que llevan mucho tiempo en un subproceso independiente.  
  
 [Tutorial: Implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 Crea mediante el diseñador una aplicación que realice cálculos matemáticos de forma asincrónica.  
  
 [Cómo: Implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 Crea una aplicación que hace cálculos matemáticos de forma asincrónica.  
  
 [Cómo: Descargar un archivo en segundo plano](../../../../docs/framework/winforms/controls/how-to-download-a-file-in-the-background.md)  
 Muestra cómo utilizar el componente `BackgroundWorker` para descargar un archivo en un subproceso independiente.  
  
## Referencia  
 <xref:System.ComponentModel.BackgroundWorker>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 Describe el tipo que contiene los datos para el evento <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>.  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 Describe el tipo que contiene los datos para el evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>.  
  
## Secciones relacionadas  
 [Event\-based Asynchronous Pattern Overview](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 Describe cómo el modelo asincrónico pone a disposición las ventajas de las aplicaciones multiproceso a la vez que oculta muchos de los problemas complejos inherentes del diseño multiproceso.