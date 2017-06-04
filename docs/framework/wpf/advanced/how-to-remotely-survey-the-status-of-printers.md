---
title: "C&#243;mo: Supervisar de forma remota el estado de las impresoras | Microsoft Docs"
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
  - "estado de la impresora, supervisar de manera remota"
  - "supervisar de manera remota el estado de la impresora"
  - "estado, impresoras, supervisar de manera remota"
  - "supervisar de manera remota el estado de la impresora"
ms.assetid: d6324759-8292-4c23-9584-9c708887dc94
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Supervisar de forma remota el estado de las impresoras
En cualquier momento determinado, en las compañías medianas y grandes puede haber varias impresoras que no funcionen por un atasco de papel, por falta de papel o por cualquier otra situación problemática.  El conjunto enriquecido de propiedades de impresora expuesto en las [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] de [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] proporciona un medio para realizar un repaso rápido de los estados de las impresoras.  
  
## Ejemplo  
 Los pasos principales para crear este tipo de utilidad son los siguientes.  
  
1.  Obtenga una lista de todos los servidores de impresión.  
  
2.  Recorra en bucle los servidores para consultar sus colas de impresión.  
  
3.  Dentro de cada paso del bucle de servidor, recorra en bucle todas las colas del servidor y lea cada propiedad que pueda indicar que la cola no está funcionando actualmente.  
  
 El código siguiente consiste en una serie de fragmentos de código.  Para mayor simplicidad, en este ejemplo se da por hecho que existe una lista de servidores de impresión delimitada por CRLF.  La variable `fileOfPrintServers` es un objeto <xref:System.IO.StreamReader> para este archivo.  Puesto que cada nombre de servidor figura en su propia línea, cualquier llamada de <xref:System.IO.StreamReader.ReadLine%2A> obtiene el nombre del servidor siguiente y mueve el cursor de <xref:System.IO.StreamReader> al principio de la línea siguiente.  
  
 Dentro del bucle exterior, el código crea un objeto <xref:System.Printing.PrintServer> para el último servidor de impresión y especifica que la aplicación debe tener derechos administrativos en el servidor.  
  
> [!NOTE]
>  Si hay muchos servidores, puede mejorar el rendimiento utilizando los constructores [PrintServer\(String, String\<xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29>, que inicializan únicamente las propiedades que se van a necesitar.  
  
 A continuación, en el ejemplo se utiliza el método <xref:System.Printing.PrintServer.GetPrintQueues%2A> para crear una colección de todas las colas del servidor y comienza a recorrerlas en bucle.  Este bucle interno contiene una estructura de bifurcación que corresponde a las dos maneras de comprobar el estado de una impresora:  
  
-   Puede leer los marcadores de la propiedad <xref:System.Printing.PrintQueue.QueueStatus%2A>, que es del tipo <xref:System.Printing.PrintQueueStatus>.  
  
-   Puede leer cada propiedad pertinente, como <xref:System.Printing.PrintQueue.IsOutOfPaper%2A> y <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.  
  
 En este ejemplo se muestran ambos métodos, de modo que previamente se ha preguntado al usuario qué método desea utilizar y este ha respondido con "y" \(Sí\) si desea utilizar los marcadores de la propiedad <xref:System.Printing.PrintQueue.QueueStatus%2A>.  Consulte más adelante los detalles de los dos métodos.  
  
 Por último, se presentan los resultados al usuario.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 Para comprobar estado de la impresora mediante los marcadores de la propiedad <xref:System.Printing.PrintQueue.QueueStatus%2A>, se comprueba cada marcador pertinente para ver si está establecido.  La manera estándar de comprobar si un bit está establecido en un conjunto de indicadores de bits, es realizar la operación de AND lógico con el conjunto de marcadores como uno de los operandos y con el propio marcador como el otro operando.  Puesto que el marcador únicamente tiene un bit establecido, el resultado de la operación de AND lógico es que, a lo sumo, ese mismo bit está establecido.  Para averiguar si lo está o no, basta con comparar el resultado de la operación de AND lógico con el propio marcador.  Para obtener más información, consulte <xref:System.Printing.PrintQueueStatus>, [Operador & \(Referencia de C\#\)](../Topic/&%20Operator%20\(C%23%20Reference\).md) y <xref:System.FlagsAttribute>.  
  
 Para cada atributo cuyo bit está establecido, el código agrega un aviso al informe final que se presentará al usuario.  \(El método **ReportAvailabilityAtThisTime** al que se llama al final del código se aborda más adelante.\)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 Para comprobar estado de la impresora mediante cada propiedad, basta con leer cada una de ellas y agregar una nota al informe final que se presentará al usuario en caso de que la propiedad sea `true`.  \(El método **ReportAvailabilityAtThisTime** al que se llama al final del código se aborda más adelante.\)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 Se creó el método **ReportAvailabilityAtThisTime** por si se necesita determinar si la cola está disponible a esta hora del día.  
  
 El método no hará nada si las propiedades <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> y <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> son iguales, porque en ese caso significa que la impresora está disponible en todo momento.  Si son diferentes, el método obtiene la hora actual que, a continuación, se tiene que convertir a minutos totales transcurridos desde la pasada medianoche; esto es porque las propiedades <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> y <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> son objetos <xref:System.Int32> que representan minutos transcurridos desde la medianoche, no objetos <xref:System.DateTime>.  Por último, el método comprueba si la hora actual se encuentra entre los momentos de inicio y "hasta".  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## Vea también  
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
 [Operador & \(Referencia de C\#\)](../Topic/&%20Operator%20\(C%23%20Reference\).md)   
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)