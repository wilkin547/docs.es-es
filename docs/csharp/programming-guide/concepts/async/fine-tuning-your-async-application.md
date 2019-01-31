---
title: Ajustar una aplicación asincrónica (C#)
ms.date: 07/20/2015
ms.assetid: 97696eb9-81fc-4940-9655-84daa8eb4d5c
ms.openlocfilehash: f33a06a181b44fc15ed2de81c4ceb385023a6fe5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601953"
---
# <a name="fine-tuning-your-async-application-c"></a>Ajustar una aplicación asincrónica (C#)
Puede agregar precisión y flexibilidad a sus aplicaciones asincrónicas mediante los métodos y las propiedades que el tipo <xref:System.Threading.Tasks.Task> pone a su disposición. Los temas de esta sección muestran ejemplos que usan <xref:System.Threading.CancellationToken> y métodos `Task` importantes como <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.  
  
 Con `WhenAny` y `WhenAll`, puede iniciar más fácilmente varias tareas y esperar su finalización mediante la supervisión de una sola tarea.  
  
-   `WhenAny` devuelve una tarea que se completa cuando se complete cualquier tarea de una colección.  
  
     Para obtener ejemplos del uso de `WhenAny`, vea [Cancel Remaining Async Tasks after One Is Complete (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) (Cancelar las tareas asincrónicas restantes cuando se completa una (C#)) y [Start Multiple Async Tasks and Process Them As They Complete (C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md) (Iniciar varias tareas asincrónicas y procesarlas a medida que se completan (C#)).  
  
-   `WhenAll` devuelve una tarea que se completa cuando se completen todas las tareas de una colección.  
  
     Para obtener más información y un ejemplo de código en el que se usa `WhenAll`, vea [Cómo: Ampliar el tutorial de Async usando Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
 Esta sección contiene los siguientes ejemplos:  
  
-   [Cancelar una tarea asincrónica o una lista de tareas (C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).  
  
-   [Cancelar tareas asincrónicas tras un período de tiempo (C#)](../../../../csharp/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [Cancelar las tareas asincrónicas restantes cuando se completa una (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [Iniciar varias tareas asincrónicas y procesarlas a medida que se completan (C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior instalados en el equipo.  
  
 Los proyectos crean una interfaz de usuario que contiene un botón que inicia el proceso y un botón que lo cancela, tal como se muestra en la imagen siguiente. Los botones se denominan `startButton` y `cancelButton`.  
  
 ![Ventana de WPF con el botón Cancelar](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "Cancelación")  
  
 Puede descargar los proyectos completos de Windows Presentation Foundation (WPF) desde [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo de async: Ajuste de la aplicación).  
  
## <a name="see-also"></a>Vea también

- [Programación asincrónica con Async y Await (C#)](../../../../csharp/programming-guide/concepts/async/index.md)
