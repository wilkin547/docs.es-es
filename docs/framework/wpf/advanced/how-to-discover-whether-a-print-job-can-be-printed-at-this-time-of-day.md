---
title: "C&#243;mo: Detectar si un trabajo de impresi&#243;n se puede imprimir en esta hora del d&#237;a | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "trabajos de impresión, control de tiempo"
  - "colas de impresión, control de tiempo"
  - "impresoras, disponibilidad"
ms.assetid: 7e9c8ec1-abf6-4b3d-b1c6-33b35d3c4063
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Detectar si un trabajo de impresi&#243;n se puede imprimir en esta hora del d&#237;a
Las colas de impresión no siempre están disponibles durante las 24 horas del día.  Tienen propiedades de hora inicial y final que se pueden establecer para que no estén disponibles en determinados momentos del día.  Por ejemplo, esta característica se puede utilizar para reservar una impresora para el uso exclusivo de un departamento determinado a partir de las 5.00 p.m.  Ese departamento tendría una cola diferente para dar servicio a la impresora que los demás departamentos.  La cola de los demás departamentos se establecería como no disponible después de las 5.00 p.m., mientras que la cola del departamento favorecido podría establecerse de modo que estuviera disponible en todo momento.  
  
 Además, se pueden establecer los propios trabajos de impresión para que únicamente puedan imprimirse en un intervalo de tiempo especificado.  
  
 Las clases <xref:System.Printing.PrintQueue> y <xref:System.Printing.PrintSystemJobInfo> expuestas en las [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] de [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] ofrecen un medio de comprobar de manera remota si un trabajo de impresión dado se puede imprimir en una cola determinada en cada momento.  
  
## Ejemplo  
 El ejemplo siguiente es capaz de diagnosticar los problemas con un trabajo de impresión.  
  
 Existen dos pasos principales para este tipo de función, que son los siguientes.  
  
1.  Lea las propiedades <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> y <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> del objeto <xref:System.Printing.PrintQueue> a fin de determinar si la hora actual se encuentra comprendida entre ellas.  
  
2.  Lea las propiedades <xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A> y <xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A> del objeto <xref:System.Printing.PrintSystemJobInfo> a fin de determinar si la hora actual se encuentra comprendida entre ellas.  
  
 No obstante, las complicaciones surgen del hecho de que estas propiedades no son objetos <xref:System.DateTime>.  En cambio, se trata de objetos <xref:System.Int32> que expresan la hora del día como el número de minutos transcurridos desde la medianoche.  Es más, no se trata de la medianoche en la zona horaria actual, sino de la medianoche según la hora universal coordinada \(UTC\).  
  
 En el primer ejemplo de código se presenta el método estático **ReportQueueAndJobAvailability**, al que se pasa un objeto <xref:System.Printing.PrintSystemJobInfo> y que llama a métodos auxiliares para determinar si el trabajo se puede imprimir en este momento y, en caso contrario, cuándo se puede hacer.  Observe que <xref:System.Printing.PrintQueue> no se pasa al método.  Esto se debe a que <xref:System.Printing.PrintSystemJobInfo> incluye una referencia a la cola en su propiedad <xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A>.  
  
 Los métodos subordinados incluyen el método sobrecargado **ReportAvailabilityAtThisTime**, que puede aceptar <xref:System.Printing.PrintQueue> o <xref:System.Printing.PrintSystemJobInfo> como parámetro.  También está el método **TimeConverter.ConvertToLocalHumanReadableTime**.  Todos estos métodos se describen más adelante.  
  
 El método **ReportQueueAndJobAvailability** comienza comprobando si la cola o el trabajo de impresión no están disponibles en este momento.  Si cualquiera de ellos no está disponible, comprueba si la cola no está disponible.  Si no está disponible, el método informa de ello y de la hora a la que la cola estará disponible de nuevo.  A continuación, comprueba el trabajo y, si no está disponible, informa del próximo intervalo de tiempo en que se podrá imprimir.  Por último, el método informa del momento más próximo en que el trabajo se podrá imprimir.  Será el posterior de los dos siguientes.  
  
-   La próxima hora a la que la cola de impresión esté disponible.  
  
-   La próxima hora a la que el trabajo de impresión esté disponible.  
  
 Al informar sobre las horas del día, se llama al método <xref:System.DateTime.ToShortTimeString%2A> también, porque este método suprime los años, meses y días del resultado.  No se puede restringir la disponibilidad de una cola de impresión o de un trabajo de impresión a determinados años, meses o días concretos.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 Las dos sobrecargas del método **ReportAvailabilityAtThisTime** son idénticas salvo por el tipo que se les pasa, por lo que únicamente se presenta la versión <xref:System.Printing.PrintQueue> a continuación.  
  
> [!NOTE]
>  El hecho de que los métodos sean idénticos salvo por el tipo, suscita la pregunta de por qué en el ejemplo no se crea un método genérico **ReportAvailabilityAtThisTime\<T\>**.  La razón es que este tipo de método tendría que estar restringido a una clase que tuviera las propiedades **StartTimeOfDay** y **UntilTimeOfDay** a las que el método llama, pero un método genérico únicamente se puede restringir a una sola clase y la única clase común a <xref:System.Printing.PrintQueue> y <xref:System.Printing.PrintSystemJobInfo> en el árbol de herencia es <xref:System.Printing.PrintSystemObject>, que carece de estas propiedades.  
  
 El método **ReportAvailabilityAtThisTime** \(que se presenta en el ejemplo de código siguiente\) comienza inicializando una variable centinela <xref:System.Boolean> en `true`.  Se restablecerá en `false` si la cola no está disponible.  
  
 Luego, el método comprueba si los momentos de inicio y "hasta" son idénticos.  Si lo son, la cola siempre está disponible, por lo que el método devuelve `true`.  
  
 Si la cola no está disponible en todo momento, el método utiliza la propiedad <xref:System.DateTime.UtcNow%2A> estática para obtener la hora actual como un objeto <xref:System.DateTime>.  \(No se necesita la hora local porque las propiedades <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> y <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> se expresan en hora UTC.\)  
  
 Sin embargo, estas dos propiedades no son objetos <xref:System.DateTime>.  Son valores <xref:System.Int32> que expresan la hora como el número de minutos transcurridos desde la medianoche según la hora UTC.  Así que es preciso convertir el objeto <xref:System.DateTime> en minutos desde la medianoche.  Una vez convertidos, el método se limita a comprobar si "ahora" se encuentra entre las horas de inicio y "hasta" de la cola, establece el centinela en false si no es así, y devuelve el centinela.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 El método **TimeConverter.ConvertToLocalHumanReadableTime** \(presentado en el ejemplo de código siguiente\) no utiliza ningún método introducido con [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], de modo que su explicación es breve.  El método tiene una tarea de conversión doble: debe tomar un entero que expresa minutos transcurridos desde la medianoche y convertirlo en una hora legible, y luego convertir este valor en la hora local.  Para ello, en primer lugar crea un objeto <xref:System.DateTime> establecido en la medianoche según la hora UTC y, a continuación, utiliza el método <xref:System.DateTime.AddMinutes%2A> para sumar los minutos que se pasaron al método.  Esto devuelve un nuevo valor <xref:System.DateTime> que expresa la hora original que se pasó al método.  A continuación, el método <xref:System.DateTime.ToLocalTime%2A> convierte este valor en la hora local.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## Vea también  
 <xref:System.DateTime>   
 <xref:System.Printing.PrintSystemJobInfo>   
 <xref:System.Printing.PrintQueue>   
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)