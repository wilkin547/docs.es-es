---
title: "C&#243;mo: Ejecutar una operaci&#243;n en segundo plano | Microsoft Docs"
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
  - "operaciones en segundo plano"
  - "tareas en segundo plano"
  - "subprocesos en segundo plano"
  - "BackgroundWorker (clase), ejemplos"
  - "formularios, operaciones en segundo plano"
  - "formularios, multithreading"
  - "subprocesamiento [Windows Forms], operaciones en segundo plano"
ms.assetid: 5b56e2aa-dc05-444f-930c-2d7b23f9ad5b
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Ejecutar una operaci&#243;n en segundo plano
Si tiene una operación que tarda mucho tiempo en completarse y no desea causar retrasos en la interfaz de usuario, puede utilizar la clase <xref:System.ComponentModel.BackgroundWorker> para ejecutar la operación en otro subproceso.  
  
 El ejemplo de código siguiente muestra cómo ejecutar en segundo plano una operación que consume mucho tiempo.  El formulario cuenta con los botones **Iniciar** y **Cancelar**.  Haga clic en el botón **Iniciar** para ejecutar una operación asincrónica.  Haga clic en el botón **Cancelar** para detener una operación asincrónica.  El resultado de cada operación se muestra en un elemento <xref:System.Windows.Forms.MessageBox>.  
  
 Hay una amplia compatibilidad para esta tarea en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
 Consulte también [Tutorial: Ejecutar una operación en segundo plano](http://msdn.microsoft.com/library/ms233672\(v=vs.110\)).  
  
## Ejemplo  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo generar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Vea también  
 <xref:System.ComponentModel.BackgroundWorker>   
 <xref:System.ComponentModel.DoWorkEventArgs>   
 [Cómo: Implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [BackgroundWorker \(Componente\)](../../../../docs/framework/winforms/controls/backgroundworker-component.md)