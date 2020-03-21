---
title: 'Cómo: Supervisar de forma remota el estado de las impresoras'
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
ms.openlocfilehash: 859ccb703c6c54c66d6ea7b433c67d156627e25b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187035"
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a>Cómo: Supervisar de forma remota el estado de las impresoras
En un momento dado, en las empresas de tamaño medio y grande puede haber varias impresoras que no funcionen debido a un atasco del papel, que se queden sin papel y otras situaciones problemáticas. El amplio conjunto de propiedades de impresora expuestas en las API de Microsoft .NET Framework proporcionan un medio para realizar una encuesta rápida de los estados de las impresoras.  
  
## <a name="example"></a>Ejemplo  
 Los pasos principales para crear este tipo de utilidad son los siguientes.  
  
1. Obtener una lista de todos los servidores de impresión.  
  
2. Recorrer los servidores para consultar sus colas de impresión.  
  
3. Dentro de cada paso del bucle de servidor, recorra en iteración todas las colas del servidor y lea cada propiedad que podría indicar que la cola no está funcionando actualmente.  
  
 El código siguiente es una serie de fragmentos de código. Para simplificar, en este ejemplo se da por hecho que hay una lista delimitada por CRLF de servidores de impresión. La `fileOfPrintServers` variable <xref:System.IO.StreamReader> es un objeto para este archivo. Puesto que cada nombre de servidor está <xref:System.IO.StreamReader.ReadLine%2A> en su propia línea, cualquier <xref:System.IO.StreamReader>llamada de obtiene el nombre del siguiente servidor y mueve el cursor 's al principio de la siguiente línea.  
  
 Dentro del bucle externo, <xref:System.Printing.PrintServer> el código crea un objeto para el servidor de impresión más reciente y especifica que la aplicación debe tener derechos administrativos para el servidor.  
  
> [!NOTE]
> Si hay muchos servidores, puede mejorar el <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> rendimiento mediante los constructores que solo inicializan las propiedades que va a necesitar.  
  
 A continuación, <xref:System.Printing.PrintServer.GetPrintQueues%2A> el ejemplo se utiliza para crear una colección de todas las colas del servidor y comienza a recorrerlas en bucle. Este bucle interno contiene una estructura de bifurcación correspondiente a las dos maneras de comprobar el estado de la impresora:  
  
- Puede leer las marcas <xref:System.Printing.PrintQueue.QueueStatus%2A> de la <xref:System.Printing.PrintQueueStatus>propiedad que es de tipo .  
  
- Puede leer cada propiedad <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>relevante, <xref:System.Printing.PrintQueue.IsPaperJammed%2A>como , y .  
  
 En este ejemplo se muestran ambos métodos, por lo que se solicitaba previamente al usuario <xref:System.Printing.PrintQueue.QueueStatus%2A> qué método usar y respondía con "y" si quería usar las marcas de la propiedad. A continuación encontrará los detalles de los dos métodos.  
  
 Por último, los resultados se presentan al usuario.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 Para comprobar el estado de <xref:System.Printing.PrintQueue.QueueStatus%2A> la impresora mediante las marcas de la propiedad, compruebe cada marca relevante para ver si está establecida. El modo estándar para ver si un bit se establece en un conjunto de marcadores de bits es realizar una operación AND lógica con el conjunto de marcadores como uno de los operandos y la propia marca como el otro. Puesto que el propio marcador solo tiene un bit establecido, el resultado del operador lógico AND es que, como máximo, se establezca ese mismo bit. Para averiguar si esto ocurre o no, basta con comparar el resultado del operador lógico AND y el propio marcador. Para obtener más <xref:System.Printing.PrintQueueStatus>información, vea , el operador <xref:System.FlagsAttribute>de& (referencia de [C)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)y .  
  
 Para cada atributo cuyo bit esté establecido, el código agrega un aviso al informe final que se presentará al usuario. (Se trata a continuación el método **ReportAvailabilityAtThisTime** que se llama al final del código).  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 Para comprobar el estado de la impresora mediante cada propiedad, simplemente lea cada propiedad y agregue una nota al informe final, que se presentará al usuario si la propiedad es `true`. (Se trata a continuación el método **ReportAvailabilityAtThisTime** que se llama al final del código).  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 El método **ReportAvailabilityAtThisTime** se creó por si necesita determinar si la cola está disponible en el momento actual del día.  
  
 El método no hará <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> nada si las propiedades son iguales; porque en ese caso la impresora está disponible en todo momento. Si son diferentes, el método obtiene la hora actual que, a continuación, <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> tiene <xref:System.Int32>que convertirse en minutos <xref:System.DateTime> totales después de la medianoche porque las <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> propiedades son s que representan minutos después de la medianoche, no objetos. Por último, el método comprueba si la hora actual se encuentra entre el inicio y las horas "hasta".  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a>Consulte también

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
- [Operador de& (referencia de C)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [Documentos en WPF](documents-in-wpf.md)
- [Información general sobre impresión](printing-overview.md)
