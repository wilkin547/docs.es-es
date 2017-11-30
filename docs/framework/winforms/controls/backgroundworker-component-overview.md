---
title: "Información general sobre el componente BackgroundWorker"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords: BackgroundWorker
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 64e9b3ab-7443-4a77-ab17-b8b8c0cb3f62
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f192081d9b7e30f10373342aef39443ff49e9931
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="backgroundworker-component-overview"></a>Información general sobre el componente BackgroundWorker
Muchas operaciones que se realizan habitualmente pueden tardar mucho tiempo en ejecutarse. Por ejemplo:  
  
-   Descargas de imágenes  
  
-   Invocaciones de servicios web  
  
-   Descargas y cargas de archivos (incluidas aplicaciones punto a punto)  
  
-   Cálculos locales complejos  
  
-   Transacciones de bases de datos  
  
-   Acceso a disco local, debido a su baja velocidad con relación al acceso a la memoria  
  
 Operaciones como estas pueden hacer que la interfaz de usuario se bloquee mientras se están ejecutando. Si quiere una interfaz de usuario con capacidad de respuesta y está sufriendo grandes retrasos asociados con estas operaciones, el componente <xref:System.ComponentModel.BackgroundWorker> ofrece una solución apropiada.  
  
 El componente <xref:System.ComponentModel.BackgroundWorker> le ofrece la posibilidad de ejecutar operaciones prolongadas de forma asincrónica ("en segundo plano"), en un subproceso diferente del subproceso principal de la interfaz de usuario de la aplicación. Para usar un <xref:System.ComponentModel.BackgroundWorker>, solo tiene que decirle qué método de trabajo prolongado debe ejecutar en segundo plano y, después, llame al método <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>. El subproceso que realiza la llamada continúa ejecutándose normalmente mientras el método de trabajo se ejecuta asincrónicamente. Cuando el método termina, el <xref:System.ComponentModel.BackgroundWorker> alerta al subproceso que realizó la llamada activando el evento <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> que, opcionalmente, contiene el resultado de la operación.  
  
 El <xref:System.ComponentModel.BackgroundWorker> componente está disponible en la **cuadro de herramientas**, en la **componentes** ficha. Para agregar un <xref:System.ComponentModel.BackgroundWorker> a su formulario, arrastre el componente <xref:System.ComponentModel.BackgroundWorker> al formulario. Aparece en la Bandeja de componentes y sus propiedades aparecen en la **propiedades** ventana.  
  
 Para iniciar la operación asincrónica, use el método <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>. <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> toma un parámetro `object` opcional, que se puede usar para pasar argumentos al método de trabajo. La clase <xref:System.ComponentModel.BackgroundWorker> expone el evento <xref:System.ComponentModel.BackgroundWorker.DoWork>, al que el subproceso de trabajo se asocia mediante un controlador de evento <xref:System.ComponentModel.BackgroundWorker.DoWork>.  
  
 El controlador de evento <xref:System.ComponentModel.BackgroundWorker.DoWork> toma un parámetro <xref:System.ComponentModel.DoWorkEventArgs>, que tiene una propiedad <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A>. Esta propiedad recibe el parámetro de <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> y se puede pasar al método de trabajo, al que se llamará en el controlador de evento <xref:System.ComponentModel.BackgroundWorker.DoWork>. En el ejemplo siguiente se muestra cómo asignar un resultado de un método de trabajo llamado `ComputeFibonacci`. Forma parte de un ejemplo más extenso, que puede encontrar en [Cómo: implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 Para obtener más información sobre el uso de controladores de eventos, vea [eventos](../../../../docs/standard/events/index.md).  
  
> [!CAUTION]
>  Cuando se usa multithreading de algún tipo, se expone a posibles errores muy graves y complejos. Vea [Procedimientos recomendados para el subprocesamiento administrado](../../../../docs/standard/threading/managed-threading-best-practices.md) antes de implementar cualquier solución que utilice multithreading.  
  
 Para obtener más información sobre el uso de la <xref:System.ComponentModel.BackgroundWorker> de clases, consulte [Cómo: ejecutar una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).  
  
## <a name="see-also"></a>Vea también  
 [NO está en la compilación: Multithreading en Visual Basic](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)  
 [Cómo: Implementar un formulario que utiliza una operación en segundo plano](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
