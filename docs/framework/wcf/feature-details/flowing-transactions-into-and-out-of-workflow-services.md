---
title: Flujo de las transacciones en los servicios de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
ms.openlocfilehash: 8b3d3e85b626d033c9ab50e93e3ceb3b86058a2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496102"
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a><span data-ttu-id="15f46-102">Flujo de las transacciones en los servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="15f46-102">Flowing Transactions into and out of Workflow Services</span></span>
<span data-ttu-id="15f46-103">Los servicios y clientes de flujo de trabajo pueden participar en las transacciones.</span><span class="sxs-lookup"><span data-stu-id="15f46-103">Workflow services and clients can participate in transactions.</span></span>  <span data-ttu-id="15f46-104">Para que una operación de servicio se convierta en parte de una transacción de ambiente, coloque una actividad de <xref:System.ServiceModel.Activities.Receive> dentro de una actividad de <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="15f46-104">For a service operation to become part of an ambient transaction, place a <xref:System.ServiceModel.Activities.Receive> activity within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="15f46-105">En cualquier llamada realizada por un objeto <xref:System.ServiceModel.Activities.Send> o una actividad de <xref:System.ServiceModel.Activities.SendReply> dentro de <xref:System.ServiceModel.Activities.TransactedReceiveScope> también se realizará dentro de la transacción de ambiente.</span><span class="sxs-lookup"><span data-stu-id="15f46-105">Any calls made by a <xref:System.ServiceModel.Activities.Send> or a <xref:System.ServiceModel.Activities.SendReply> activity within the <xref:System.ServiceModel.Activities.TransactedReceiveScope> will also be made within the ambient transaction.</span></span> <span data-ttu-id="15f46-106">Una aplicación cliente del flujo de trabajo puede crear una transacción de ambiente utilizando la actividad de <xref:System.Activities.Statements.TransactionScope> y operaciones de servicio de llamada que usen la transacción de ambiente.</span><span class="sxs-lookup"><span data-stu-id="15f46-106">A workflow client application can create an ambient transaction by using the <xref:System.Activities.Statements.TransactionScope> activity and call service operations using the ambient transaction.</span></span> <span data-ttu-id="15f46-107">Este tema sirve de guía para crear un servicio de flujo de trabajo y un cliente de flujo de trabajo que participan en transacciones.</span><span class="sxs-lookup"><span data-stu-id="15f46-107">This topic walks you through creating a workflow service and workflow client that participate in transactions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="15f46-108">Si una instancia del servicio de flujo de trabajo se carga dentro de una transacción y el flujo de trabajo contiene una actividad <xref:System.Activities.Statements.Persist>, la instancia de flujo de trabajo no responderá hasta que se agote el tiempo de espera de la transacción.</span><span class="sxs-lookup"><span data-stu-id="15f46-108">If a workflow service instance is loaded within a transaction and the workflow contains a <xref:System.Activities.Statements.Persist> activity, the workflow instance will hang until the transaction times out.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="15f46-109">Siempre que use un objeto <xref:System.ServiceModel.Activities.TransactedReceiveScope> se recomienda que coloque todas las recepciones en el flujo de trabajo dentro de actividades <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="15f46-109">Whenever you use a <xref:System.ServiceModel.Activities.TransactedReceiveScope> it is recommended to place all Receives in the workflow within <xref:System.ServiceModel.Activities.TransactedReceiveScope> activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="15f46-110">Cuando se usa el objeto <xref:System.ServiceModel.Activities.TransactedReceiveScope> y los mensajes llegan en el orden incorrecto, el flujo de trabajo se anulará al intentar entregar el primer mensaje que lo indique.</span><span class="sxs-lookup"><span data-stu-id="15f46-110">When using <xref:System.ServiceModel.Activities.TransactedReceiveScope> and messages arrive in the incorrect order, the workflow will be aborted when trying to deliver the first out of order message.</span></span> <span data-ttu-id="15f46-111">Debe asegurarse de que el flujo de trabajo siempre está en un punto de detención coherente cuando el flujo de trabajo está inactivo.</span><span class="sxs-lookup"><span data-stu-id="15f46-111">You must make sure your workflow is always at a consistent stopping point when the workflow idles.</span></span> <span data-ttu-id="15f46-112">De este modo, podrá reiniciar el flujo de trabajo a partir de un punto de persistencia anterior si el flujo de trabajo se anula.</span><span class="sxs-lookup"><span data-stu-id="15f46-112">This will allow you to restart the workflow from a previous persistence point should the workflow be aborted.</span></span>  
  
### <a name="create-a-shared-library"></a><span data-ttu-id="15f46-113">Crear una biblioteca compartida</span><span class="sxs-lookup"><span data-stu-id="15f46-113">Create a shared library</span></span>  
  
1.  <span data-ttu-id="15f46-114">Cree una nueva solución de Visual Studio vacía.</span><span class="sxs-lookup"><span data-stu-id="15f46-114">Create a new empty Visual Studio Solution.</span></span>  
  
2.  <span data-ttu-id="15f46-115">Agregue un nuevo proyecto de biblioteca de clases denominado `Common`.</span><span class="sxs-lookup"><span data-stu-id="15f46-115">Add a new class library project called `Common`.</span></span> <span data-ttu-id="15f46-116">Agregue referencias a los siguientes ensamblados:</span><span class="sxs-lookup"><span data-stu-id="15f46-116">Add references to the following assemblies:</span></span>  
  
    -   <span data-ttu-id="15f46-117">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="15f46-117">System.Activities.dll</span></span>  
  
    -   <span data-ttu-id="15f46-118">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="15f46-118">System.ServiceModel.dll</span></span>  
  
    -   <span data-ttu-id="15f46-119">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="15f46-119">System.ServiceModel.Activities.dll</span></span>  
  
    -   <span data-ttu-id="15f46-120">System.Transactions.dll</span><span class="sxs-lookup"><span data-stu-id="15f46-120">System.Transactions.dll</span></span>  
  
3.  <span data-ttu-id="15f46-121">Agregue una nueva clase denominada `PrintTransactionInfo` al proyecto `Common`.</span><span class="sxs-lookup"><span data-stu-id="15f46-121">Add a new class called `PrintTransactionInfo` to the `Common` project.</span></span> <span data-ttu-id="15f46-122">Esta clase se deriva de <xref:System.Activities.NativeActivity> y sobrecarga el método <xref:System.Activities.NativeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="15f46-122">This class is derived from <xref:System.Activities.NativeActivity> and overloads the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>  
  
    ```  
    using System;  
    using System;  
    using System.Activities;  
    using System.Transactions;  
  
    namespace Common  
    {  
        public class PrintTransactionInfo : NativeActivity  
        {  
            protected override void Execute(NativeActivityContext context)  
            {  
                RuntimeTransactionHandle rth = context.Properties.Find(typeof(RuntimeTransactionHandle).FullName) as RuntimeTransactionHandle;  
  
                if (rth == null)  
                {  
                    Console.WriteLine("There is no ambient RuntimeTransactionHandle");  
                }  
  
                Transaction t = rth.GetCurrentTransaction(context);  
  
                if (t == null)  
                {  
                    Console.WriteLine("There is no ambient transaction");  
                }  
                else  
                {  
                    Console.WriteLine("Transaction: {0} is {1}", t.TransactionInformation.DistributedIdentifier, t.TransactionInformation.Status);  
                }  
            }  
        }  
  
    }  
    ```  
  
     <span data-ttu-id="15f46-123">Esta es una actividad nativa que muestra información acerca de la transacción de ambiente y se utiliza en ambos flujos de trabajo, de cliente y de servicio, que se usan en este tema.</span><span class="sxs-lookup"><span data-stu-id="15f46-123">This is a native activity that displays information about the ambient transaction and is used in both the service and client workflows used in this topic.</span></span> <span data-ttu-id="15f46-124">Compile la solución para que esté disponible en esta actividad la **común** sección de la **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="15f46-124">Build the solution to make this activity available in the **Common** section of the **Toolbox**.</span></span>  
  
### <a name="implement-the-workflow-service"></a><span data-ttu-id="15f46-125">Implementar el servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="15f46-125">Implement the workflow service</span></span>  
  
1.  <span data-ttu-id="15f46-126">Agregar un nuevo servicio de flujo de trabajo de WCF, denominado `WorkflowService` a la `Common` proyecto.</span><span class="sxs-lookup"><span data-stu-id="15f46-126">Add a new WCF Workflow Service, called `WorkflowService` to the `Common` project.</span></span> <span data-ttu-id="15f46-127">Para ello, este derecho, seleccione la `Common` proyecto, seleccione **agregar**, **nuevo elemento...** , Seleccione **flujo de trabajo** en **plantillas instaladas** y seleccione **servicio de flujo de trabajo de WCF**.</span><span class="sxs-lookup"><span data-stu-id="15f46-127">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **WCF Workflow Service**.</span></span>  
  
     <span data-ttu-id="15f46-128">![Agregar un servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/media/addwfservice.JPG "AddWFService")</span><span class="sxs-lookup"><span data-stu-id="15f46-128">![Adding a Workflow Service](../../../../docs/framework/wcf/feature-details/media/addwfservice.JPG "AddWFService")</span></span>  
  
2.  <span data-ttu-id="15f46-129">Elimine las actividades `ReceiveRequest` y `SendResponse` predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="15f46-129">Delete the default `ReceiveRequest` and `SendResponse` activities.</span></span>  
  
3.  <span data-ttu-id="15f46-130">Arrastre y coloque una actividad de <xref:System.Activities.Statements.WriteLine> en la actividad de `Sequential Service`.</span><span class="sxs-lookup"><span data-stu-id="15f46-130">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity into the `Sequential Service` activity.</span></span> <span data-ttu-id="15f46-131">Establezca la propiedad de texto en `"Workflow Service starting ..."` como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="15f46-131">Set the text property to `"Workflow Service starting ..."` as shown in the following example.</span></span>  
  
     <span data-ttu-id="15f46-132">![Agregar una actividad WriteLine](../../../../docs/framework/wcf/feature-details/media/addwriteline.JPG "AddWriteLine")</span><span class="sxs-lookup"><span data-stu-id="15f46-132">![Adding a WriteLine activity](../../../../docs/framework/wcf/feature-details/media/addwriteline.JPG "AddWriteLine")</span></span>  
  
4.  <span data-ttu-id="15f46-133">Arrastre y coloque una actividad <xref:System.ServiceModel.Activities.TransactedReceiveScope> después de la actividad de <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="15f46-133">Drag and drop a <xref:System.ServiceModel.Activities.TransactedReceiveScope> after the <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="15f46-134">El <xref:System.ServiceModel.Activities.TransactedReceiveScope> actividad puede encontrarse en el **mensajería** sección de la **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="15f46-134">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity can be found in the **Messaging** section of the **Toolbox**.</span></span> <span data-ttu-id="15f46-135">El <xref:System.ServiceModel.Activities.TransactedReceiveScope> actividad está compuesta de dos secciones **solicitar** y **cuerpo**.</span><span class="sxs-lookup"><span data-stu-id="15f46-135">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity is composed of two sections **Request** and **Body**.</span></span> <span data-ttu-id="15f46-136">El **solicitar** sección contiene la <xref:System.ServiceModel.Activities.Receive> actividad.</span><span class="sxs-lookup"><span data-stu-id="15f46-136">The **Request** section contains the <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="15f46-137">El **cuerpo** sección contiene las actividades que se ejecutan dentro de una transacción después de que se ha recibido un mensaje.</span><span class="sxs-lookup"><span data-stu-id="15f46-137">The **Body** section contains the activities to execute within a transaction after a message has been received.</span></span>  
  
     <span data-ttu-id="15f46-138">![Agregar una actividad TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trs.JPG "TRS")</span><span class="sxs-lookup"><span data-stu-id="15f46-138">![Adding a TransactedReceiveScope activity](../../../../docs/framework/wcf/feature-details/media/trs.JPG "TRS")</span></span>  
  
5.  <span data-ttu-id="15f46-139">Seleccione el <xref:System.ServiceModel.Activities.TransactedReceiveScope> actividad y haga clic en el **Variables** botón.</span><span class="sxs-lookup"><span data-stu-id="15f46-139">Select the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity and click the **Variables** button.</span></span> <span data-ttu-id="15f46-140">Agregue las variables siguientes.</span><span class="sxs-lookup"><span data-stu-id="15f46-140">Add the following variables.</span></span>  
  
     <span data-ttu-id="15f46-141">![Agregar Variables a TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trsvariables.JPG "TRSVariables")</span><span class="sxs-lookup"><span data-stu-id="15f46-141">![Adding Variables to the TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trsvariables.JPG "TRSVariables")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15f46-142">Puede eliminar la variable de datos que está allí de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="15f46-142">You can delete the data variable that is there by default.</span></span> <span data-ttu-id="15f46-143">También puede utilizar la variable de controlador existente.</span><span class="sxs-lookup"><span data-stu-id="15f46-143">You can also use the existing handle variable.</span></span>  
  
6.  <span data-ttu-id="15f46-144">Arrastre y coloque una <xref:System.ServiceModel.Activities.Receive> actividad dentro de la **solicitar** sección de la <xref:System.ServiceModel.Activities.TransactedReceiveScope> actividad.</span><span class="sxs-lookup"><span data-stu-id="15f46-144">Drag and drop a <xref:System.ServiceModel.Activities.Receive> activity within the **Request** section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="15f46-145">Establezca las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="15f46-145">Set the following properties:</span></span>  
  
    |<span data-ttu-id="15f46-146">Property</span><span class="sxs-lookup"><span data-stu-id="15f46-146">Property</span></span>|<span data-ttu-id="15f46-147">Valor</span><span class="sxs-lookup"><span data-stu-id="15f46-147">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="15f46-148">CanCreateInstance</span><span class="sxs-lookup"><span data-stu-id="15f46-148">CanCreateInstance</span></span>|<span data-ttu-id="15f46-149">True (activar la casilla)</span><span class="sxs-lookup"><span data-stu-id="15f46-149">True (check the checkbox)</span></span>|  
    |<span data-ttu-id="15f46-150">OperationName</span><span class="sxs-lookup"><span data-stu-id="15f46-150">OperationName</span></span>|<span data-ttu-id="15f46-151">StartSample</span><span class="sxs-lookup"><span data-stu-id="15f46-151">StartSample</span></span>|  
    |<span data-ttu-id="15f46-152">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="15f46-152">ServiceContractName</span></span>|<span data-ttu-id="15f46-153">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="15f46-153">ITransactionSample</span></span>|  
  
     <span data-ttu-id="15f46-154">El flujo de trabajo debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="15f46-154">The workflow should look like this:</span></span>  
  
     <span data-ttu-id="15f46-155">![Agregar una actividad Receive](../../../../docs/framework/wcf/feature-details/media/serviceaddreceive.JPG "ServiceAddReceive")</span><span class="sxs-lookup"><span data-stu-id="15f46-155">![Adding a Receive activity](../../../../docs/framework/wcf/feature-details/media/serviceaddreceive.JPG "ServiceAddReceive")</span></span>  
  
7.  <span data-ttu-id="15f46-156">Haga clic en el **definir...**  vincular en el <xref:System.ServiceModel.Activities.Receive> actividad y realice la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="15f46-156">Click the **Define...** link in the <xref:System.ServiceModel.Activities.Receive> activity and make the following settings:</span></span>  
  
     <span data-ttu-id="15f46-157">![Establecer configuración de mensajes de la actividad Receive](../../../../docs/framework/wcf/feature-details/media/receivemessagesettings.JPG "ReceiveMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="15f46-157">![Setting message settings for the Recieve activity](../../../../docs/framework/wcf/feature-details/media/receivemessagesettings.JPG "ReceiveMessageSettings")</span></span>  
  
8.  <span data-ttu-id="15f46-158">Arrastre y coloque una actividad de <xref:System.Activities.Statements.Sequence> en la sección Cuerpo de <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="15f46-158">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the Body section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="15f46-159">Dentro de la actividad de <xref:System.Activities.Statements.Sequence>, arrastre las dos actividades de <xref:System.Activities.Statements.WriteLine> y establezca las propiedades <xref:System.Activities.Statements.WriteLine.Text%2A> como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="15f46-159">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop two <xref:System.Activities.Statements.WriteLine> activities and set the <xref:System.Activities.Statements.WriteLine.Text%2A> properties as shown in the following table.</span></span>  
  
    |<span data-ttu-id="15f46-160">Actividad</span><span class="sxs-lookup"><span data-stu-id="15f46-160">Activity</span></span>|<span data-ttu-id="15f46-161">Valor</span><span class="sxs-lookup"><span data-stu-id="15f46-161">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="15f46-162">Primera propiedad WriteLine</span><span class="sxs-lookup"><span data-stu-id="15f46-162">1st WriteLine</span></span>|<span data-ttu-id="15f46-163">"Servicio: recepción completada"</span><span class="sxs-lookup"><span data-stu-id="15f46-163">"Service: Receive Completed"</span></span>|  
    |<span data-ttu-id="15f46-164">Segunda propiedad WriteLine</span><span class="sxs-lookup"><span data-stu-id="15f46-164">2nd WriteLine</span></span>|<span data-ttu-id="15f46-165">"Servicio: recibido = " + requestMessage</span><span class="sxs-lookup"><span data-stu-id="15f46-165">"Service: Received = " + requestMessage</span></span>|  
  
     <span data-ttu-id="15f46-166">El flujo de trabajo ahora debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="15f46-166">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="15f46-167">![Agregar actividades WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingwritelines.JPG "AfterAddingWriteLines")</span><span class="sxs-lookup"><span data-stu-id="15f46-167">![Adding WriteLine activities](../../../../docs/framework/wcf/feature-details/media/afteraddingwritelines.JPG "AfterAddingWriteLines")</span></span>  
  
9. <span data-ttu-id="15f46-168">Arrastre y coloque el `PrintTransactionInfo` actividad después de la segunda <xref:System.Activities.Statements.WriteLine> actividad en el **cuerpo** en la <xref:System.ServiceModel.Activities.TransactedReceiveScope> actividad.</span><span class="sxs-lookup"><span data-stu-id="15f46-168">Drag and drop the `PrintTransactionInfo` activity after the second <xref:System.Activities.Statements.WriteLine> activity in the **Body** in the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span>  
  
     <span data-ttu-id="15f46-169">![Después de agregar PrintTransactionInfo](../../../../docs/framework/wcf/feature-details/media/afteraddingprinttransactioninfo.JPG "AfterAddingPrintTransactionInfo")</span><span class="sxs-lookup"><span data-stu-id="15f46-169">![After adding PrintTransactionInfo](../../../../docs/framework/wcf/feature-details/media/afteraddingprinttransactioninfo.JPG "AfterAddingPrintTransactionInfo")</span></span>  
  
10. <span data-ttu-id="15f46-170">Arrastre y coloque una actividad de <xref:System.Activities.Statements.Assign> después de la actividad de `PrintTransactionInfo` y establezca sus propiedades según la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="15f46-170">Drag and drop an <xref:System.Activities.Statements.Assign> activity after the `PrintTransactionInfo` activity and set its properties according to the following table.</span></span>  
  
    |<span data-ttu-id="15f46-171">Property</span><span class="sxs-lookup"><span data-stu-id="15f46-171">Property</span></span>|<span data-ttu-id="15f46-172">Valor</span><span class="sxs-lookup"><span data-stu-id="15f46-172">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="15f46-173">En</span><span class="sxs-lookup"><span data-stu-id="15f46-173">To</span></span>|<span data-ttu-id="15f46-174">replyMessage</span><span class="sxs-lookup"><span data-stu-id="15f46-174">replyMessage</span></span>|  
    |<span data-ttu-id="15f46-175">Valor</span><span class="sxs-lookup"><span data-stu-id="15f46-175">Value</span></span>|<span data-ttu-id="15f46-176">"Servicio: enviando respuesta."</span><span class="sxs-lookup"><span data-stu-id="15f46-176">"Service: Sending reply."</span></span>|  
  
11. <span data-ttu-id="15f46-177">Arrastre y coloque una actividad de <xref:System.Activities.Statements.WriteLine> después de la actividad de <xref:System.Activities.Statements.Assign> y establezca su propiedad <xref:System.Activities.Statements.WriteLine.Text%2A> en "Servicio: iniciar respuesta".</span><span class="sxs-lookup"><span data-stu-id="15f46-177">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.Activities.Statements.Assign> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Begin reply."</span></span>  
  
     <span data-ttu-id="15f46-178">El flujo de trabajo ahora debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="15f46-178">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="15f46-179">![Después de agregar Assign y WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingsbrwriteline.JPG "AfterAddingSBRWriteLine")</span><span class="sxs-lookup"><span data-stu-id="15f46-179">![After adding Assign and WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingsbrwriteline.JPG "AfterAddingSBRWriteLine")</span></span>  
  
12. <span data-ttu-id="15f46-180">Haga clic con el <xref:System.ServiceModel.Activities.Receive> actividad y seleccione **crear SendReply** y pegarlos después de la última <xref:System.Activities.Statements.WriteLine> actividad.</span><span class="sxs-lookup"><span data-stu-id="15f46-180">Right click the <xref:System.ServiceModel.Activities.Receive> activity and select **Create SendReply** and paste it after the last <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="15f46-181">Haga clic en el **definir...**  vincular en el `SendReplyToReceive` actividad y realice la siguiente configuración.</span><span class="sxs-lookup"><span data-stu-id="15f46-181">Click the **Define...** link in the `SendReplyToReceive` activity and make the following settings.</span></span>  
  
     <span data-ttu-id="15f46-182">![Configuración de mensajes de respuesta](../../../../docs/framework/wcf/feature-details/media/replymessagesettings.JPG "ReplyMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="15f46-182">![Reply message settings](../../../../docs/framework/wcf/feature-details/media/replymessagesettings.JPG "ReplyMessageSettings")</span></span>  
  
13. <span data-ttu-id="15f46-183">Arrastre y coloque una <xref:System.Activities.Statements.WriteLine> actividad después de la `SendReplyToReceive` actividad y el conjunto tiene <xref:System.Activities.Statements.WriteLine.Text%2A> propiedad en "servicio: respuesta enviada."</span><span class="sxs-lookup"><span data-stu-id="15f46-183">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `SendReplyToReceive` activity and set it’s <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Reply sent."</span></span>  
  
14. <span data-ttu-id="15f46-184">Arrastre y coloque una actividad de <xref:System.Activities.Statements.WriteLine> en la parte inferior del flujo de trabajo y establezca su propiedad <xref:System.Activities.Statements.WriteLine.Text%2A> en "Servicio: el flujo de trabajo finaliza, presione Entrar para salir".</span><span class="sxs-lookup"><span data-stu-id="15f46-184">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the bottom of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Workflow ends, press ENTER to exit."</span></span>  
  
     <span data-ttu-id="15f46-185">El flujo de trabajo del servicio completado debería ser similar a:</span><span class="sxs-lookup"><span data-stu-id="15f46-185">The completed service workflow should look like this:</span></span>  
  
     <span data-ttu-id="15f46-186">![Completar flujo de trabajo de servicio](../../../../docs/framework/wcf/feature-details/media/servicecomplete.jpg "ServiceComplete")</span><span class="sxs-lookup"><span data-stu-id="15f46-186">![Complete Service Workflow](../../../../docs/framework/wcf/feature-details/media/servicecomplete.jpg "ServiceComplete")</span></span>  
  
### <a name="implement-the-workflow-client"></a><span data-ttu-id="15f46-187">Implementar el cliente de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="15f46-187">Implement the workflow client</span></span>  
  
1.  <span data-ttu-id="15f46-188">Agregue una nueva aplicación Flujo de trabajo WCF, denominada `WorkflowClient`, al proyecto `Common`.</span><span class="sxs-lookup"><span data-stu-id="15f46-188">Add a new WCF Workflow application, called `WorkflowClient` to the `Common` project.</span></span> <span data-ttu-id="15f46-189">Para ello, este derecho, seleccione la `Common` proyecto, seleccione **agregar**, **nuevo elemento...** , Seleccione **flujo de trabajo** en **plantillas instaladas** y seleccione **actividad**.</span><span class="sxs-lookup"><span data-stu-id="15f46-189">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **Activity**.</span></span>  
  
     <span data-ttu-id="15f46-190">![Agregar un proyecto de actividad](../../../../docs/framework/wcf/feature-details/media/addactivity.JPG "AddActivity")</span><span class="sxs-lookup"><span data-stu-id="15f46-190">![Add an Activity project](../../../../docs/framework/wcf/feature-details/media/addactivity.JPG "AddActivity")</span></span>  
  
2.  <span data-ttu-id="15f46-191">Arrastre y coloque una actividad <xref:System.Activities.Statements.Sequence> en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="15f46-191">Drag and drop a <xref:System.Activities.Statements.Sequence> activity onto the design surface.</span></span>  
  
3.  <span data-ttu-id="15f46-192">Dentro de la actividad <xref:System.Activities.Statements.Sequence>, arrastre y coloque una actividad de <xref:System.Activities.Statements.WriteLine> y establezca su propiedad <xref:System.Activities.Statements.WriteLine.Text%2A> en `"Client: Workflow starting"`.</span><span class="sxs-lookup"><span data-stu-id="15f46-192">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop a <xref:System.Activities.Statements.WriteLine> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to `"Client: Workflow starting"`.</span></span> <span data-ttu-id="15f46-193">El flujo de trabajo ahora debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="15f46-193">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="15f46-194">![Agregar una actividad WriteLine](../../../../docs/framework/wcf/feature-details/media/clientaddwriteline.JPG "ClientAddWriteLine")</span><span class="sxs-lookup"><span data-stu-id="15f46-194">![Add a WriteLine activity](../../../../docs/framework/wcf/feature-details/media/clientaddwriteline.JPG "ClientAddWriteLine")</span></span>  
  
4.  <span data-ttu-id="15f46-195">Arrastre y coloque una actividad de <xref:System.Activities.Statements.TransactionScope> después de la actividad de <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="15f46-195">Drag and drop a <xref:System.Activities.Statements.TransactionScope> activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  <span data-ttu-id="15f46-196">Seleccione la actividad de <xref:System.Activities.Statements.TransactionScope>, haga clic en el botón Variables y agregue las siguientes variables.</span><span class="sxs-lookup"><span data-stu-id="15f46-196">Select the <xref:System.Activities.Statements.TransactionScope> activity, click the Variables button and add the following variables.</span></span>  
  
     <span data-ttu-id="15f46-197">![Agregar variables a TransactionScope](../../../../docs/framework/wcf/feature-details/media/tsvariables.JPG "TSVariables")</span><span class="sxs-lookup"><span data-stu-id="15f46-197">![Add variables to the TransactionScope](../../../../docs/framework/wcf/feature-details/media/tsvariables.JPG "TSVariables")</span></span>  
  
5.  <span data-ttu-id="15f46-198">Arrastre y coloque una actividad de <xref:System.Activities.Statements.Sequence> en el cuerpo de la actividad de <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="15f46-198">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the body of the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
6.  <span data-ttu-id="15f46-199">Arrastre y coloque una actividad de `PrintTransactionInfo` dentro de <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="15f46-199">Drag and drop a `PrintTransactionInfo` activity within the <xref:System.Activities.Statements.Sequence></span></span>  
  
7.  <span data-ttu-id="15f46-200">Arrastre y coloque una <xref:System.Activities.Statements.WriteLine> actividad después de la `PrintTransactionInfo` actividad y establezca su <xref:System.Activities.Statements.WriteLine.Text%2A> propiedad en "Cliente: comenzando envío".</span><span class="sxs-lookup"><span data-stu-id="15f46-200">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `PrintTransactionInfo` activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Beginning Send".</span></span> <span data-ttu-id="15f46-201">El flujo de trabajo ahora debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="15f46-201">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="15f46-202">![Agregar actividades](../../../../docs/framework/wcf/feature-details/media/clientaddcbswriteline.JPG "ClientAddCBSWriteLine")</span><span class="sxs-lookup"><span data-stu-id="15f46-202">![Adding activities](../../../../docs/framework/wcf/feature-details/media/clientaddcbswriteline.JPG "ClientAddCBSWriteLine")</span></span>  
  
8.  <span data-ttu-id="15f46-203">Arrastre y coloque una actividad de <xref:System.ServiceModel.Activities.Send> después de la actividad de <xref:System.Activities.Statements.Assign> y establezca las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="15f46-203">Drag and drop a <xref:System.ServiceModel.Activities.Send> activity after the <xref:System.Activities.Statements.Assign> activity and set the following properties:</span></span>  
  
    |<span data-ttu-id="15f46-204">Property</span><span class="sxs-lookup"><span data-stu-id="15f46-204">Property</span></span>|<span data-ttu-id="15f46-205">Valor</span><span class="sxs-lookup"><span data-stu-id="15f46-205">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="15f46-206">EndpointConfigurationName</span><span class="sxs-lookup"><span data-stu-id="15f46-206">EndpointConfigurationName</span></span>|<span data-ttu-id="15f46-207">workflowServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="15f46-207">workflowServiceEndpoint</span></span>|  
    |<span data-ttu-id="15f46-208">OperationName</span><span class="sxs-lookup"><span data-stu-id="15f46-208">OperationName</span></span>|<span data-ttu-id="15f46-209">StartSample</span><span class="sxs-lookup"><span data-stu-id="15f46-209">StartSample</span></span>|  
    |<span data-ttu-id="15f46-210">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="15f46-210">ServiceContractName</span></span>|<span data-ttu-id="15f46-211">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="15f46-211">ITransactionSample</span></span>|  
  
     <span data-ttu-id="15f46-212">El flujo de trabajo ahora debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="15f46-212">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="15f46-213">![Establecer las propiedades de la actividad Send](../../../../docs/framework/wcf/feature-details/media/clientsendsettings.JPG "ClientSendSettings")</span><span class="sxs-lookup"><span data-stu-id="15f46-213">![Setting the Send activity properties](../../../../docs/framework/wcf/feature-details/media/clientsendsettings.JPG "ClientSendSettings")</span></span>  
  
9. <span data-ttu-id="15f46-214">Haga clic en el **definir...**  vincular y realice la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="15f46-214">Click the **Define...** link and make the following settings:</span></span>  
  
     <span data-ttu-id="15f46-215">![Configuración de mensajes de actividad Send](../../../../docs/framework/wcf/feature-details/media/sendmessagesettings.JPG "SendMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="15f46-215">![Send activity message settings](../../../../docs/framework/wcf/feature-details/media/sendmessagesettings.JPG "SendMessageSettings")</span></span>  
  
10. <span data-ttu-id="15f46-216">Haga clic con el <xref:System.ServiceModel.Activities.Send> actividad y seleccione **crear ReceiveReply**.</span><span class="sxs-lookup"><span data-stu-id="15f46-216">Right click the <xref:System.ServiceModel.Activities.Send> activity and select **Create ReceiveReply**.</span></span> <span data-ttu-id="15f46-217">La actividad de <xref:System.ServiceModel.Activities.ReceiveReply> se colocará automáticamente después de la actividad de <xref:System.ServiceModel.Activities.Send>.</span><span class="sxs-lookup"><span data-stu-id="15f46-217">The <xref:System.ServiceModel.Activities.ReceiveReply> activity will be automatically placed after the <xref:System.ServiceModel.Activities.Send> activity.</span></span>  
  
11. <span data-ttu-id="15f46-218">Haga clic en el vínculo Definir... en la actividad ReceiveReplyForSend y realice la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="15f46-218">Click the Define... link on the ReceiveReplyForSend activity and make the following settings:</span></span>  
  
     <span data-ttu-id="15f46-219">![Establecer la configuración de mensajes ReceiveForSend](../../../../docs/framework/wcf/feature-details/media/clientreplymessagesettings.JPG "ClientReplyMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="15f46-219">![Setting the ReceiveForSend message settings](../../../../docs/framework/wcf/feature-details/media/clientreplymessagesettings.JPG "ClientReplyMessageSettings")</span></span>  
  
12. <span data-ttu-id="15f46-220">Arrastre y coloque una actividad de <xref:System.Activities.Statements.WriteLine> entre las actividades de <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Activities.ReceiveReply>, y establezca su propiedad <xref:System.Activities.Statements.WriteLine.Text%2A> en "Cliente: envío completado".</span><span class="sxs-lookup"><span data-stu-id="15f46-220">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity between the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> activities and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Send complete."</span></span>  
  
13. <span data-ttu-id="15f46-221">Arrastre y coloque una actividad de <xref:System.Activities.Statements.WriteLine> después de la actividad de <xref:System.ServiceModel.Activities.ReceiveReply> y establezca su propiedad <xref:System.Activities.Statements.WriteLine.Text%2A> en "Cliente: respuesta recibida = " + replyMessage</span><span class="sxs-lookup"><span data-stu-id="15f46-221">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.ServiceModel.Activities.ReceiveReply> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client side: Reply received = " + replyMessage</span></span>  
  
14. <span data-ttu-id="15f46-222">Arrastre y coloque una actividad de `PrintTransactionInfo` después de la actividad de <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="15f46-222">Drag and drop a `PrintTransactionInfo` activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
15. <span data-ttu-id="15f46-223">Arrastre y coloque una actividad de <xref:System.Activities.Statements.WriteLine> al final del flujo de trabajo y establezca su propiedad <xref:System.Activities.Statements.WriteLine.Text%2A> en "El flujo de cliente finaliza".</span><span class="sxs-lookup"><span data-stu-id="15f46-223">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the end of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client workflow ends."</span></span> <span data-ttu-id="15f46-224">El flujo de trabajo del cliente completado debería parecerse al del siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="15f46-224">The completed client workflow should look like the following diagram.</span></span>  
  
     <span data-ttu-id="15f46-225">![El cliente workfliow](../../../../docs/framework/wcf/feature-details/media/clientcompleteworkflow.jpg "ClientCompleteWorkflow")</span><span class="sxs-lookup"><span data-stu-id="15f46-225">![The completed client workfliow](../../../../docs/framework/wcf/feature-details/media/clientcompleteworkflow.jpg "ClientCompleteWorkflow")</span></span>  
  
16. <span data-ttu-id="15f46-226">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="15f46-226">Build the solution.</span></span>  
  
### <a name="create-the-service-application"></a><span data-ttu-id="15f46-227">Crear la aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="15f46-227">Create the Service application</span></span>  
  
1.  <span data-ttu-id="15f46-228">Agregue un nuevo proyecto Aplicación de consola denominado `Service` a la solución.</span><span class="sxs-lookup"><span data-stu-id="15f46-228">Add a new Console Application project called `Service` to the solution.</span></span> <span data-ttu-id="15f46-229">Agregue referencias a los siguientes ensamblados:</span><span class="sxs-lookup"><span data-stu-id="15f46-229">Add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="15f46-230">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="15f46-230">System.Activities.dll</span></span>  
  
    2.  <span data-ttu-id="15f46-231">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="15f46-231">System.ServiceModel.dll</span></span>  
  
    3.  <span data-ttu-id="15f46-232">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="15f46-232">System.ServiceModel.Activities.dll</span></span>  
  
2.  <span data-ttu-id="15f46-233">Abra el archivo Program.cs generado y el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="15f46-233">Open the generated Program.cs file and the following code:</span></span>  
  
    ```  
    static void Main()  
          {  
              Console.WriteLine("Building the server.");  
              using (WorkflowServiceHost host = new WorkflowServiceHost(new DeclarativeServiceWorkflow(), new Uri("net.tcp://localhost:8000/TransactedReceiveService/Declarative")))  
              {                
                  //Start the server  
                  host.Open();  
                  Console.WriteLine("Service started.");  
  
                  Console.WriteLine();  
                  Console.ReadLine();  
                  //Shutdown  
                  host.Close();  
              };         
          }  
    ```  
  
3.  <span data-ttu-id="15f46-234">Agregue el archivo app.config siguiente al proyecto.</span><span class="sxs-lookup"><span data-stu-id="15f46-234">Add the following app.config file to the project.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <!-- Copyright © Microsoft Corporation.  All rights reserved. -->  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding transactionFlow="true" />  
                </netTcpBinding>  
            </bindings>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="create-the-client-application"></a><span data-ttu-id="15f46-235">Crear la aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="15f46-235">Create the client application</span></span>  
  
1.  <span data-ttu-id="15f46-236">Agregue un nuevo proyecto Aplicación de consola denominado `Client` a la solución.</span><span class="sxs-lookup"><span data-stu-id="15f46-236">Add a new Console Application project called `Client` to the solution.</span></span> <span data-ttu-id="15f46-237">Agregue una referencia a System.Activities.dll.</span><span class="sxs-lookup"><span data-stu-id="15f46-237">Add a reference to System.Activities.dll.</span></span>  
  
2.  <span data-ttu-id="15f46-238">Abra el archivo Program.cs y agregue el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="15f46-238">Open the program.cs file and add the following code.</span></span>  
  
    ```  
    class Program  
        {  
  
            private static AutoResetEvent syncEvent = new AutoResetEvent(false);  
  
            static void Main(string[] args)  
            {  
                //Build client  
                Console.WriteLine("Building the client.");  
                WorkflowApplication client = new WorkflowApplication(new DeclarativeClientWorkflow());  
                client.Completed = Program.Completed;  
                client.Aborted = Program.Aborted;  
                client.OnUnhandledException = Program.OnUnhandledException;  
  
                //Wait for service to start  
                Console.WriteLine("Press ENTER once service is started.");  
                Console.ReadLine();  
  
                //Start the client              
                Console.WriteLine("Starting the client.");  
                client.Run();  
                syncEvent.WaitOne();  
  
                //Sample complete  
                Console.WriteLine();  
                Console.WriteLine("Client complete. Press ENTER to exit.");  
                Console.ReadLine();  
            }  
  
            private static void Completed(WorkflowApplicationCompletedEventArgs e)  
            {  
                Program.syncEvent.Set();  
            }  
  
            private static void Aborted(WorkflowApplicationAbortedEventArgs e)  
            {  
                Console.WriteLine("Client Aborted: {0}", e.Reason);  
                Program.syncEvent.Set();  
            }  
  
            private static UnhandledExceptionAction OnUnhandledException(WorkflowApplicationUnhandledExceptionEventArgs e)  
            {  
                Console.WriteLine("Client had an unhandled exception: {0}", e.UnhandledException);  
                return UnhandledExceptionAction.Cancel;  
            }  
        }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="15f46-239">Vea también</span><span class="sxs-lookup"><span data-stu-id="15f46-239">See Also</span></span>  
 [<span data-ttu-id="15f46-240">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="15f46-240">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="15f46-241">Información general sobre las transacciones de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="15f46-241">Windows Communication Foundation Transactions Overview</span></span>](../../../../docs/framework/wcf/feature-details/transactions-overview.md)  
 [<span data-ttu-id="15f46-242">Uso de TransactedReceiveScope</span><span class="sxs-lookup"><span data-stu-id="15f46-242">Use of TransactedReceiveScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)
