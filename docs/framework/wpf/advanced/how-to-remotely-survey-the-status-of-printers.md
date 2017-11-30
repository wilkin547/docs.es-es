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
ms.openlocfilehash: ad824a1cef637edc99e6aaafc99d557167ea1f1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a><span data-ttu-id="4b2f0-102">Cómo: Supervisar de forma remota el estado de las impresoras</span><span class="sxs-lookup"><span data-stu-id="4b2f0-102">How to: Remotely Survey the Status of Printers</span></span>
<span data-ttu-id="4b2f0-103">En un momento dado, en las empresas de tamaño medio y grande puede haber varias impresoras que no funcionen debido a un atasco del papel, que se queden sin papel y otras situaciones problemáticas.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-103">At any given time at medium and large companies there may be multiple printers that are not working due to a paper jam or being out of paper or some other problematic situation.</span></span> <span data-ttu-id="4b2f0-104">El amplio conjunto de propiedades de impresora expuesto en [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] de [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] proporciona un medio para realizar una encuesta rápida de los estados de las impresoras.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-104">The rich set of printer properties exposed in the [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] of [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] provide a means for performing a rapid survey of the states of printers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b2f0-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4b2f0-105">Example</span></span>  
 <span data-ttu-id="4b2f0-106">Los pasos principales para crear este tipo de utilidad son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-106">The major steps for creating this kind of utility are as follows.</span></span>  
  
1.  <span data-ttu-id="4b2f0-107">Obtener una lista de todos los servidores de impresión.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-107">Obtain a list of all print servers.</span></span>  
  
2.  <span data-ttu-id="4b2f0-108">Recorrer los servidores para consultar sus colas de impresión.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-108">Loop through the servers to query their print queues.</span></span>  
  
3.  <span data-ttu-id="4b2f0-109">Dentro de cada paso del bucle de servidor, recorra en iteración todas las colas del servidor y lea cada propiedad que podría indicar que la cola no está funcionando actualmente.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-109">Within each pass of the server loop, loop through all the server's queues and read each property that might indicate that the queue is not currently working.</span></span>  
  
 <span data-ttu-id="4b2f0-110">El código siguiente es una serie de fragmentos de código.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-110">The code below is a series of snippets.</span></span> <span data-ttu-id="4b2f0-111">Para simplificar, en este ejemplo se da por hecho que hay una lista delimitada por CRLF de servidores de impresión.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-111">For simplicity, this example assumes that there is a CRLF-delimited list of print servers.</span></span> <span data-ttu-id="4b2f0-112">La variable `fileOfPrintServers` es un <xref:System.IO.StreamReader> objeto para este archivo.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-112">The variable `fileOfPrintServers` is a <xref:System.IO.StreamReader> object for this file.</span></span> <span data-ttu-id="4b2f0-113">Puesto que cada nombre de servidor está en su propia línea, todas las llamadas de <xref:System.IO.StreamReader.ReadLine%2A> Obtiene el nombre del servidor del próximo y mueve el <xref:System.IO.StreamReader>del cursor al principio de la línea siguiente.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-113">Since each server name is on its own line, any call of <xref:System.IO.StreamReader.ReadLine%2A> gets the name of the next server and moves the <xref:System.IO.StreamReader>'s cursor to the beginning of the next line.</span></span>  
  
 <span data-ttu-id="4b2f0-114">Dentro del bucle exterior, el código crea un <xref:System.Printing.PrintServer> de objetos para el servidor de impresión más reciente y especifica que la aplicación debe tener derechos administrativos en el servidor.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-114">Within the outer loop, the code creates a <xref:System.Printing.PrintServer> object for the latest print server and specifies that the application is to have administrative rights to the server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b2f0-115">Si hay una gran cantidad de servidores, puede mejorar el rendimiento mediante el uso de la <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> constructores que inicializan únicamente las propiedades que se va a necesitar.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-115">If there are a lot of servers, you can improve performance by using the <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> constructors that only initialize the properties you are going to need.</span></span>  
  
 <span data-ttu-id="4b2f0-116">El ejemplo se utiliza <xref:System.Printing.PrintServer.GetPrintQueues%2A> crear una colección de todos los servidores de las colas y comienza a recorrerlas en bucle.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-116">The example then uses <xref:System.Printing.PrintServer.GetPrintQueues%2A> to create a collection of all of the server's queues and begins to loop through them.</span></span> <span data-ttu-id="4b2f0-117">Este bucle interno contiene una estructura de bifurcación correspondiente a las dos maneras de comprobar el estado de la impresora:</span><span class="sxs-lookup"><span data-stu-id="4b2f0-117">This inner loop contains a branching structure corresponding to the two ways of checking a printer's status:</span></span>  
  
-   <span data-ttu-id="4b2f0-118">Puede leer las marcas de la <xref:System.Printing.PrintQueue.QueueStatus%2A> propiedad que es del tipo <xref:System.Printing.PrintQueueStatus>.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-118">You can read the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property which is of type <xref:System.Printing.PrintQueueStatus>.</span></span>  
  
-   <span data-ttu-id="4b2f0-119">Puede leer cada propiedad pertinente como <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, y <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-119">You can read each relevant property such as <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, and <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.</span></span>  
  
 <span data-ttu-id="4b2f0-120">Este ejemplo muestra ambos métodos, por lo que el usuario se preguntará qué método utilizar previamente y se ha respondido con "y" Si desea usar los marcadores de la <xref:System.Printing.PrintQueue.QueueStatus%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-120">This example demonstrates both methods, so the user was previously prompted as to which method to use and responded with "y" if he or she wanted to use the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property.</span></span> <span data-ttu-id="4b2f0-121">A continuación encontrará los detalles de los dos métodos.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-121">See below for the details of the two methods.</span></span>  
  
 <span data-ttu-id="4b2f0-122">Por último, los resultados se presentan al usuario.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-122">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 <span data-ttu-id="4b2f0-123">Para comprobar el estado de la impresora mediante los marcadores de la <xref:System.Printing.PrintQueue.QueueStatus%2A> propiedad, se comprueba cada marcador pertinente para ver si está configurada.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-123">To check printer status using the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property, you check each relevant flag to see if it is set.</span></span> <span data-ttu-id="4b2f0-124">El modo estándar para ver si un bit se establece en un conjunto de marcadores de bits es realizar una operación AND lógica con el conjunto de marcadores como uno de los operandos y la propia marca como el otro.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-124">The standard way to see if one bit is set in a set of bit flags is to perform a logical AND operation with the set of flags as one operand and the flag itself as the other.</span></span> <span data-ttu-id="4b2f0-125">Puesto que el propio marcador solo tiene un bit establecido, el resultado del operador lógico AND es que, como máximo, se establezca ese mismo bit.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-125">Since the flag itself has only one bit set, the result of the logical AND is that, at most, that same bit is set.</span></span> <span data-ttu-id="4b2f0-126">Para averiguar si esto ocurre o no, basta con comparar el resultado del operador lógico AND y el propio marcador.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-126">To find out whether it is or not, just compare the result of the logical AND with the flag itself.</span></span> <span data-ttu-id="4b2f0-127">Para obtener más información, consulte <xref:System.Printing.PrintQueueStatus>, [& (operador) (referencia de C#)](~/docs/csharp/language-reference/operators/and-operator.md), y <xref:System.FlagsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-127">For more information, see <xref:System.Printing.PrintQueueStatus>, the [& Operator (C# Reference)](~/docs/csharp/language-reference/operators/and-operator.md), and <xref:System.FlagsAttribute>.</span></span>  
  
 <span data-ttu-id="4b2f0-128">Para cada atributo cuyo bit esté establecido, el código agrega un aviso al informe final que se presentará al usuario.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-128">For each attribute whose bit is set, the code adds a notice to the final report that will be presented to the user.</span></span> <span data-ttu-id="4b2f0-129">(Se trata a continuación el método **ReportAvailabilityAtThisTime** que se llama al final del código).</span><span class="sxs-lookup"><span data-stu-id="4b2f0-129">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 <span data-ttu-id="4b2f0-130">Para comprobar el estado de la impresora mediante cada propiedad, simplemente lea cada propiedad y agregue una nota al informe final, que se presentará al usuario si la propiedad es `true`.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-130">To check printer status using each property, you simply read each property and add a note to the final report that will be presented to the user if the property is `true`.</span></span> <span data-ttu-id="4b2f0-131">(Se trata a continuación el método **ReportAvailabilityAtThisTime** que se llama al final del código).</span><span class="sxs-lookup"><span data-stu-id="4b2f0-131">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 <span data-ttu-id="4b2f0-132">El método **ReportAvailabilityAtThisTime** se creó por si necesita determinar si la cola está disponible en el momento actual del día.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-132">The **ReportAvailabilityAtThisTime** method was created in case you need to determine if the queue is available at the current time of day.</span></span>  
  
 <span data-ttu-id="4b2f0-133">El método no hará nada si el <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> y <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> propiedades son iguales; porque en ese caso la impresora está disponible en todo momento.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-133">The method will do nothing if the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are equal; because in that case the printer is available at all times.</span></span> <span data-ttu-id="4b2f0-134">Si son diferentes, el método obtiene la hora actual que, a continuación, se convertirán en total de minutos anterior medianoche porque la <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> y <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> propiedades son <xref:System.Int32>que no representa minutos después de medianoche, <xref:System.DateTime> objetos.</span><span class="sxs-lookup"><span data-stu-id="4b2f0-134">If they are different, the method gets the current time which then has to be converted into total minutes past midnight because the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are <xref:System.Int32>s representing minutes-after-midnight, not <xref:System.DateTime> objects.</span></span> <span data-ttu-id="4b2f0-135">Por último, el método comprueba si la hora actual se encuentra entre el inicio y las horas "hasta".</span><span class="sxs-lookup"><span data-stu-id="4b2f0-135">Finally, the method checks to see if the current time is between the start and "until" times.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a><span data-ttu-id="4b2f0-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b2f0-136">See Also</span></span>  
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
 [<span data-ttu-id="4b2f0-137">& (Operador) (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4b2f0-137">& Operator (C# Reference)</span></span>](~/docs/csharp/language-reference/operators/and-operator.md)  
 [<span data-ttu-id="4b2f0-138">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="4b2f0-138">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="4b2f0-139">Información general sobre impresión</span><span class="sxs-lookup"><span data-stu-id="4b2f0-139">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
