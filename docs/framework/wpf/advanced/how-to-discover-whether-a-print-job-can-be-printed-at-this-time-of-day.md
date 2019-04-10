---
title: Filtrar Detectar si un trabajo de impresión se puede imprimir en esta hora del día
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print queues [WPF], timing
- printers [WPF], availability
- print jobs [WPF], timing
ms.assetid: 7e9c8ec1-abf6-4b3d-b1c6-33b35d3c4063
ms.openlocfilehash: 7eed5400744f1010cbf52dc8d3b3d0bc24aa4371
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59326871"
---
# <a name="how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day"></a>Filtrar Detectar si un trabajo de impresión se puede imprimir en esta hora del día
Las colas de impresión no están siempre disponibles durante 24 horas al día. Tienen propiedades de tiempo de inicio y finalización que se pueden establecer para que no esté disponible en determinados momentos del día. Esta característica, por ejemplo, puede usarse para reservar una impresora para uso exclusivo de un determinado departamento después de las 5 P.M.. Ese departamento tendría una cola diferente, mantenimiento de la impresora que otros departamentos usar. La cola para los otros departamentos se establecería en estar disponible después de 5 P.M., mientras que la cola del departamento favorecido podría establecerse como disponible en todo momento.  
  
 Además, los propios trabajos de impresión se pueden establecer en ser imprimible solo dentro de un intervalo de tiempo especificado.  
  
 El <xref:System.Printing.PrintQueue> y <xref:System.Printing.PrintSystemJobInfo> clases se expongan en el [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] de Microsoft .NET Framework proporcionan un medio para la comprobación de forma remota si un determinado trabajo de impresión puede imprimir en una cola determinada en el momento actual.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente es un ejemplo que puede diagnosticar problemas con un trabajo de impresión.  
  
 Hay dos pasos principales para este tipo de función como se indica a continuación.  
  
1. Leer el <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> y <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> propiedades de la <xref:System.Printing.PrintQueue> para determinar si la hora actual es entre ellos.  
  
2. Leer el <xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A> y <xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A> propiedades de la <xref:System.Printing.PrintSystemJobInfo> para determinar si la hora actual es entre ellos.  
  
 Pero las complicaciones surgen del hecho de que estas propiedades no son <xref:System.DateTime> objetos. En su lugar, son <xref:System.Int32> objetos que expresan la hora del día como el número de minutos desde la medianoche. Además, esto no es medianoche en la zona horaria actual, pero la medianoche UTC (Coordinated Universal Time).  
  
 El primer ejemplo de código presenta el método estático **ReportQueueAndJobAvailability**, que se pasa un <xref:System.Printing.PrintSystemJobInfo> y llama a métodos auxiliares para determinar si puede imprimir el trabajo en el momento actual y, si no, cuando puede imprimir. Tenga en cuenta que un <xref:System.Printing.PrintQueue> no se pasa al método. Esto es porque el <xref:System.Printing.PrintSystemJobInfo> incluye una referencia a la cola en su <xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A> propiedad.  
  
 Los métodos subordinados incluyen sobrecargado **ReportAvailabilityAtThisTime** método que puede tomar un <xref:System.Printing.PrintQueue> o un <xref:System.Printing.PrintSystemJobInfo> como un parámetro. También hay un **TimeConverter.ConvertToLocalHumanReadableTime**. Todos estos métodos se describen a continuación.  
  
 El **ReportQueueAndJobAvailability** método comienza comprobando si la cola o el trabajo de impresión no está disponible en este momento. Si cualquiera de ellas está disponible, a continuación, comprueba para ver si la cola no está disponible. Si no está disponible, el método notifica este hecho y el tiempo cuando la cola volverá a estar disponible. A continuación, comprueba el trabajo y si no está disponible, notifica la próxima vez que abarcan cuando cuando puede imprimir. Por último, el método notifica la hora más temprana, cuando el trabajo puede imprimirse. Esto es una versión posterior de los siguientes dos veces.  
  
-   La próxima hora a la cola de impresión esté disponible.  
  
-   La hora cuando el trabajo de impresión a continuación está disponible.  
  
 Al informar de horas del día, la <xref:System.DateTime.ToShortTimeString%2A> también se llama al método porque este método suprime los años, meses y días a partir de la salida. No se puede restringir la disponibilidad de una cola de impresión o un trabajo de impresión para días, meses o años determinados.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 Las dos sobrecargas de los **ReportAvailabilityAtThisTime** método son idénticos salvo por el tipo pasado a ellas, por lo que solo el <xref:System.Printing.PrintQueue> versión se presenta a continuación.  
  
> [!NOTE]
>  El hecho de que los métodos son idénticos salvo por tipo plantea la pregunta de por qué el ejemplo no crea un método genérico **ReportAvailabilityAtThisTime\<T >**. El motivo es que este tipo de método tendría que estar restringido a una clase que tiene el **las StartTimeOfDay** y **UntilTimeOfDay** las propiedades que se llama al método, pero un método genérico solo pueden restringirse a un único de clase y la única clase comunes a ambos <xref:System.Printing.PrintQueue> y <xref:System.Printing.PrintSystemJobInfo> en la herencia es árbol <xref:System.Printing.PrintSystemObject> que no tiene ninguna propiedad de este tipo.  
  
 El **ReportAvailabilityAtThisTime** método (presentado en el ejemplo de código siguiente) comienza por inicializar un <xref:System.Boolean> variable centinela para `true`. Se restablecerá a `false`, si la cola no está disponible.  
  
 A continuación, el método comprueba si el inicio y "until" horas son idénticas. Si lo son, la cola siempre está disponible, por lo que devuelve el método `true`.  
  
 Si la cola no está disponible todo el tiempo, utiliza el método estático <xref:System.DateTime.UtcNow%2A> propiedad va a obtener la hora actual como un <xref:System.DateTime> objeto. (Hora local no es necesario porque el <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> y <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> son propiedades en hora UTC.)  
  
 Sin embargo, estas dos propiedades no son <xref:System.DateTime> objetos. Son <xref:System.Int32>expresan la hora como el número de minutos después de medianoche UTC. Por lo que tenemos que convertir nuestra <xref:System.DateTime> objeto en minutos después de medianoche. Cuando esté listo, el método simplemente comprueba ver si "ahora" está entre el inicio de la cola y "horas, Establece el centinela en false si"ahora"no está entre las dos horas y devuelve al centinela hasta".  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 El **TimeConverter.ConvertToLocalHumanReadableTime** método (presentado en el ejemplo de código siguiente) no utiliza ningún método introducido con Microsoft .NET Framework, por lo que el análisis es breve. El método tiene una tarea de conversión doble: debe tomar un entero que expresa minutos después de medianoche y convertirlo en un tiempo legible y que debe convertir a la hora local. Esto realiza creando primero un <xref:System.DateTime> objeto que está establecida en medianoche UTC y, a continuación, usa el <xref:System.DateTime.AddMinutes%2A> método para agregar los minutos que se pasaron al método. Esto devuelve un nuevo <xref:System.DateTime> expresa la hora original que se pasó al método. El <xref:System.DateTime.ToLocalTime%2A> método, a continuación, lo convierte en hora local.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.DateTime>
- <xref:System.Printing.PrintSystemJobInfo>
- <xref:System.Printing.PrintQueue>
- [Documentos en WPF](documents-in-wpf.md)
- [Información general sobre impresión](printing-overview.md)
