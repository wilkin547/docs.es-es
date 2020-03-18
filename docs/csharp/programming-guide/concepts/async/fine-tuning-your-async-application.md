---
title: Ajustar una aplicación asincrónica (C#)
ms.date: 07/20/2015
ms.assetid: 97696eb9-81fc-4940-9655-84daa8eb4d5c
ms.openlocfilehash: cff50e62ff62b70e97e7ea6e03714326d774e407
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73970238"
---
# <a name="fine-tuning-your-async-application-c"></a>Ajustar una aplicación asincrónica (C#)
Puede agregar precisión y flexibilidad a sus aplicaciones asincrónicas mediante los métodos y las propiedades que el tipo <xref:System.Threading.Tasks.Task> pone a su disposición. Los temas de esta sección muestran ejemplos que usan <xref:System.Threading.CancellationToken> y métodos `Task` importantes como <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.  
  
 Con `WhenAny` y `WhenAll`, puede iniciar más fácilmente varias tareas y esperar su finalización mediante la supervisión de una sola tarea.  
  
- `WhenAny` devuelve una tarea que se completa cuando se complete cualquier tarea de una colección.  
  
     Para obtener ejemplos del uso de `WhenAny`, vea [Cancelar las tareas asincrónicas restantes cuando se completa una (C#)](./cancel-remaining-async-tasks-after-one-is-complete.md) y [Iniciar varias tareas asincrónicas y procesarlas a medida que se completan (C#)](./start-multiple-async-tasks-and-process-them-as-they-complete.md).  
  
- `WhenAll` devuelve una tarea que se completa cuando se completen todas las tareas de una colección.  
  
     Para obtener más información y un ejemplo del uso de `WhenAll`, vea [Procedimiento para ampliar el tutorial de async usando Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).
  
 Esta sección contiene los siguientes ejemplos:  
  
- [Cancelar una tarea asincrónica o una lista de tareas (C#)](./cancel-an-async-task-or-a-list-of-tasks.md).  
  
- [Cancelar tareas asincrónicas tras un período de tiempo (C#)](./cancel-async-tasks-after-a-period-of-time.md)  
  
- [Cancelar las tareas asincrónicas restantes cuando se completa una (C#)](./cancel-remaining-async-tasks-after-one-is-complete.md)  
  
- [Iniciar varias tareas asincrónicas y procesarlas a medida que se completan (C#)](./start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
> Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior, y .NET Framework 4.5 o posterior, instalado en el equipo.  
  
 Los proyectos crean una interfaz de usuario que contiene un botón que inicia el proceso y un botón que lo cancela, tal como se muestra en la imagen siguiente. Los botones se denominan `startButton` y `cancelButton`.  
  
 ![Ventana de WPF con el botón Cancelar](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Cuadro de diálogo con un botón de inicio y detención")  
  
 Puede descargar los proyectos completos de Windows Presentation Foundation (WPF) de [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo Async: Ajustar la aplicación).  
  
## <a name="see-also"></a>Vea también

- [Asynchronous Programming with async and await (C#)](./index.md) (Programación asincrónica con async y await (C#))
