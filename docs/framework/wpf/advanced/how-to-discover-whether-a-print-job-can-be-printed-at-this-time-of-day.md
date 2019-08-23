---
title: Procedimiento Detectar si un trabajo de impresión se puede imprimir en esta hora del día
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
ms.openlocfilehash: 859dc75169e443d07361951692a428507886fa2e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947809"
---
# <a name="how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day"></a>Procedimiento Detectar si un trabajo de impresión se puede imprimir en esta hora del día
Las colas de impresión no siempre están disponibles durante las 24 horas del día. Tienen propiedades de hora de inicio y de finalización que se pueden establecer para que no estén disponibles en determinados momentos del día. Esta característica se puede usar, por ejemplo, para reservar una impresora para el uso exclusivo de un determinado departamento después de las 5 P.M. Ese departamento tendría una cola diferente atendiendo a la impresora que usan otros departamentos. La cola de los demás departamentos se configuraría para que no estuviera disponible después de las 5 de la tarde, mientras que la cola del Departamento favorable podría estar configurada para estar disponible en todo momento.  
  
 Además, los trabajos de impresión se pueden configurar para que se puedan imprimir solo dentro de un intervalo de tiempo especificado.  
  
 Las <xref:System.Printing.PrintQueue> clases <xref:System.Printing.PrintSystemJobInfo> y que se exponen en las API de Microsoft .NET Framework proporcionan un medio para comprobar de forma remota si un trabajo de impresión determinado puede imprimir en una cola determinada en el momento actual.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente es un ejemplo que puede diagnosticar problemas con un trabajo de impresión.  
  
 Hay dos pasos principales para este tipo de función, como se indica a continuación.  
  
1. Lea las <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> propiedades <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> y de <xref:System.Printing.PrintQueue> para determinar si la hora actual está entre ellas.  
  
2. Lea las <xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A> propiedades <xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A> y de <xref:System.Printing.PrintSystemJobInfo> para determinar si la hora actual está entre ellas.  
  
 Pero surgen complicaciones del hecho de que estas propiedades no <xref:System.DateTime> son objetos. En su lugar, <xref:System.Int32> son objetos que expresan la hora del día como el número de minutos transcurridos desde la medianoche. Además, esto no es la medianoche en la zona horaria actual, sino la medianoche UTC (hora universal coordinada).  
  
 En el primer ejemplo de código se presenta el método estático **ReportQueueAndJobAvailability**, al <xref:System.Printing.PrintSystemJobInfo> que se pasa y se llama a los métodos auxiliares para determinar si el trabajo se puede imprimir en el momento actual y, de no ser así, cuando se puede imprimir. Observe que <xref:System.Printing.PrintQueue> no se pasa al método. Esto se debe <xref:System.Printing.PrintSystemJobInfo> a que incluye una referencia a la cola en <xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A> su propiedad.  
  
 Los métodos subordinados incluyen el método <xref:System.Printing.PrintSystemJobInfo> **ReportAvailabilityAtThisTime** sobrecargado, que puede tomar <xref:System.Printing.PrintQueue> o como un parámetro. También hay un **TimeConverter. ConvertToLocalHumanReadableTime**. Todos estos métodos se describen a continuación.  
  
 El método **ReportQueueAndJobAvailability** comienza comprobando si la cola o el trabajo de impresión no están disponibles en este momento. Si alguno de ellos no está disponible, comprueba para ver si la cola no está disponible. Si no está disponible, el método informa de este hecho y el momento en que la cola volverá a estar disponible. A continuación, comprueba el trabajo y, si no está disponible, informa del siguiente intervalo de tiempo en el que se puede imprimir. Por último, el método notifica la primera hora en que el trabajo puede imprimirse. Esta es la más reciente de las dos horas siguientes.  
  
- La hora a la que la cola de impresión está próximamente disponible.  
  
- La hora a la que está disponible el trabajo de impresión.  
  
 Al notificar las horas del día <xref:System.DateTime.ToShortTimeString%2A> , también se llama al método porque este método suprime los años, meses y días de la salida. No se puede restringir la disponibilidad de una cola de impresión o de un trabajo de impresión en determinados años, meses o días.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 Las dos sobrecargas del método **ReportAvailabilityAtThisTime** son idénticas, salvo por el tipo que se les pasa, por <xref:System.Printing.PrintQueue> lo que solo se muestra la versión siguiente.  
  
> [!NOTE]
> El hecho de que los métodos sean idénticos salvo el tipo produce la pregunta de por qué el ejemplo no crea un método genérico **\<ReportAvailabilityAtThisTime T >** . La razón es que este tipo de método tendría que estar restringido a una clase que tenga las propiedades **StartTimeOfDay** y **UntilTimeOfDay** a las que llama el método, pero un método genérico solo se puede restringir a una sola clase y la única clase común a ambos y en el árbol de herencia <xref:System.Printing.PrintSystemObject> es que no tiene tales propiedades. <xref:System.Printing.PrintSystemJobInfo> <xref:System.Printing.PrintQueue>  
  
 El método **ReportAvailabilityAtThisTime** (que se presenta en el ejemplo de código siguiente) comienza <xref:System.Boolean> inicializando una `true`variable Sentinel en. Se restablecerá a `false`si la cola no está disponible.  
  
 A continuación, el método comprueba si las horas de inicio y "hasta" son idénticas. Si es así, la cola siempre está disponible, por lo que el `true`método devuelve.  
  
 Si la cola no está disponible todo el tiempo, el método usa la propiedad <xref:System.DateTime.UtcNow%2A> estática para obtener la hora actual como un <xref:System.DateTime> objeto. (No se necesita la hora local porque las <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> propiedades <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> y sí mismas en la hora UTC).  
  
 Sin embargo, estas dos propiedades no <xref:System.DateTime> son objetos. Están <xref:System.Int32>expresando la hora como el número de minutos (después de la medianoche). Por lo tanto, tenemos que convertir <xref:System.DateTime> el objeto en minutos después de medianoche. Cuando esto se hace, el método simplemente comprueba si "Now" se encuentra entre el inicio de la cola y las horas "hasta", establece el centinela en false si "Now" no se encuentra entre las dos horas y devuelve el centinela.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 El método **TimeConverter. ConvertToLocalHumanReadableTime** (que se presenta en el ejemplo de código siguiente) no usa los métodos introducidos con Microsoft .NET Framework, por lo que la explicación es breve. El método tiene una tarea de conversión doble: debe tomar un entero que exprese minutos después de medianoche y convertirlo en un tiempo legible y debe convertirlo en la hora local. Para ello, crea primero un <xref:System.DateTime> objeto que se establece en la medianoche UTC y, a continuación, usa el <xref:System.DateTime.AddMinutes%2A> método para agregar los minutos que se pasaron al método. Esto devuelve un nuevo <xref:System.DateTime> que expresa la hora original pasada al método. Después <xref:System.DateTime.ToLocalTime%2A> , el método lo convierte en la hora local.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.DateTime>
- <xref:System.Printing.PrintSystemJobInfo>
- <xref:System.Printing.PrintQueue>
- [Documentos en WPF](documents-in-wpf.md)
- [Información general sobre impresión](printing-overview.md)
