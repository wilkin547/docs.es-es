---
title: "C&#243;mo: Diagnosticar trabajos de impresi&#243;n problem&#225;ticos | Microsoft Docs"
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
  - "trabajos de impresión, diagnosticar problemas"
  - "trabajos de impresión, solucionar problemas"
  - "solucionar problemas con trabajos de impresión"
ms.assetid: b081a170-84c6-48f9-a487-5766a8d58a82
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Diagnosticar trabajos de impresi&#243;n problem&#225;ticos
Los administradores de red con frecuencia tienen que ocuparse de las quejas de los usuarios sobre trabajos de impresión que no se imprimen o lo hacen con lentitud.  El conjunto enriquecido de propiedades de trabajos de impresión expuesto en las [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] de [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] proporciona un medio para realizar un diagnóstico remoto rápido de los trabajos de impresión.  
  
## Ejemplo  
 Los pasos principales para crear este tipo de utilidad son los siguientes.  
  
1.  Identifique el trabajo de impresión que provoca la queja del usuario.  Con frecuencia, los usuarios no lo pueden hacer con precisión.  Es posible que no sepan el nombre de los servidores de impresión o de las impresoras.  Puede que describan la ubicación de la impresora con una terminología distinta a la utilizada al establecer su propiedad <xref:System.Printing.PrintQueue.Location%2A>.  En consecuencia, es conveniente generar una lista de trabajos del usuario actualmente enviados.  Si hay más de uno, entonces puede utilizarse la comunicación entre el usuario y el administrador del sistema de impresión para determinar con precisión qué trabajo es el que presenta problemas.  Para ello, proceda como sigue.  
  
    1.  Obtenga una lista de todos los servidores de impresión.  
  
    2.  Recorra en bucle los servidores para consultar sus colas de impresión.  
  
    3.  En cada pasada del bucle de servidor, recorra en bucle todas las colas del servidor para consultar sus trabajos.  
  
    4.  Dentro de cada pasada del bucle de cola, recorra en bucle sus trabajos y recolecte la información identificativa sobre aquéllos que ha enviado el usuario que se queja.  
  
2.  Una vez identificado el trabajo de impresión problemático, examine las propiedades pertinentes para ver cuál puede ser el problema.  Por ejemplo, ¿el trabajo se encuentra en un estado de error? o ¿la impresora correspondiente se ha quedado sin conexión antes de imprimir el trabajo?  
  
 El código siguiente consiste en una serie de ejemplos de código.  El primer ejemplo de código contiene el bucle que recorre las colas de impresión.  \(Paso 1c anterior.\) La variable `myPrintQueues` es el objeto <xref:System.Printing.PrintQueueCollection> correspondiente al servidor de impresión actual.  
  
 El ejemplo de código comienza actualizando el objeto de cola de impresión actual mediante <xref:System.Printing.PrintQueue.Refresh%2A?displayProperty=fullName>.  De este modo, se asegura de que las propiedades del objeto se corresponden con precisión al estado de la impresora física que representan.  A continuación, la aplicación obtiene la colección de trabajos de impresión que se encuentran en este momento en la cola de impresión, mediante <xref:System.Printing.PrintQueue.GetPrintJobInfoCollection%2A>.  
  
 Luego, la aplicación recorre en bucle la colección <xref:System.Printing.PrintSystemJobInfo> y compara cada propiedad <xref:System.Printing.PrintSystemJobInfo.Submitter%2A> con el alias del usuario que ha presentado la queja.  Si coinciden, la aplicación agrega información identificativa sobre el trabajo a la cadena que se presentará.  \(Las variables `jobList` y `userName` se inicializan anteriormente en la aplicación.\)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#enumeratejobsinqueues)]
 [!code-csharp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#enumeratejobsinqueues)]
 [!code-vb[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#enumeratejobsinqueues)]  
  
 En el ejemplo de código siguiente se continúa con la aplicación en el paso 2.  \(Vea más arriba.\) Se ha identificado el trabajo problemático y la aplicación solicita la información que lo identificará.  A partir de esta información, crea los objetos <xref:System.Printing.PrintServer>, <xref:System.Printing.PrintQueue> y <xref:System.Printing.PrintSystemJobInfo>.  
  
 En este punto, la aplicación contiene una estructura de bifurcación que corresponde a las dos maneras de comprobar el estado de un trabajo de impresión:  
  
-   Puede leer los marcadores de la propiedad <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A>, que es del tipo <xref:System.Printing.PrintJobStatus>.  
  
-   Puede leer cada propiedad pertinente, como <xref:System.Printing.PrintSystemJobInfo.IsBlocked%2A> y <xref:System.Printing.PrintSystemJobInfo.IsInError%2A>.  
  
 En este ejemplo se muestran ambos métodos, de modo que previamente se ha preguntado al usuario qué método desea utilizar y este ha respondido con "Y" \(Sí\) si desea utilizar los marcadores de la propiedad <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A>.  Consulte más adelante los detalles de los dos métodos.  Por último, la aplicación utiliza un método denominado **ReportQueueAndJobAvailability** para informar de si el trabajo se puede imprimir en este momento de día.  Este método se describe en [Detectar si un trabajo de impresión se puede imprimir en esta hora del día](../../../../docs/framework/wpf/advanced/how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day.md).  
  
 [!code-cpp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#identifyanddiagnoseproblematicjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#identifyanddiagnoseproblematicjob)]
 [!code-vb[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#identifyanddiagnoseproblematicjob)]  
  
 Para comprobar estado del trabajo de impresión mediante los marcadores de la propiedad <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A>, se comprueba cada marcador pertinente para ver si está establecido.  La manera estándar de comprobar si un bit está establecido en un conjunto de indicadores de bits, es realizar la operación de AND lógico con el conjunto de marcadores como uno de los operandos y con el propio marcador como el otro operando.  Puesto que el marcador únicamente tiene un bit establecido, el resultado de la operación de AND lógico es que, a lo sumo, ese mismo bit está establecido.  Para averiguar si lo está o no, basta con comparar el resultado de la operación de AND lógico con el propio marcador.  Para obtener más información, consulte <xref:System.Printing.PrintJobStatus>, [Operador & \(Referencia de C\#\)](../Topic/&%20Operator%20\(C%23%20Reference\).md) y <xref:System.FlagsAttribute>.  
  
 Para cada atributo cuyo bit está establecido, el código informa de ello en la pantalla de la consola y, en ocasiones, sugiere una manera de responder.  \(El método **HandlePausedJob** al que se llama si el trabajo o la cola está en pausa se describe más adelante.\)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobattributes)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobattributes)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobattributes)]  
  
 Para comprobar el estado del trabajo de impresión mediante propiedades independientes, basta con leer cada propiedad y, si la propiedad es `true`, informar de ello en la pantalla de la consola y, si se desea, sugerir una manera de responder.  \(El método **HandlePausedJob** al que se llama si el trabajo o la cola está en pausa se describe más adelante.\)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobproperties)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobproperties)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobproperties)]  
  
 El método **HandlePausedJob** permite al usuario de la aplicación reanudar remotamente los trabajos en pausa.  Dado que puede existir una razón de peso por la que se ha puesto en pausa la cola de impresión, el método comienza solicitando una decisión del usuario sobre si reanudarla o no.  Si la respuesta es "Y" \(Sí\), entonces se llama al método <xref:System.Printing.PrintQueue.Resume%2A?displayProperty=fullName>.  
  
 Luego, se pide al usuario que decida si se debe reanudar el propio trabajo, por si se ha puesto en pausa con independencia de la cola de impresión.  \(Observe las diferencias entre <xref:System.Printing.PrintQueue.IsPaused%2A?displayProperty=fullName> y <xref:System.Printing.PrintSystemJobInfo.IsPaused%2A?displayProperty=fullName>.\) Si la respuesta es "Y" \(Sí\), entonces se llama al método <xref:System.Printing.PrintSystemJobInfo.Resume%2A?displayProperty=fullName>, de lo contrario, se llama al método <xref:System.Printing.PrintSystemJobInfo.Cancel%2A>.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#HandlePausedJob](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#handlepausedjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#HandlePausedJob](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#handlepausedjob)]
 [!code-vb[DiagnoseProblematicPrintJob#HandlePausedJob](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#handlepausedjob)]  
  
## Vea también  
 <xref:System.Printing.PrintJobStatus>   
 <xref:System.Printing.PrintSystemJobInfo>   
 <xref:System.FlagsAttribute>   
 <xref:System.Printing.PrintQueue>   
 [Operador & \(Referencia de C\#\)](../Topic/&%20Operator%20\(C%23%20Reference\).md)   
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)