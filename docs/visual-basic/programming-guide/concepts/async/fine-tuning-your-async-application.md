---
title: "Ajustar una aplicación asincrónica (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7d0cac2fe7305031b93a375a08e785285a291320
ms.lasthandoff: 03/13/2017

---
# <a name="fine-tuning-your-async-application-visual-basic"></a>Ajustar una aplicación asincrónica (Visual Basic)
Puede agregar flexibilidad y precisión a sus aplicaciones asincrónicas mediante los métodos y propiedades que el <xref:System.Threading.Tasks.Task>tipo hace que estén disponible.</xref:System.Threading.Tasks.Task> Los temas de esta sección muestran ejemplos que utilizan <xref:System.Threading.CancellationToken>e importantes `Task` métodos como <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>y <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>.</xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName> </xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> </xref:System.Threading.CancellationToken>  
  
 Mediante el uso de `WhenAny` y `WhenAll`, puede iniciar varias tareas y esperar su finalización mediante la supervisión de una sola tarea más fácilmente.  
  
-   `WhenAny`Devuelve una tarea que se completa cuando se complete cualquier tarea en una colección.  
  
     Para obtener ejemplos que utilizan `WhenAny`, consulte [Cancelar restantes tareas asincrónicas, después de una completa (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)y [iniciar varias tareas asincrónicas y proceso de ellos como se completa (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).  
  
-   `WhenAll`Devuelve una tarea que se completa cuando se completan todas las tareas en una colección.  
  
     Para obtener más información y un ejemplo que utiliza `WhenAll`, consulte [Cómo: Extender la Async Walkthrough por usando Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
 Esta sección incluye los siguientes ejemplos.  
  
-   [Cancelar una tarea asincrónica o una lista de tareas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).  
  
-   [Cancelar tareas asincrónicas tras un período de tiempo (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [Cancelar las tareas asincrónicas restantes cuando se una completa (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [Iniciar varias tareas asincrónicas y procesarlas a medida que se completan (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior, instalado en el equipo.  
  
 Los proyectos de creación una interfaz de usuario que contiene un botón que inicia el proceso y un botón que cancela, tal como se muestra en la siguiente imagen. Los botones se denominan `startButton` y `cancelButton`.  
  
 ![Ventana de WPF con el botón Cancelar](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "cancelación")  
  
 Puede descargar los proyectos de Windows Presentation Foundation (WPF) completa de [ejemplo Async: bien para la optimización de la aplicación](http://go.microsoft.com/fwlink/?LinkId=255046).  
  
## <a name="see-also"></a>Vea también  
 [Programación asincrónica con Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
