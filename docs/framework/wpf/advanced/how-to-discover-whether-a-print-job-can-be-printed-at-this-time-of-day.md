---
title: "Cómo: Detectar si un trabajo de impresión se puede imprimir en esta hora del día"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print queues [WPF], timing
- printers [WPF], availability
- print jobs [WPF], timing
ms.assetid: 7e9c8ec1-abf6-4b3d-b1c6-33b35d3c4063
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ac89b8dce67c95c78a5dd46e591d84730a68346
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day"></a>Cómo: Detectar si un trabajo de impresión se puede imprimir en esta hora del día
Las colas de impresión no están siempre disponibles para 24 horas al día. Tienen propiedades de tiempo de inicio y finalización que se pueden establecer para que no estén disponibles en determinados momentos del día. Esta característica se puede utilizar, por ejemplo, para reservar una impresora para uso exclusivo de un determinado departamento después de las 5 P.M.. Ese departamento tendría otra cola de servicio de la impresora que otros departamentos a usar. La cola de los demás departamentos se establecería en estar disponible después de las 5 P.M., mientras la cola del departamento favorecido podría establecerse como disponible en todo momento.  
  
 Además, pueden establecerse propios trabajos de impresión sea imprimible solo dentro de un intervalo de tiempo especificado.  
  
 El <xref:System.Printing.PrintQueue> y <xref:System.Printing.PrintSystemJobInfo> exponen las clases en el [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] de [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] proporcionan un medio para la comprobación de forma remota si un determinado trabajo de impresión puede imprimir en una cola determinada en el momento actual.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente es un ejemplo que puede diagnosticar problemas con un trabajo de impresión.  
  
 Hay dos pasos principales para este tipo de función, como se indica a continuación.  
  
1.  Leer la <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> y <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> propiedades de la <xref:System.Printing.PrintQueue> para determinar si es la hora actual entre ellos.  
  
2.  Leer la <xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A> y <xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A> propiedades de la <xref:System.Printing.PrintSystemJobInfo> para determinar si es la hora actual entre ellos.  
  
 Pero las complicaciones surgen del hecho de que estas propiedades no son <xref:System.DateTime> objetos. En su lugar, son <xref:System.Int32> objetos que expresan la hora del día como el número de minutos transcurridos desde la medianoche. Además, esto no es medianoche en la zona horaria actual, pero la medianoche UTC (hora Universal).  
  
 El primer ejemplo de código presenta el método estático **ReportQueueAndJobAvailability**, que se pasa un <xref:System.Printing.PrintSystemJobInfo> y llama a métodos auxiliares para determinar si puede imprimir el trabajo en el momento actual y, si no es así, cuando puede imprimir. Tenga en cuenta que un <xref:System.Printing.PrintQueue> no se pasa al método. Esto es porque el <xref:System.Printing.PrintSystemJobInfo> incluye una referencia a la cola en su <xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A> propiedad.  
  
 Los métodos subordinados incluyen sobrecargado **ReportAvailabilityAtThisTime** método que puede aceptar también un <xref:System.Printing.PrintQueue> o <xref:System.Printing.PrintSystemJobInfo> como un parámetro. También hay un **TimeConverter.ConvertToLocalHumanReadableTime**. Todos estos métodos se describen a continuación.  
  
 El **ReportQueueAndJobAvailability** método comienza comprobando si la cola o el trabajo de impresión no está disponible en este momento. Si alguno de ellos no está disponible, a continuación, comprueba para ver si la cola no está disponible. Si no está disponible, el método notifica este hecho y el tiempo cuando la cola volverá a estar disponible. A continuación, comprueba el trabajo y si no está disponible, notifica la próxima vez que abarcan cuando cuándo puede imprimir. Por último, el método notifica la primera hora cuando se puede imprimir el trabajo. Esto es una versión posterior de los siguientes dos veces.  
  
-   La próxima hora a la cola de impresión esté disponible.  
  
-   La próxima hora al trabajo de impresión esté disponible.  
  
 Cuando se notifican horas del día, la <xref:System.DateTime.ToShortTimeString%2A> también se llama al método porque este método suprime los años, meses y días a partir de la salida. No se puede restringir la disponibilidad de una cola de impresión o un trabajo de impresión a determinado años, meses o días.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 Las dos sobrecargas de la **ReportAvailabilityAtThisTime** método son idénticos salvo por el tipo que se les pasado, por lo que solo el <xref:System.Printing.PrintQueue> versión se muestra a continuación.  
  
> [!NOTE]
>  El hecho de que los métodos son idénticos, salvo por tipo provoca la pregunta de por qué el ejemplo no crea un método genérico **ReportAvailabilityAtThisTime\<T >**. La razón es que un método de este tipo tendría que limitarse a una clase que tiene el **las StartTimeOfDay** y **UntilTimeOfDay** propiedades que llama al método, pero un método genérico solo se puede restringir a un único clase y la única clase comunes a ambos <xref:System.Printing.PrintQueue> y <xref:System.Printing.PrintSystemJobInfo> en la herencia es árbol <xref:System.Printing.PrintSystemObject> que no tiene ninguna propiedad de este tipo.  
  
 El **ReportAvailabilityAtThisTime** método (que se presenta en el ejemplo de código siguiente) comienza inicializando una <xref:System.Boolean> variable centinela para `true`. Se restablecerá a `false`, si la cola no está disponible.  
  
 A continuación, el método comprueba si el inicio y "hasta" horas son idénticas. Si lo son, la cola siempre está disponible, por lo que el método devuelve `true`.  
  
 Si la cola no está disponible todo el tiempo, el método utiliza el método estático <xref:System.DateTime.UtcNow%2A> propiedad que se va a obtener la hora actual como un <xref:System.DateTime> objeto. (Hora local no es necesario porque el <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> y <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> son propiedades en hora UTC.)  
  
 Sin embargo, estas dos propiedades no son <xref:System.DateTime> objetos. Únicamente son <xref:System.Int32>s cuando el tiempo se expresan como el número de minutos después de medianoche de UTC. Por lo que se tiene que convertir nuestro <xref:System.DateTime> objeto a minutos después de medianoche. Una vez hecho, el método simplemente comprueba ver si "ahora" es entre el inicio de la cola y "horas, Establece el centinela en false si"ahora"no está entre los dos veces y devuelve al centinela hasta".  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 El **TimeConverter.ConvertToLocalHumanReadableTime** método (que se presenta en el ejemplo de código siguiente) no utiliza ningún método introducido con [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], por lo que el análisis es breve. El método tiene una tarea de conversión doble: debe tomar un entero que expresa minutos después de medianoche y convertirlo en una hora legible y debe convertir a la hora local. Para hacerlo, creando primero una <xref:System.DateTime> objeto que está establecida en medianoche UTC y, a continuación, utiliza el <xref:System.DateTime.AddMinutes%2A> método para agregar los minutos que se pasaron al método. Esto devuelve un nuevo <xref:System.DateTime> expresa la hora original que se pasó al método. El <xref:System.DateTime.ToLocalTime%2A> método, a continuación, lo convierte en hora local.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.DateTime>  
 <xref:System.Printing.PrintSystemJobInfo>  
 <xref:System.Printing.PrintQueue>  
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)
