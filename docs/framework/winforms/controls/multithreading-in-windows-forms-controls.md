---
title: "Subprocesamiento m&#250;ltiple en los controles de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "BackgroundWorker (componente)"
  - "BeginInvoke (método)"
  - "subprocesamiento [Windows Forms], controles"
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Subprocesamiento m&#250;ltiple en los controles de formularios Windows Forms
En muchas aplicaciones, puede hacer que la interfaz de usuario \(IIU\) tenga mayor capacidad de respuesta realizando las operaciones que llevan mucho tiempo en otro subproceso.  Varias herramientas están disponibles para el multithreading de los controles de formularios Windows Forms, incluido el espacio de nombres <xref:System.Threading>, el método <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=fullName> y el componente `BackgroundWorker`.  
  
> [!NOTE]
>  Aunque el componente `BackgroundWorker` reemplaza y agrega funcionalidad al espacio de nombres <xref:System.Threading> y al método <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=fullName>, éstos se conservan a efectos de compatibilidad con versiones anteriores y uso futuro, si se desea.  Para obtener más información, vea [Información general sobre el componente BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).  
  
## En esta sección  
 [Cómo: Realizar llamadas seguras para subprocesos en controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Muestra cómo hacer llamadas a controles de formularios Windows Forms seguras para la ejecución de subprocesos.  
  
 [Cómo: Utilizar un subproceso en segundo plano para buscar archivos](../../../../docs/framework/winforms/controls/how-to-use-a-background-thread-to-search-for-files.md)  
 Muestra cómo utilizar el espacio de nombres <xref:System.Threading> y el método <xref:System.Windows.Forms.Control.BeginInvoke%2A> para buscar de forma asincrónica los archivos.  
  
## Referencia  
 <xref:System.ComponentModel.BackgroundWorker>  
 Documenta un componente que encapsula un subproceso de trabajo para las operaciones asincrónicas.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Documenta cómo cargar de forma asincrónica un sonido.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Documenta cómo cargar de forma asincrónica una imagen.  
  
## Secciones relacionadas  
 [Cómo: Ejecutar una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 Muestra cómo realizar operaciones que llevan mucho tiempo con el componente <xref:System.ComponentModel.BackgroundWorker>.  
  
 [Información general sobre el componente BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 Proporciona temas que describen cómo utilizar el componente <xref:System.ComponentModel.BackgroundWorker> para las operaciones asincrónicas.