---
title: Procedimiento Supervisar de forma remota el estado de las impresoras
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- surveying printer status remotely [WPF]
- printer status [WPF], surveying remotely
- remotely surveying printer status [WPF]
- status [WPF], printers [WPF], surveying remotely
ms.assetid: d6324759-8292-4c23-9584-9c708887dc94
ms.openlocfilehash: dc187a4ea120661e8118ce79a966d3d4a3b40711
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340794"
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a>Procedimiento Supervisar de forma remota el estado de las impresoras
En un momento dado, en las empresas de tamaño medio y grande puede haber varias impresoras que no funcionen debido a un atasco del papel, que se queden sin papel y otras situaciones problemáticas. El amplio conjunto de propiedades de la impresora expuesto en el [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] de Microsoft .NET Framework proporciona un medio para realizar una encuesta rápida de los Estados de las impresoras.  
  
## <a name="example"></a>Ejemplo  
 Los pasos principales para crear este tipo de utilidad son los siguientes.  
  
1. Obtener una lista de todos los servidores de impresión.  
  
2. Recorrer los servidores para consultar sus colas de impresión.  
  
3. Dentro de cada paso del bucle de servidor, recorra en iteración todas las colas del servidor y lea cada propiedad que podría indicar que la cola no está funcionando actualmente.  
  
 El código siguiente es una serie de fragmentos de código. Para simplificar, en este ejemplo se da por hecho que hay una lista delimitada por CRLF de servidores de impresión. La variable `fileOfPrintServers` es un <xref:System.IO.StreamReader> objeto para este archivo. Puesto que cada nombre de servidor está en su propia línea, todas las llamadas de <xref:System.IO.StreamReader.ReadLine%2A> Obtiene el nombre del servidor siguiente y mueve el <xref:System.IO.StreamReader>del cursor al principio de la línea siguiente.  
  
 Dentro del bucle exterior, el código crea un <xref:System.Printing.PrintServer> de objetos para el servidor de impresión más reciente y especifica que la aplicación debe tener derechos administrativos en el servidor.  
  
> [!NOTE]
>  Si hay una gran cantidad de servidores, puede mejorar el rendimiento mediante el uso de la <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> constructores que inicializan únicamente las propiedades que se va a necesitar.  
  
 El ejemplo se utiliza <xref:System.Printing.PrintServer.GetPrintQueues%2A> para crear una colección de todos los servidores de pone en cola y comienza a recorrerlas. Este bucle interno contiene una estructura de bifurcación correspondiente a las dos maneras de comprobar el estado de la impresora:  
  
-   Puede leer los marcadores de la <xref:System.Printing.PrintQueue.QueueStatus%2A> propiedad que es de tipo <xref:System.Printing.PrintQueueStatus>.  
  
-   Puede leer cada propiedad pertinente, como <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, y <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.  
  
 En este ejemplo se muestra ambos métodos, por lo que el usuario se le pregunte qué método utilizar y Respondí con "s" si quería utilizar los marcadores de anteriormente el <xref:System.Printing.PrintQueue.QueueStatus%2A> propiedad. A continuación encontrará los detalles de los dos métodos.  
  
 Por último, los resultados se presentan al usuario.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 Para comprobar el estado de la impresora mediante los marcadores de la <xref:System.Printing.PrintQueue.QueueStatus%2A> propiedad, se comprueba cada marcador pertinente para ver si está establecido. El modo estándar para ver si un bit se establece en un conjunto de marcadores de bits es realizar una operación AND lógica con el conjunto de marcadores como uno de los operandos y la propia marca como el otro. Puesto que el propio marcador solo tiene un bit establecido, el resultado del operador lógico AND es que, como máximo, se establezca ese mismo bit. Para averiguar si esto ocurre o no, basta con comparar el resultado del operador lógico AND y el propio marcador. Para obtener más información, consulte <xref:System.Printing.PrintQueueStatus>, [& (operador) (C# referencia)](~/docs/csharp/language-reference/operators/and-operator.md), y <xref:System.FlagsAttribute>.  
  
 Para cada atributo cuyo bit esté establecido, el código agrega un aviso al informe final que se presentará al usuario. (Se trata a continuación el método **ReportAvailabilityAtThisTime** que se llama al final del código).  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 Para comprobar el estado de la impresora mediante cada propiedad, simplemente lea cada propiedad y agregue una nota al informe final, que se presentará al usuario si la propiedad es `true`. (Se trata a continuación el método **ReportAvailabilityAtThisTime** que se llama al final del código).  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 El método **ReportAvailabilityAtThisTime** se creó por si necesita determinar si la cola está disponible en el momento actual del día.  
  
 El método no hará nada si el <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> y <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> propiedades son iguales, porque en ese caso la impresora está disponible en todo momento. Si son diferentes, el método obtiene la hora actual que, a continuación, tiene que convertir a minutos totales pasada medianoche porque el <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> y <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> son propiedades <xref:System.Int32>que representan minutos después de medianoche, no <xref:System.DateTime> objetos. Por último, el método comprueba si la hora actual se encuentra entre el inicio y las horas "hasta".  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Printing.PrintQueue.StartTimeOfDay%2A>
- <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>
- <xref:System.DateTime>
- <xref:System.Printing.PrintQueueStatus>
- <xref:System.FlagsAttribute>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- [& (Operador) (C# referencia)](~/docs/csharp/language-reference/operators/and-operator.md)
- [Documentos en WPF](documents-in-wpf.md)
- [Información general sobre impresión](printing-overview.md)
