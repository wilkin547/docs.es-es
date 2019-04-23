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
# <a name="how-to-remotely-survey-the-status-of-printers"></a><span data-ttu-id="95864-102">Procedimiento Supervisar de forma remota el estado de las impresoras</span><span class="sxs-lookup"><span data-stu-id="95864-102">How to: Remotely Survey the Status of Printers</span></span>
<span data-ttu-id="95864-103">En un momento dado, en las empresas de tamaño medio y grande puede haber varias impresoras que no funcionen debido a un atasco del papel, que se queden sin papel y otras situaciones problemáticas.</span><span class="sxs-lookup"><span data-stu-id="95864-103">At any given time at medium and large companies there may be multiple printers that are not working due to a paper jam or being out of paper or some other problematic situation.</span></span> <span data-ttu-id="95864-104">El amplio conjunto de propiedades de la impresora expuesto en el [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] de Microsoft .NET Framework proporciona un medio para realizar una encuesta rápida de los Estados de las impresoras.</span><span class="sxs-lookup"><span data-stu-id="95864-104">The rich set of printer properties exposed in the [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] of Microsoft .NET Framework provide a means for performing a rapid survey of the states of printers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95864-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="95864-105">Example</span></span>  
 <span data-ttu-id="95864-106">Los pasos principales para crear este tipo de utilidad son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="95864-106">The major steps for creating this kind of utility are as follows.</span></span>  
  
1. <span data-ttu-id="95864-107">Obtener una lista de todos los servidores de impresión.</span><span class="sxs-lookup"><span data-stu-id="95864-107">Obtain a list of all print servers.</span></span>  
  
2. <span data-ttu-id="95864-108">Recorrer los servidores para consultar sus colas de impresión.</span><span class="sxs-lookup"><span data-stu-id="95864-108">Loop through the servers to query their print queues.</span></span>  
  
3. <span data-ttu-id="95864-109">Dentro de cada paso del bucle de servidor, recorra en iteración todas las colas del servidor y lea cada propiedad que podría indicar que la cola no está funcionando actualmente.</span><span class="sxs-lookup"><span data-stu-id="95864-109">Within each pass of the server loop, loop through all the server's queues and read each property that might indicate that the queue is not currently working.</span></span>  
  
 <span data-ttu-id="95864-110">El código siguiente es una serie de fragmentos de código.</span><span class="sxs-lookup"><span data-stu-id="95864-110">The code below is a series of snippets.</span></span> <span data-ttu-id="95864-111">Para simplificar, en este ejemplo se da por hecho que hay una lista delimitada por CRLF de servidores de impresión.</span><span class="sxs-lookup"><span data-stu-id="95864-111">For simplicity, this example assumes that there is a CRLF-delimited list of print servers.</span></span> <span data-ttu-id="95864-112">La variable `fileOfPrintServers` es un <xref:System.IO.StreamReader> objeto para este archivo.</span><span class="sxs-lookup"><span data-stu-id="95864-112">The variable `fileOfPrintServers` is a <xref:System.IO.StreamReader> object for this file.</span></span> <span data-ttu-id="95864-113">Puesto que cada nombre de servidor está en su propia línea, todas las llamadas de <xref:System.IO.StreamReader.ReadLine%2A> Obtiene el nombre del servidor siguiente y mueve el <xref:System.IO.StreamReader>del cursor al principio de la línea siguiente.</span><span class="sxs-lookup"><span data-stu-id="95864-113">Since each server name is on its own line, any call of <xref:System.IO.StreamReader.ReadLine%2A> gets the name of the next server and moves the <xref:System.IO.StreamReader>'s cursor to the beginning of the next line.</span></span>  
  
 <span data-ttu-id="95864-114">Dentro del bucle exterior, el código crea un <xref:System.Printing.PrintServer> de objetos para el servidor de impresión más reciente y especifica que la aplicación debe tener derechos administrativos en el servidor.</span><span class="sxs-lookup"><span data-stu-id="95864-114">Within the outer loop, the code creates a <xref:System.Printing.PrintServer> object for the latest print server and specifies that the application is to have administrative rights to the server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95864-115">Si hay una gran cantidad de servidores, puede mejorar el rendimiento mediante el uso de la <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> constructores que inicializan únicamente las propiedades que se va a necesitar.</span><span class="sxs-lookup"><span data-stu-id="95864-115">If there are a lot of servers, you can improve performance by using the <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> constructors that only initialize the properties you are going to need.</span></span>  
  
 <span data-ttu-id="95864-116">El ejemplo se utiliza <xref:System.Printing.PrintServer.GetPrintQueues%2A> para crear una colección de todos los servidores de pone en cola y comienza a recorrerlas.</span><span class="sxs-lookup"><span data-stu-id="95864-116">The example then uses <xref:System.Printing.PrintServer.GetPrintQueues%2A> to create a collection of all of the server's queues and begins to loop through them.</span></span> <span data-ttu-id="95864-117">Este bucle interno contiene una estructura de bifurcación correspondiente a las dos maneras de comprobar el estado de la impresora:</span><span class="sxs-lookup"><span data-stu-id="95864-117">This inner loop contains a branching structure corresponding to the two ways of checking a printer's status:</span></span>  
  
-   <span data-ttu-id="95864-118">Puede leer los marcadores de la <xref:System.Printing.PrintQueue.QueueStatus%2A> propiedad que es de tipo <xref:System.Printing.PrintQueueStatus>.</span><span class="sxs-lookup"><span data-stu-id="95864-118">You can read the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property which is of type <xref:System.Printing.PrintQueueStatus>.</span></span>  
  
-   <span data-ttu-id="95864-119">Puede leer cada propiedad pertinente, como <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, y <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.</span><span class="sxs-lookup"><span data-stu-id="95864-119">You can read each relevant property such as <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, and <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.</span></span>  
  
 <span data-ttu-id="95864-120">En este ejemplo se muestra ambos métodos, por lo que el usuario se le pregunte qué método utilizar y Respondí con "s" si quería utilizar los marcadores de anteriormente el <xref:System.Printing.PrintQueue.QueueStatus%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="95864-120">This example demonstrates both methods, so the user was previously prompted as to which method to use and responded with "y" if he or she wanted to use the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property.</span></span> <span data-ttu-id="95864-121">A continuación encontrará los detalles de los dos métodos.</span><span class="sxs-lookup"><span data-stu-id="95864-121">See below for the details of the two methods.</span></span>  
  
 <span data-ttu-id="95864-122">Por último, los resultados se presentan al usuario.</span><span class="sxs-lookup"><span data-stu-id="95864-122">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 <span data-ttu-id="95864-123">Para comprobar el estado de la impresora mediante los marcadores de la <xref:System.Printing.PrintQueue.QueueStatus%2A> propiedad, se comprueba cada marcador pertinente para ver si está establecido.</span><span class="sxs-lookup"><span data-stu-id="95864-123">To check printer status using the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property, you check each relevant flag to see if it is set.</span></span> <span data-ttu-id="95864-124">El modo estándar para ver si un bit se establece en un conjunto de marcadores de bits es realizar una operación AND lógica con el conjunto de marcadores como uno de los operandos y la propia marca como el otro.</span><span class="sxs-lookup"><span data-stu-id="95864-124">The standard way to see if one bit is set in a set of bit flags is to perform a logical AND operation with the set of flags as one operand and the flag itself as the other.</span></span> <span data-ttu-id="95864-125">Puesto que el propio marcador solo tiene un bit establecido, el resultado del operador lógico AND es que, como máximo, se establezca ese mismo bit.</span><span class="sxs-lookup"><span data-stu-id="95864-125">Since the flag itself has only one bit set, the result of the logical AND is that, at most, that same bit is set.</span></span> <span data-ttu-id="95864-126">Para averiguar si esto ocurre o no, basta con comparar el resultado del operador lógico AND y el propio marcador.</span><span class="sxs-lookup"><span data-stu-id="95864-126">To find out whether it is or not, just compare the result of the logical AND with the flag itself.</span></span> <span data-ttu-id="95864-127">Para obtener más información, consulte <xref:System.Printing.PrintQueueStatus>, [& (operador) (C# referencia)](~/docs/csharp/language-reference/operators/and-operator.md), y <xref:System.FlagsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="95864-127">For more information, see <xref:System.Printing.PrintQueueStatus>, the [& Operator (C# Reference)](~/docs/csharp/language-reference/operators/and-operator.md), and <xref:System.FlagsAttribute>.</span></span>  
  
 <span data-ttu-id="95864-128">Para cada atributo cuyo bit esté establecido, el código agrega un aviso al informe final que se presentará al usuario.</span><span class="sxs-lookup"><span data-stu-id="95864-128">For each attribute whose bit is set, the code adds a notice to the final report that will be presented to the user.</span></span> <span data-ttu-id="95864-129">(Se trata a continuación el método **ReportAvailabilityAtThisTime** que se llama al final del código).</span><span class="sxs-lookup"><span data-stu-id="95864-129">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 <span data-ttu-id="95864-130">Para comprobar el estado de la impresora mediante cada propiedad, simplemente lea cada propiedad y agregue una nota al informe final, que se presentará al usuario si la propiedad es `true`.</span><span class="sxs-lookup"><span data-stu-id="95864-130">To check printer status using each property, you simply read each property and add a note to the final report that will be presented to the user if the property is `true`.</span></span> <span data-ttu-id="95864-131">(Se trata a continuación el método **ReportAvailabilityAtThisTime** que se llama al final del código).</span><span class="sxs-lookup"><span data-stu-id="95864-131">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 <span data-ttu-id="95864-132">El método **ReportAvailabilityAtThisTime** se creó por si necesita determinar si la cola está disponible en el momento actual del día.</span><span class="sxs-lookup"><span data-stu-id="95864-132">The **ReportAvailabilityAtThisTime** method was created in case you need to determine if the queue is available at the current time of day.</span></span>  
  
 <span data-ttu-id="95864-133">El método no hará nada si el <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> y <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> propiedades son iguales, porque en ese caso la impresora está disponible en todo momento.</span><span class="sxs-lookup"><span data-stu-id="95864-133">The method will do nothing if the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are equal; because in that case the printer is available at all times.</span></span> <span data-ttu-id="95864-134">Si son diferentes, el método obtiene la hora actual que, a continuación, tiene que convertir a minutos totales pasada medianoche porque el <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> y <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> son propiedades <xref:System.Int32>que representan minutos después de medianoche, no <xref:System.DateTime> objetos.</span><span class="sxs-lookup"><span data-stu-id="95864-134">If they are different, the method gets the current time which then has to be converted into total minutes past midnight because the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are <xref:System.Int32>s representing minutes-after-midnight, not <xref:System.DateTime> objects.</span></span> <span data-ttu-id="95864-135">Por último, el método comprueba si la hora actual se encuentra entre el inicio y las horas "hasta".</span><span class="sxs-lookup"><span data-stu-id="95864-135">Finally, the method checks to see if the current time is between the start and "until" times.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a><span data-ttu-id="95864-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="95864-136">See also</span></span>

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
- [<span data-ttu-id="95864-137">& (Operador) (C# referencia)</span><span class="sxs-lookup"><span data-stu-id="95864-137">& Operator (C# Reference)</span></span>](~/docs/csharp/language-reference/operators/and-operator.md)
- [<span data-ttu-id="95864-138">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="95864-138">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="95864-139">Información general sobre impresión</span><span class="sxs-lookup"><span data-stu-id="95864-139">Printing Overview</span></span>](printing-overview.md)
