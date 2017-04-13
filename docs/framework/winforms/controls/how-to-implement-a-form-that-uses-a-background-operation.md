---
title: "C&#243;mo: Implementar un formulario que utiliza una operaci&#243;n en segundo plano | Microsoft Docs"
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
  - "BackgroundWorker (componente)"
  - "componentes [Windows Forms], asincrónico"
  - "formularios, operaciones en segundo plano"
  - "formularios, multithreading"
  - "subprocesamiento [Windows Forms], operaciones en segundo plano"
  - "subprocesamiento [Windows Forms], formularios"
ms.assetid: 9f483f93-1613-4be1-a021-b4934e9c78f3
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Implementar un formulario que utiliza una operaci&#243;n en segundo plano
El programa de ejemplo siguiente crea un formulario que calcula los números de Fibonacci.  El cálculo se ejecuta en un subproceso independiente del subproceso de interfaz de usuario, por lo que la interfaz de usuario sigue ejecutándose sin retrasos mientras se realiza el cálculo.  
  
 Visual Studio es altamente compatible con esta tarea.  
  
 Consulte también [Tutorial: Implementar un formulario que utiliza una operación en segundo plano](http://msdn.microsoft.com/library/b2zk6580\(v=vs.110\)).  
  
## Ejemplo  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo generar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Programación eficaz  
  
> [!CAUTION]
>  Cuando se usa multithreading de algún tipo, se expone a posibles errores muy graves y complejos.  consulte [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) antes de implementar cualquier solución que utilice el subprocesamiento múltiple.  
  
## Vea también  
 <xref:System.ComponentModel.BackgroundWorker>   
 <xref:System.ComponentModel.DoWorkEventArgs>   
 [Event\-based Asynchronous Pattern Overview](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)   
 [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md)