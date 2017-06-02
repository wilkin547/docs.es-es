---
title: "Informaci&#243;n general sobre el componente BackgroundWorker | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BackgroundWorker"
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
ms.assetid: 64e9b3ab-7443-4a77-ab17-b8b8c0cb3f62
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Informaci&#243;n general sobre el componente BackgroundWorker
Muchas operaciones que se realizan habitualmente pueden tardar mucho tiempo en ejecutarse.  Por ejemplo:  
  
-   Descargas de imágenes  
  
-   Invocaciones de servicios web  
  
-   Descargas y cargas de archivos \(incluidas aplicaciones punto a punto\)  
  
-   Cálculos locales complejos  
  
-   Transacciones de bases de datos  
  
-   Acceso a disco local, debido a su baja velocidad con relación al acceso a la memoria  
  
 Operaciones como estas pueden hacer que la interfaz de usuario se bloquee mientras se están ejecutando.  Si quiere una interfaz de usuario con capacidad de respuesta y está sufriendo grandes retrasos asociados con estas operaciones, el componente <xref:System.ComponentModel.BackgroundWorker> ofrece una solución apropiada.  
  
 El componente <xref:System.ComponentModel.BackgroundWorker> le ofrece la posibilidad de ejecutar operaciones prolongadas de forma asincrónica \("en segundo plano"\), en un subproceso diferente del subproceso principal de la interfaz de usuario de la aplicación.  Para usar un <xref:System.ComponentModel.BackgroundWorker>, solo tiene que decirle qué método de trabajo prolongado debe ejecutar en segundo plano y, después, llame al método <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>.  El subproceso que realiza la llamada continúa ejecutándose normalmente mientras el método de trabajo se ejecuta asincrónicamente.  Cuando el método termina, el <xref:System.ComponentModel.BackgroundWorker> alerta al subproceso que realizó la llamada activando el evento <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> que, opcionalmente, contiene el resultado de la operación.  
  
 El componente <xref:System.ComponentModel.BackgroundWorker> está disponible en el **Cuadro de herramientas**, en la pestaña **Componentes**.  Para agregar un <xref:System.ComponentModel.BackgroundWorker> a su formulario, arrastre el componente <xref:System.ComponentModel.BackgroundWorker> al formulario.  Aparece en la bandeja de componentes, y sus propiedades aparecen en la ventana **Propiedades**.  
  
 Para iniciar la operación asincrónica, use el método <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>.  <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> toma un parámetro `object` opcional, que se puede usar para pasar argumentos al método de trabajo.  La clase <xref:System.ComponentModel.BackgroundWorker> expone el evento <xref:System.ComponentModel.BackgroundWorker.DoWork>, al que el subproceso de trabajo se asocia mediante un controlador de evento <xref:System.ComponentModel.BackgroundWorker.DoWork>.  
  
 El controlador de evento <xref:System.ComponentModel.BackgroundWorker.DoWork> toma un parámetro <xref:System.ComponentModel.DoWorkEventArgs>, que tiene una propiedad <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A>.  Esta propiedad recibe el parámetro de <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> y se puede pasar al método de trabajo, al que se llamará en el controlador de evento <xref:System.ComponentModel.BackgroundWorker.DoWork>.  En el ejemplo siguiente se muestra cómo asignar un resultado de un método de trabajo llamado `ComputeFibonacci`.  Forma parte de un ejemplo mayor, que encontrará en [Cómo: Implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 Para obtener más información sobre cómo usar controladores de evento, vea [Eventos](../../../../docs/standard/events/index.md).  
  
> [!CAUTION]
>  Cuando se usa multithreading de algún tipo, se expone a posibles errores muy graves y complejos.  Consulte [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) antes de implementar una solución que use multithreading.  
  
 Para más información sobre cómo usar la clase <xref:System.ComponentModel.BackgroundWorker>, vea [Cómo: Ejecutar una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).  
  
## Vea también  
 [NOT IN BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/es-es/c731a50c-09c1-4468-9646-54c86b75d269)   
 [Cómo: Implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)