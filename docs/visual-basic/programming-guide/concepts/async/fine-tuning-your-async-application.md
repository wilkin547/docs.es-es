---
title: Ajustar una aplicación asincrónica
ms.date: 07/20/2015
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
ms.openlocfilehash: 51786993cf16cd12b39cde3d47832191b3fdca8d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345834"
---
# <a name="fine-tuning-your-async-application-visual-basic"></a>Ajustar la aplicación asincrónica (Visual Basic)
Puede agregar precisión y flexibilidad a sus aplicaciones asincrónicas mediante los métodos y las propiedades que el tipo <xref:System.Threading.Tasks.Task> pone a su disposición. Los temas de esta sección muestran ejemplos que usan <xref:System.Threading.CancellationToken> y métodos `Task` importantes como <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.  
  
 Con `WhenAny` y `WhenAll`, puede iniciar más fácilmente varias tareas y esperar su finalización mediante la supervisión de una sola tarea.  
  
- `WhenAny` devuelve una tarea que se completa cuando se complete cualquier tarea de una colección.  
  
     Para obtener ejemplos que usan `WhenAny`, consulte [cancelar las tareas asincrónicas restantes una vez completado (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)e [iniciar varias tareas asincrónicas y procesarlas a medida que se completan (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).  
  
- `WhenAll` devuelve una tarea que se completa cuando se completen todas las tareas de una colección.  
  
     Para obtener más información y un ejemplo que usa `WhenAll`, consulte [Cómo: extender el tutorial de Async mediante Task. WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
 Esta sección contiene los siguientes ejemplos:  
  
- [Cancelar una tarea asincrónica o una lista de tareas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).  
  
- [Cancelar tareas asincrónicas después de un período de tiempo (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
- [Cancelar las tareas asincrónicas restantes una vez completada una (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
- [Iniciar varias tareas asincrónicas y procesarlas a medida que se completan (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
> Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior instalados en el equipo.  
  
 Los proyectos crean una interfaz de usuario que contiene un botón que inicia el proceso y un botón que lo cancela, tal como se muestra en la imagen siguiente. Los botones se denominan `startButton` y `cancelButton`.  
  
 ![Ventana de WPF con el botón Cancelar](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Cuadro de diálogo con un botón de inicio y detención")  
  
 Puede descargar los proyectos completos de Windows Presentation Foundation (WPF) de [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo Async: Ajustar la aplicación).  
  
## <a name="see-also"></a>Vea también

- [Programación asincrónica con Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
