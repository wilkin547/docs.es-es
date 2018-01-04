---
title: "Cómo: Supervisar de forma remota el estado de las impresoras"
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
- surveying printer status remotely [WPF]
- printer status [WPF], surveying remotely
- remotely surveying printer status [WPF]
- status [WPF], printers [WPF], surveying remotely
ms.assetid: d6324759-8292-4c23-9584-9c708887dc94
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eef67d6ade8fb2a17edadff35fc3155608f831cd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a>Cómo: Supervisar de forma remota el estado de las impresoras
En un momento dado, en las empresas de tamaño medio y grande puede haber varias impresoras que no funcionen debido a un atasco del papel, que se queden sin papel y otras situaciones problemáticas. El amplio conjunto de propiedades de impresora expuesto en [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] de [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] proporciona un medio para realizar una encuesta rápida de los estados de las impresoras.  
  
## <a name="example"></a>Ejemplo  
 Los pasos principales para crear este tipo de utilidad son los siguientes.  
  
1.  Obtener una lista de todos los servidores de impresión.  
  
2.  Recorrer los servidores para consultar sus colas de impresión.  
  
3.  Dentro de cada paso del bucle de servidor, recorra en iteración todas las colas del servidor y lea cada propiedad que podría indicar que la cola no está funcionando actualmente.  
  
 El código siguiente es una serie de fragmentos de código. Para simplificar, en este ejemplo se da por hecho que hay una lista delimitada por CRLF de servidores de impresión. La variable `fileOfPrintServers` es un <xref:System.IO.StreamReader> objeto para este archivo. Puesto que cada nombre de servidor está en su propia línea, todas las llamadas de <xref:System.IO.StreamReader.ReadLine%2A> Obtiene el nombre del servidor del próximo y mueve el <xref:System.IO.StreamReader>del cursor al principio de la línea siguiente.  
  
 Dentro del bucle exterior, el código crea un <xref:System.Printing.PrintServer> de objetos para el servidor de impresión más reciente y especifica que la aplicación debe tener derechos administrativos en el servidor.  
  
> [!NOTE]
>  Si hay una gran cantidad de servidores, puede mejorar el rendimiento mediante el uso de la <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> constructores que inicializan únicamente las propiedades que se va a necesitar.  
  
 El ejemplo se utiliza <xref:System.Printing.PrintServer.GetPrintQueues%2A> crear una colección de todos los servidores de las colas y comienza a recorrerlas en bucle. Este bucle interno contiene una estructura de bifurcación correspondiente a las dos maneras de comprobar el estado de la impresora:  
  
-   Puede leer las marcas de la <xref:System.Printing.PrintQueue.QueueStatus%2A> propiedad que es del tipo <xref:System.Printing.PrintQueueStatus>.  
  
-   Puede leer cada propiedad pertinente como <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, y <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.  
  
 Este ejemplo muestra ambos métodos, por lo que el usuario se preguntará qué método utilizar previamente y se ha respondido con "y" Si desea usar los marcadores de la <xref:System.Printing.PrintQueue.QueueStatus%2A> propiedad. A continuación encontrará los detalles de los dos métodos.  
  
 Por último, los resultados se presentan al usuario.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 Para comprobar el estado de la impresora mediante los marcadores de la <xref:System.Printing.PrintQueue.QueueStatus%2A> propiedad, se comprueba cada marcador pertinente para ver si está configurada. El modo estándar para ver si un bit se establece en un conjunto de marcadores de bits es realizar una operación AND lógica con el conjunto de marcadores como uno de los operandos y la propia marca como el otro. Puesto que el propio marcador solo tiene un bit establecido, el resultado del operador lógico AND es que, como máximo, se establezca ese mismo bit. Para averiguar si esto ocurre o no, basta con comparar el resultado del operador lógico AND y el propio marcador. Para obtener más información, consulte <xref:System.Printing.PrintQueueStatus>, [& (operador) (referencia de C#)](~/docs/csharp/language-reference/operators/and-operator.md), y <xref:System.FlagsAttribute>.  
  
 Para cada atributo cuyo bit esté establecido, el código agrega un aviso al informe final que se presentará al usuario. (Se trata a continuación el método **ReportAvailabilityAtThisTime** que se llama al final del código).  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 Para comprobar el estado de la impresora mediante cada propiedad, simplemente lea cada propiedad y agregue una nota al informe final, que se presentará al usuario si la propiedad es `true`. (Se trata a continuación el método **ReportAvailabilityAtThisTime** que se llama al final del código).  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 El método **ReportAvailabilityAtThisTime** se creó por si necesita determinar si la cola está disponible en el momento actual del día.  
  
 El método no hará nada si el <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> y <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> propiedades son iguales; porque en ese caso la impresora está disponible en todo momento. Si son diferentes, el método obtiene la hora actual que, a continuación, se convertirán en total de minutos anterior medianoche porque la <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> y <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> propiedades son <xref:System.Int32>que no representa minutos después de medianoche, <xref:System.DateTime> objetos. Por último, el método comprueba si la hora actual se encuentra entre el inicio y las horas "hasta".  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A>  
 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>  
 <xref:System.DateTime>  
 <xref:System.Printing.PrintQueueStatus>  
 <xref:System.FlagsAttribute>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 [& (Operador) (referencia de C#)](~/docs/csharp/language-reference/operators/and-operator.md)  
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)
