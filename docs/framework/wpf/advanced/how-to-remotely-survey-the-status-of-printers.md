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
# <a name="how-to-remotely-survey-the-status-of-printers"></a><span data-ttu-id="7d429-102">Cómo: Supervisar de forma remota el estado de las impresoras</span><span class="sxs-lookup"><span data-stu-id="7d429-102">How to: Remotely Survey the Status of Printers</span></span>
<span data-ttu-id="7d429-103">En un momento dado, en las empresas de tamaño medio y grande puede haber varias impresoras que no funcionen debido a un atasco del papel, que se queden sin papel y otras situaciones problemáticas.</span><span class="sxs-lookup"><span data-stu-id="7d429-103">At any given time at medium and large companies there may be multiple printers that are not working due to a paper jam or being out of paper or some other problematic situation.</span></span> <span data-ttu-id="7d429-104">El amplio conjunto de propiedades de impresora expuestas en las API de Microsoft .NET Framework proporcionan un medio para realizar una encuesta rápida de los estados de las impresoras.</span><span class="sxs-lookup"><span data-stu-id="7d429-104">The rich set of printer properties exposed in the APIs of Microsoft .NET Framework provide a means for performing a rapid survey of the states of printers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d429-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d429-105">Example</span></span>  
 <span data-ttu-id="7d429-106">Los pasos principales para crear este tipo de utilidad son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="7d429-106">The major steps for creating this kind of utility are as follows.</span></span>  
  
1. <span data-ttu-id="7d429-107">Obtener una lista de todos los servidores de impresión.</span><span class="sxs-lookup"><span data-stu-id="7d429-107">Obtain a list of all print servers.</span></span>  
  
2. <span data-ttu-id="7d429-108">Recorrer los servidores para consultar sus colas de impresión.</span><span class="sxs-lookup"><span data-stu-id="7d429-108">Loop through the servers to query their print queues.</span></span>  
  
3. <span data-ttu-id="7d429-109">Dentro de cada paso del bucle de servidor, recorra en iteración todas las colas del servidor y lea cada propiedad que podría indicar que la cola no está funcionando actualmente.</span><span class="sxs-lookup"><span data-stu-id="7d429-109">Within each pass of the server loop, loop through all the server's queues and read each property that might indicate that the queue is not currently working.</span></span>  
  
 <span data-ttu-id="7d429-110">El código siguiente es una serie de fragmentos de código.</span><span class="sxs-lookup"><span data-stu-id="7d429-110">The code below is a series of snippets.</span></span> <span data-ttu-id="7d429-111">Para simplificar, en este ejemplo se da por hecho que hay una lista delimitada por CRLF de servidores de impresión.</span><span class="sxs-lookup"><span data-stu-id="7d429-111">For simplicity, this example assumes that there is a CRLF-delimited list of print servers.</span></span> <span data-ttu-id="7d429-112">La `fileOfPrintServers` variable <xref:System.IO.StreamReader> es un objeto para este archivo.</span><span class="sxs-lookup"><span data-stu-id="7d429-112">The variable `fileOfPrintServers` is a <xref:System.IO.StreamReader> object for this file.</span></span> <span data-ttu-id="7d429-113">Puesto que cada nombre de servidor está <xref:System.IO.StreamReader.ReadLine%2A> en su propia línea, cualquier <xref:System.IO.StreamReader>llamada de obtiene el nombre del siguiente servidor y mueve el cursor 's al principio de la siguiente línea.</span><span class="sxs-lookup"><span data-stu-id="7d429-113">Since each server name is on its own line, any call of <xref:System.IO.StreamReader.ReadLine%2A> gets the name of the next server and moves the <xref:System.IO.StreamReader>'s cursor to the beginning of the next line.</span></span>  
  
 <span data-ttu-id="7d429-114">Dentro del bucle externo, <xref:System.Printing.PrintServer> el código crea un objeto para el servidor de impresión más reciente y especifica que la aplicación debe tener derechos administrativos para el servidor.</span><span class="sxs-lookup"><span data-stu-id="7d429-114">Within the outer loop, the code creates a <xref:System.Printing.PrintServer> object for the latest print server and specifies that the application is to have administrative rights to the server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d429-115">Si hay muchos servidores, puede mejorar el <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> rendimiento mediante los constructores que solo inicializan las propiedades que va a necesitar.</span><span class="sxs-lookup"><span data-stu-id="7d429-115">If there are a lot of servers, you can improve performance by using the <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> constructors that only initialize the properties you are going to need.</span></span>  
  
 <span data-ttu-id="7d429-116">A continuación, <xref:System.Printing.PrintServer.GetPrintQueues%2A> el ejemplo se utiliza para crear una colección de todas las colas del servidor y comienza a recorrerlas en bucle.</span><span class="sxs-lookup"><span data-stu-id="7d429-116">The example then uses <xref:System.Printing.PrintServer.GetPrintQueues%2A> to create a collection of all of the server's queues and begins to loop through them.</span></span> <span data-ttu-id="7d429-117">Este bucle interno contiene una estructura de bifurcación correspondiente a las dos maneras de comprobar el estado de la impresora:</span><span class="sxs-lookup"><span data-stu-id="7d429-117">This inner loop contains a branching structure corresponding to the two ways of checking a printer's status:</span></span>  
  
- <span data-ttu-id="7d429-118">Puede leer las marcas <xref:System.Printing.PrintQueue.QueueStatus%2A> de la <xref:System.Printing.PrintQueueStatus>propiedad que es de tipo .</span><span class="sxs-lookup"><span data-stu-id="7d429-118">You can read the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property which is of type <xref:System.Printing.PrintQueueStatus>.</span></span>  
  
- <span data-ttu-id="7d429-119">Puede leer cada propiedad <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>relevante, <xref:System.Printing.PrintQueue.IsPaperJammed%2A>como , y .</span><span class="sxs-lookup"><span data-stu-id="7d429-119">You can read each relevant property such as <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, and <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.</span></span>  
  
 <span data-ttu-id="7d429-120">En este ejemplo se muestran ambos métodos, por lo que se solicitaba previamente al usuario <xref:System.Printing.PrintQueue.QueueStatus%2A> qué método usar y respondía con "y" si quería usar las marcas de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7d429-120">This example demonstrates both methods, so the user was previously prompted as to which method to use and responded with "y" if they wanted to use the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property.</span></span> <span data-ttu-id="7d429-121">A continuación encontrará los detalles de los dos métodos.</span><span class="sxs-lookup"><span data-stu-id="7d429-121">See below for the details of the two methods.</span></span>  
  
 <span data-ttu-id="7d429-122">Por último, los resultados se presentan al usuario.</span><span class="sxs-lookup"><span data-stu-id="7d429-122">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 <span data-ttu-id="7d429-123">Para comprobar el estado de <xref:System.Printing.PrintQueue.QueueStatus%2A> la impresora mediante las marcas de la propiedad, compruebe cada marca relevante para ver si está establecida.</span><span class="sxs-lookup"><span data-stu-id="7d429-123">To check printer status using the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property, you check each relevant flag to see if it is set.</span></span> <span data-ttu-id="7d429-124">El modo estándar para ver si un bit se establece en un conjunto de marcadores de bits es realizar una operación AND lógica con el conjunto de marcadores como uno de los operandos y la propia marca como el otro.</span><span class="sxs-lookup"><span data-stu-id="7d429-124">The standard way to see if one bit is set in a set of bit flags is to perform a logical AND operation with the set of flags as one operand and the flag itself as the other.</span></span> <span data-ttu-id="7d429-125">Puesto que el propio marcador solo tiene un bit establecido, el resultado del operador lógico AND es que, como máximo, se establezca ese mismo bit.</span><span class="sxs-lookup"><span data-stu-id="7d429-125">Since the flag itself has only one bit set, the result of the logical AND is that, at most, that same bit is set.</span></span> <span data-ttu-id="7d429-126">Para averiguar si esto ocurre o no, basta con comparar el resultado del operador lógico AND y el propio marcador.</span><span class="sxs-lookup"><span data-stu-id="7d429-126">To find out whether it is or not, just compare the result of the logical AND with the flag itself.</span></span> <span data-ttu-id="7d429-127">Para obtener más <xref:System.Printing.PrintQueueStatus>información, vea , el operador <xref:System.FlagsAttribute>de& (referencia de [C)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)y .</span><span class="sxs-lookup"><span data-stu-id="7d429-127">For more information, see <xref:System.Printing.PrintQueueStatus>, the [& Operator (C# Reference)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-), and <xref:System.FlagsAttribute>.</span></span>  
  
 <span data-ttu-id="7d429-128">Para cada atributo cuyo bit esté establecido, el código agrega un aviso al informe final que se presentará al usuario.</span><span class="sxs-lookup"><span data-stu-id="7d429-128">For each attribute whose bit is set, the code adds a notice to the final report that will be presented to the user.</span></span> <span data-ttu-id="7d429-129">(Se trata a continuación el método **ReportAvailabilityAtThisTime** que se llama al final del código).</span><span class="sxs-lookup"><span data-stu-id="7d429-129">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 <span data-ttu-id="7d429-130">Para comprobar el estado de la impresora mediante cada propiedad, simplemente lea cada propiedad y agregue una nota al informe final, que se presentará al usuario si la propiedad es `true`.</span><span class="sxs-lookup"><span data-stu-id="7d429-130">To check printer status using each property, you simply read each property and add a note to the final report that will be presented to the user if the property is `true`.</span></span> <span data-ttu-id="7d429-131">(Se trata a continuación el método **ReportAvailabilityAtThisTime** que se llama al final del código).</span><span class="sxs-lookup"><span data-stu-id="7d429-131">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 <span data-ttu-id="7d429-132">El método **ReportAvailabilityAtThisTime** se creó por si necesita determinar si la cola está disponible en el momento actual del día.</span><span class="sxs-lookup"><span data-stu-id="7d429-132">The **ReportAvailabilityAtThisTime** method was created in case you need to determine if the queue is available at the current time of day.</span></span>  
  
 <span data-ttu-id="7d429-133">El método no hará <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> nada si las propiedades son iguales; porque en ese caso la impresora está disponible en todo momento.</span><span class="sxs-lookup"><span data-stu-id="7d429-133">The method will do nothing if the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are equal; because in that case the printer is available at all times.</span></span> <span data-ttu-id="7d429-134">Si son diferentes, el método obtiene la hora actual que, a continuación, <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> tiene <xref:System.Int32>que convertirse en minutos <xref:System.DateTime> totales después de la medianoche porque las <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> propiedades son s que representan minutos después de la medianoche, no objetos.</span><span class="sxs-lookup"><span data-stu-id="7d429-134">If they are different, the method gets the current time which then has to be converted into total minutes past midnight because the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are <xref:System.Int32>s representing minutes-after-midnight, not <xref:System.DateTime> objects.</span></span> <span data-ttu-id="7d429-135">Por último, el método comprueba si la hora actual se encuentra entre el inicio y las horas "hasta".</span><span class="sxs-lookup"><span data-stu-id="7d429-135">Finally, the method checks to see if the current time is between the start and "until" times.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a><span data-ttu-id="7d429-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d429-136">See also</span></span>

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
- [<span data-ttu-id="7d429-137">Operador de& (referencia de C)</span><span class="sxs-lookup"><span data-stu-id="7d429-137">& Operator (C# Reference)</span></span>](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [<span data-ttu-id="7d429-138">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="7d429-138">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="7d429-139">Información general sobre impresión</span><span class="sxs-lookup"><span data-stu-id="7d429-139">Printing Overview</span></span>](printing-overview.md)
