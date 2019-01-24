---
title: Flujo de las transacciones en los servicios de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
ms.openlocfilehash: 4a5cde045c6c676c2efc694c67fd049b6eb611b2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708641"
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a><span data-ttu-id="52204-102">Flujo de las transacciones en los servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="52204-102">Flowing Transactions into and out of Workflow Services</span></span>
<span data-ttu-id="52204-103">Los servicios y clientes de flujo de trabajo pueden participar en las transacciones.</span><span class="sxs-lookup"><span data-stu-id="52204-103">Workflow services and clients can participate in transactions.</span></span>  <span data-ttu-id="52204-104">Para que una operación de servicio se convierta en parte de una transacción de ambiente, coloque una actividad de <xref:System.ServiceModel.Activities.Receive> dentro de una actividad de <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="52204-104">For a service operation to become part of an ambient transaction, place a <xref:System.ServiceModel.Activities.Receive> activity within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="52204-105">En cualquier llamada realizada por un objeto <xref:System.ServiceModel.Activities.Send> o una actividad de <xref:System.ServiceModel.Activities.SendReply> dentro de <xref:System.ServiceModel.Activities.TransactedReceiveScope> también se realizará dentro de la transacción de ambiente.</span><span class="sxs-lookup"><span data-stu-id="52204-105">Any calls made by a <xref:System.ServiceModel.Activities.Send> or a <xref:System.ServiceModel.Activities.SendReply> activity within the <xref:System.ServiceModel.Activities.TransactedReceiveScope> will also be made within the ambient transaction.</span></span> <span data-ttu-id="52204-106">Una aplicación cliente del flujo de trabajo puede crear una transacción de ambiente utilizando la actividad de <xref:System.Activities.Statements.TransactionScope> y operaciones de servicio de llamada que usen la transacción de ambiente.</span><span class="sxs-lookup"><span data-stu-id="52204-106">A workflow client application can create an ambient transaction by using the <xref:System.Activities.Statements.TransactionScope> activity and call service operations using the ambient transaction.</span></span> <span data-ttu-id="52204-107">Este tema sirve de guía para crear un servicio de flujo de trabajo y un cliente de flujo de trabajo que participan en transacciones.</span><span class="sxs-lookup"><span data-stu-id="52204-107">This topic walks you through creating a workflow service and workflow client that participate in transactions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="52204-108">Si una instancia del servicio de flujo de trabajo se carga dentro de una transacción y el flujo de trabajo contiene una actividad <xref:System.Activities.Statements.Persist>, la instancia de flujo de trabajo no responderá hasta que se agote el tiempo de espera de la transacción.</span><span class="sxs-lookup"><span data-stu-id="52204-108">If a workflow service instance is loaded within a transaction and the workflow contains a <xref:System.Activities.Statements.Persist> activity, the workflow instance will hang until the transaction times out.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="52204-109">Siempre que use un objeto <xref:System.ServiceModel.Activities.TransactedReceiveScope> se recomienda que coloque todas las recepciones en el flujo de trabajo dentro de actividades <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="52204-109">Whenever you use a <xref:System.ServiceModel.Activities.TransactedReceiveScope> it is recommended to place all Receives in the workflow within <xref:System.ServiceModel.Activities.TransactedReceiveScope> activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="52204-110">Cuando se usa el objeto <xref:System.ServiceModel.Activities.TransactedReceiveScope> y los mensajes llegan en el orden incorrecto, el flujo de trabajo se anulará al intentar entregar el primer mensaje que lo indique.</span><span class="sxs-lookup"><span data-stu-id="52204-110">When using <xref:System.ServiceModel.Activities.TransactedReceiveScope> and messages arrive in the incorrect order, the workflow will be aborted when trying to deliver the first out of order message.</span></span> <span data-ttu-id="52204-111">Debe asegurarse de que el flujo de trabajo siempre está en un punto de detención coherente cuando el flujo de trabajo está inactivo.</span><span class="sxs-lookup"><span data-stu-id="52204-111">You must make sure your workflow is always at a consistent stopping point when the workflow idles.</span></span> <span data-ttu-id="52204-112">De este modo, podrá reiniciar el flujo de trabajo a partir de un punto de persistencia anterior si el flujo de trabajo se anula.</span><span class="sxs-lookup"><span data-stu-id="52204-112">This will allow you to restart the workflow from a previous persistence point should the workflow be aborted.</span></span>  
  
### <a name="create-a-shared-library"></a><span data-ttu-id="52204-113">Crear una biblioteca compartida</span><span class="sxs-lookup"><span data-stu-id="52204-113">Create a shared library</span></span>  
  
1.  <span data-ttu-id="52204-114">Cree una nueva solución de Visual Studio vacía.</span><span class="sxs-lookup"><span data-stu-id="52204-114">Create a new empty Visual Studio Solution.</span></span>  
  
2.  <span data-ttu-id="52204-115">Agregue un nuevo proyecto de biblioteca de clases denominado `Common`.</span><span class="sxs-lookup"><span data-stu-id="52204-115">Add a new class library project called `Common`.</span></span> <span data-ttu-id="52204-116">Agregue referencias a los siguientes ensamblados:</span><span class="sxs-lookup"><span data-stu-id="52204-116">Add references to the following assemblies:</span></span>  
  
    -   <span data-ttu-id="52204-117">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="52204-117">System.Activities.dll</span></span>  
  
    -   <span data-ttu-id="52204-118">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="52204-118">System.ServiceModel.dll</span></span>  
  
    -   <span data-ttu-id="52204-119">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="52204-119">System.ServiceModel.Activities.dll</span></span>  
  
    -   <span data-ttu-id="52204-120">System.Transactions.dll</span><span class="sxs-lookup"><span data-stu-id="52204-120">System.Transactions.dll</span></span>  
  
3.  <span data-ttu-id="52204-121">Agregue una nueva clase denominada `PrintTransactionInfo` al proyecto `Common`.</span><span class="sxs-lookup"><span data-stu-id="52204-121">Add a new class called `PrintTransactionInfo` to the `Common` project.</span></span> <span data-ttu-id="52204-122">Esta clase se deriva de <xref:System.Activities.NativeActivity> y sobrecarga el método <xref:System.Activities.NativeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="52204-122">This class is derived from <xref:System.Activities.NativeActivity> and overloads the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>  
  
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
  
     <span data-ttu-id="52204-123">Esta es una actividad nativa que muestra información acerca de la transacción de ambiente y se utiliza en ambos flujos de trabajo, de cliente y de servicio, que se usan en este tema.</span><span class="sxs-lookup"><span data-stu-id="52204-123">This is a native activity that displays information about the ambient transaction and is used in both the service and client workflows used in this topic.</span></span> <span data-ttu-id="52204-124">Compile la solución para que estén disponibles en esta actividad la **común** sección de la **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="52204-124">Build the solution to make this activity available in the **Common** section of the **Toolbox**.</span></span>  
  
### <a name="implement-the-workflow-service"></a><span data-ttu-id="52204-125">Implementar el servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="52204-125">Implement the workflow service</span></span>  
  
1.  <span data-ttu-id="52204-126">Agregar un nuevo servicio de flujo de trabajo WCF denominado `WorkflowService` a la `Common` proyecto.</span><span class="sxs-lookup"><span data-stu-id="52204-126">Add a new WCF Workflow Service, called `WorkflowService` to the `Common` project.</span></span> <span data-ttu-id="52204-127">Para ello, seleccione derecho la `Common` proyecto, seleccione **agregar**, **nuevo elemento...** , Seleccione **flujo de trabajo** en **plantillas instaladas** y seleccione **servicio de flujo de trabajo de WCF**.</span><span class="sxs-lookup"><span data-stu-id="52204-127">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **WCF Workflow Service**.</span></span>  
  
     <span data-ttu-id="52204-128">![Agregar un servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/media/addwfservice.JPG "AddWFService")</span><span class="sxs-lookup"><span data-stu-id="52204-128">![Adding a Workflow Service](../../../../docs/framework/wcf/feature-details/media/addwfservice.JPG "AddWFService")</span></span>  
  
2.  <span data-ttu-id="52204-129">Elimine las actividades `ReceiveRequest` y `SendResponse` predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="52204-129">Delete the default `ReceiveRequest` and `SendResponse` activities.</span></span>  
  
3.  <span data-ttu-id="52204-130">Arrastre y coloque una actividad de <xref:System.Activities.Statements.WriteLine> en la actividad de `Sequential Service`.</span><span class="sxs-lookup"><span data-stu-id="52204-130">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity into the `Sequential Service` activity.</span></span> <span data-ttu-id="52204-131">Establezca la propiedad de texto en `"Workflow Service starting ..."` como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="52204-131">Set the text property to `"Workflow Service starting ..."` as shown in the following example.</span></span>  
  
     <span data-ttu-id="52204-132">![Agregar una actividad WriteLine](../../../../docs/framework/wcf/feature-details/media/addwriteline.JPG "AddWriteLine")</span><span class="sxs-lookup"><span data-stu-id="52204-132">![Adding a WriteLine activity](../../../../docs/framework/wcf/feature-details/media/addwriteline.JPG "AddWriteLine")</span></span>  
  
4.  <span data-ttu-id="52204-133">Arrastre y coloque una actividad <xref:System.ServiceModel.Activities.TransactedReceiveScope> después de la actividad de <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="52204-133">Drag and drop a <xref:System.ServiceModel.Activities.TransactedReceiveScope> after the <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="52204-134">El <xref:System.ServiceModel.Activities.TransactedReceiveScope> actividad puede encontrarse en el **mensajería** sección de la **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="52204-134">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity can be found in the **Messaging** section of the **Toolbox**.</span></span> <span data-ttu-id="52204-135">El <xref:System.ServiceModel.Activities.TransactedReceiveScope> actividad se compone de dos secciones **solicitar** y **cuerpo**.</span><span class="sxs-lookup"><span data-stu-id="52204-135">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity is composed of two sections **Request** and **Body**.</span></span> <span data-ttu-id="52204-136">El **solicitar** sección contiene la <xref:System.ServiceModel.Activities.Receive> actividad.</span><span class="sxs-lookup"><span data-stu-id="52204-136">The **Request** section contains the <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="52204-137">El **cuerpo** sección contiene las actividades que se ejecutan dentro de una transacción después de que ha recibido un mensaje.</span><span class="sxs-lookup"><span data-stu-id="52204-137">The **Body** section contains the activities to execute within a transaction after a message has been received.</span></span>  
  
     <span data-ttu-id="52204-138">![Agregar una actividad TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trs.JPG "TRS")</span><span class="sxs-lookup"><span data-stu-id="52204-138">![Adding a TransactedReceiveScope activity](../../../../docs/framework/wcf/feature-details/media/trs.JPG "TRS")</span></span>  
  
5.  <span data-ttu-id="52204-139">Seleccione el <xref:System.ServiceModel.Activities.TransactedReceiveScope> actividad y haga clic en el **Variables** botón.</span><span class="sxs-lookup"><span data-stu-id="52204-139">Select the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity and click the **Variables** button.</span></span> <span data-ttu-id="52204-140">Agregue las variables siguientes.</span><span class="sxs-lookup"><span data-stu-id="52204-140">Add the following variables.</span></span>  
  
     <span data-ttu-id="52204-141">![Agregar Variables a TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trsvariables.JPG "TRSVariables")</span><span class="sxs-lookup"><span data-stu-id="52204-141">![Adding Variables to the TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trsvariables.JPG "TRSVariables")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52204-142">Puede eliminar la variable de datos que está allí de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="52204-142">You can delete the data variable that is there by default.</span></span> <span data-ttu-id="52204-143">También puede utilizar la variable de controlador existente.</span><span class="sxs-lookup"><span data-stu-id="52204-143">You can also use the existing handle variable.</span></span>  
  
6.  <span data-ttu-id="52204-144">Arrastre y coloque un <xref:System.ServiceModel.Activities.Receive> actividad dentro de la **solicitar** sección de la <xref:System.ServiceModel.Activities.TransactedReceiveScope> actividad.</span><span class="sxs-lookup"><span data-stu-id="52204-144">Drag and drop a <xref:System.ServiceModel.Activities.Receive> activity within the **Request** section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="52204-145">Establezca las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="52204-145">Set the following properties:</span></span>  
  
    |<span data-ttu-id="52204-146">Property</span><span class="sxs-lookup"><span data-stu-id="52204-146">Property</span></span>|<span data-ttu-id="52204-147">Valor</span><span class="sxs-lookup"><span data-stu-id="52204-147">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="52204-148">CanCreateInstance</span><span class="sxs-lookup"><span data-stu-id="52204-148">CanCreateInstance</span></span>|<span data-ttu-id="52204-149">True (activar la casilla)</span><span class="sxs-lookup"><span data-stu-id="52204-149">True (check the checkbox)</span></span>|  
    |<span data-ttu-id="52204-150">OperationName</span><span class="sxs-lookup"><span data-stu-id="52204-150">OperationName</span></span>|<span data-ttu-id="52204-151">StartSample</span><span class="sxs-lookup"><span data-stu-id="52204-151">StartSample</span></span>|  
    |<span data-ttu-id="52204-152">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="52204-152">ServiceContractName</span></span>|<span data-ttu-id="52204-153">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="52204-153">ITransactionSample</span></span>|  
  
     <span data-ttu-id="52204-154">El flujo de trabajo debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="52204-154">The workflow should look like this:</span></span>  
  
     <span data-ttu-id="52204-155">![Agregar una actividad Receive](../../../../docs/framework/wcf/feature-details/media/serviceaddreceive.JPG "ServiceAddReceive")</span><span class="sxs-lookup"><span data-stu-id="52204-155">![Adding a Receive activity](../../../../docs/framework/wcf/feature-details/media/serviceaddreceive.JPG "ServiceAddReceive")</span></span>  
  
7.  <span data-ttu-id="52204-156">Haga clic en el **definir...**  vincular en la <xref:System.ServiceModel.Activities.Receive> actividad y realice la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="52204-156">Click the **Define...** link in the <xref:System.ServiceModel.Activities.Receive> activity and make the following settings:</span></span>  
  
     <span data-ttu-id="52204-157">![Configuración de mensaje de la actividad Recieve](../../../../docs/framework/wcf/feature-details/media/receivemessagesettings.JPG "ReceiveMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="52204-157">![Setting message settings for the Recieve activity](../../../../docs/framework/wcf/feature-details/media/receivemessagesettings.JPG "ReceiveMessageSettings")</span></span>  
  
8.  <span data-ttu-id="52204-158">Arrastre y coloque una actividad de <xref:System.Activities.Statements.Sequence> en la sección Cuerpo de <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="52204-158">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the Body section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="52204-159">Dentro de la actividad de <xref:System.Activities.Statements.Sequence>, arrastre las dos actividades de <xref:System.Activities.Statements.WriteLine> y establezca las propiedades <xref:System.Activities.Statements.WriteLine.Text%2A> como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="52204-159">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop two <xref:System.Activities.Statements.WriteLine> activities and set the <xref:System.Activities.Statements.WriteLine.Text%2A> properties as shown in the following table.</span></span>  
  
    |<span data-ttu-id="52204-160">Actividad</span><span class="sxs-lookup"><span data-stu-id="52204-160">Activity</span></span>|<span data-ttu-id="52204-161">Valor</span><span class="sxs-lookup"><span data-stu-id="52204-161">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="52204-162">Primera propiedad WriteLine</span><span class="sxs-lookup"><span data-stu-id="52204-162">1st WriteLine</span></span>|<span data-ttu-id="52204-163">"Servicio: Recepción completada"</span><span class="sxs-lookup"><span data-stu-id="52204-163">"Service: Receive Completed"</span></span>|  
    |<span data-ttu-id="52204-164">Segunda propiedad WriteLine</span><span class="sxs-lookup"><span data-stu-id="52204-164">2nd WriteLine</span></span>|<span data-ttu-id="52204-165">"Servicio: Recibido = "+ requestMessage</span><span class="sxs-lookup"><span data-stu-id="52204-165">"Service: Received = " + requestMessage</span></span>|  
  
     <span data-ttu-id="52204-166">El flujo de trabajo ahora debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="52204-166">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="52204-167">![Agregar actividades WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingwritelines.JPG "AfterAddingWriteLines")</span><span class="sxs-lookup"><span data-stu-id="52204-167">![Adding WriteLine activities](../../../../docs/framework/wcf/feature-details/media/afteraddingwritelines.JPG "AfterAddingWriteLines")</span></span>  
  
9. <span data-ttu-id="52204-168">Arrastre y coloque el `PrintTransactionInfo` actividad después de la segunda <xref:System.Activities.Statements.WriteLine> actividad en el **cuerpo** en el <xref:System.ServiceModel.Activities.TransactedReceiveScope> actividad.</span><span class="sxs-lookup"><span data-stu-id="52204-168">Drag and drop the `PrintTransactionInfo` activity after the second <xref:System.Activities.Statements.WriteLine> activity in the **Body** in the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span>  
  
     <span data-ttu-id="52204-169">![Después de agregar PrintTransactionInfo](../../../../docs/framework/wcf/feature-details/media/afteraddingprinttransactioninfo.JPG "AfterAddingPrintTransactionInfo")</span><span class="sxs-lookup"><span data-stu-id="52204-169">![After adding PrintTransactionInfo](../../../../docs/framework/wcf/feature-details/media/afteraddingprinttransactioninfo.JPG "AfterAddingPrintTransactionInfo")</span></span>  
  
10. <span data-ttu-id="52204-170">Arrastre y coloque una actividad de <xref:System.Activities.Statements.Assign> después de la actividad de `PrintTransactionInfo` y establezca sus propiedades según la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="52204-170">Drag and drop an <xref:System.Activities.Statements.Assign> activity after the `PrintTransactionInfo` activity and set its properties according to the following table.</span></span>  
  
    |<span data-ttu-id="52204-171">Property</span><span class="sxs-lookup"><span data-stu-id="52204-171">Property</span></span>|<span data-ttu-id="52204-172">Valor</span><span class="sxs-lookup"><span data-stu-id="52204-172">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="52204-173">En</span><span class="sxs-lookup"><span data-stu-id="52204-173">To</span></span>|<span data-ttu-id="52204-174">replyMessage</span><span class="sxs-lookup"><span data-stu-id="52204-174">replyMessage</span></span>|  
    |<span data-ttu-id="52204-175">Valor</span><span class="sxs-lookup"><span data-stu-id="52204-175">Value</span></span>|<span data-ttu-id="52204-176">"Servicio: Enviar respuesta".</span><span class="sxs-lookup"><span data-stu-id="52204-176">"Service: Sending reply."</span></span>|  
  
11. <span data-ttu-id="52204-177">Arrastrar y colocar un <xref:System.Activities.Statements.WriteLine> actividad después de la <xref:System.Activities.Statements.Assign> actividad y establezca su <xref:System.Activities.Statements.WriteLine.Text%2A> propiedad en "servicio: Iniciar respuesta".</span><span class="sxs-lookup"><span data-stu-id="52204-177">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.Activities.Statements.Assign> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Begin reply."</span></span>  
  
     <span data-ttu-id="52204-178">El flujo de trabajo ahora debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="52204-178">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="52204-179">![Después de agregar Assign y WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingsbrwriteline.JPG "AfterAddingSBRWriteLine")</span><span class="sxs-lookup"><span data-stu-id="52204-179">![After adding Assign and WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingsbrwriteline.JPG "AfterAddingSBRWriteLine")</span></span>  
  
12. <span data-ttu-id="52204-180">Haga clic en el <xref:System.ServiceModel.Activities.Receive> actividad y seleccione **crear SendReply** y péguelos después del último <xref:System.Activities.Statements.WriteLine> actividad.</span><span class="sxs-lookup"><span data-stu-id="52204-180">Right click the <xref:System.ServiceModel.Activities.Receive> activity and select **Create SendReply** and paste it after the last <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="52204-181">Haga clic en el **definir...**  vincular en la `SendReplyToReceive` actividad y realice la siguiente configuración.</span><span class="sxs-lookup"><span data-stu-id="52204-181">Click the **Define...** link in the `SendReplyToReceive` activity and make the following settings.</span></span>  
  
     <span data-ttu-id="52204-182">![Configuración de mensajes de respuesta](../../../../docs/framework/wcf/feature-details/media/replymessagesettings.JPG "ReplyMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="52204-182">![Reply message settings](../../../../docs/framework/wcf/feature-details/media/replymessagesettings.JPG "ReplyMessageSettings")</span></span>  
  
13. <span data-ttu-id="52204-183">Arrastre y coloque un <xref:System.Activities.Statements.WriteLine> actividad después de la `SendReplyToReceive` actividad y el conjunto tiene <xref:System.Activities.Statements.WriteLine.Text%2A> propiedad en "servicio: Respuesta enviada".</span><span class="sxs-lookup"><span data-stu-id="52204-183">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `SendReplyToReceive` activity and set it’s <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Reply sent."</span></span>  
  
14. <span data-ttu-id="52204-184">Arrastre y coloque un <xref:System.Activities.Statements.WriteLine> actividad en la parte inferior del flujo de trabajo y establezca su <xref:System.Activities.Statements.WriteLine.Text%2A> propiedad en "servicio: Flujo de trabajo finaliza, presione ENTRAR para salir."</span><span class="sxs-lookup"><span data-stu-id="52204-184">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the bottom of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Workflow ends, press ENTER to exit."</span></span>  
  
     <span data-ttu-id="52204-185">El flujo de trabajo del servicio completado debería ser similar a:</span><span class="sxs-lookup"><span data-stu-id="52204-185">The completed service workflow should look like this:</span></span>  
  
     <span data-ttu-id="52204-186">![Completar flujo de trabajo de servicio](../../../../docs/framework/wcf/feature-details/media/servicecomplete.jpg "ServiceComplete")</span><span class="sxs-lookup"><span data-stu-id="52204-186">![Complete Service Workflow](../../../../docs/framework/wcf/feature-details/media/servicecomplete.jpg "ServiceComplete")</span></span>  
  
### <a name="implement-the-workflow-client"></a><span data-ttu-id="52204-187">Implementar el cliente de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="52204-187">Implement the workflow client</span></span>  
  
1.  <span data-ttu-id="52204-188">Agregue una nueva aplicación Flujo de trabajo WCF, denominada `WorkflowClient`, al proyecto `Common`.</span><span class="sxs-lookup"><span data-stu-id="52204-188">Add a new WCF Workflow application, called `WorkflowClient` to the `Common` project.</span></span> <span data-ttu-id="52204-189">Para ello, seleccione derecho la `Common` proyecto, seleccione **agregar**, **nuevo elemento...** , Seleccione **flujo de trabajo** en **plantillas instaladas** y seleccione **actividad**.</span><span class="sxs-lookup"><span data-stu-id="52204-189">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **Activity**.</span></span>  
  
     <span data-ttu-id="52204-190">![Agregar un proyecto de actividad](../../../../docs/framework/wcf/feature-details/media/addactivity.JPG "AddActivity")</span><span class="sxs-lookup"><span data-stu-id="52204-190">![Add an Activity project](../../../../docs/framework/wcf/feature-details/media/addactivity.JPG "AddActivity")</span></span>  
  
2.  <span data-ttu-id="52204-191">Arrastre y coloque una actividad <xref:System.Activities.Statements.Sequence> en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="52204-191">Drag and drop a <xref:System.Activities.Statements.Sequence> activity onto the design surface.</span></span>  
  
3.  <span data-ttu-id="52204-192">Dentro de la actividad <xref:System.Activities.Statements.Sequence>, arrastre y coloque una actividad de <xref:System.Activities.Statements.WriteLine> y establezca su propiedad <xref:System.Activities.Statements.WriteLine.Text%2A> en `"Client: Workflow starting"`.</span><span class="sxs-lookup"><span data-stu-id="52204-192">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop a <xref:System.Activities.Statements.WriteLine> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to `"Client: Workflow starting"`.</span></span> <span data-ttu-id="52204-193">El flujo de trabajo ahora debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="52204-193">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="52204-194">![Agregar una actividad WriteLine](../../../../docs/framework/wcf/feature-details/media/clientaddwriteline.JPG "ClientAddWriteLine")</span><span class="sxs-lookup"><span data-stu-id="52204-194">![Add a WriteLine activity](../../../../docs/framework/wcf/feature-details/media/clientaddwriteline.JPG "ClientAddWriteLine")</span></span>  
  
4.  <span data-ttu-id="52204-195">Arrastre y coloque una actividad de <xref:System.Activities.Statements.TransactionScope> después de la actividad de <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="52204-195">Drag and drop a <xref:System.Activities.Statements.TransactionScope> activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  <span data-ttu-id="52204-196">Seleccione la actividad de <xref:System.Activities.Statements.TransactionScope>, haga clic en el botón Variables y agregue las siguientes variables.</span><span class="sxs-lookup"><span data-stu-id="52204-196">Select the <xref:System.Activities.Statements.TransactionScope> activity, click the Variables button and add the following variables.</span></span>  
  
     <span data-ttu-id="52204-197">![Agregar variables a TransactionScope](../../../../docs/framework/wcf/feature-details/media/tsvariables.JPG "TSVariables")</span><span class="sxs-lookup"><span data-stu-id="52204-197">![Add variables to the TransactionScope](../../../../docs/framework/wcf/feature-details/media/tsvariables.JPG "TSVariables")</span></span>  
  
5.  <span data-ttu-id="52204-198">Arrastre y coloque una actividad de <xref:System.Activities.Statements.Sequence> en el cuerpo de la actividad de <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="52204-198">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the body of the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
6.  <span data-ttu-id="52204-199">Arrastre y coloque una actividad de `PrintTransactionInfo` dentro de <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="52204-199">Drag and drop a `PrintTransactionInfo` activity within the <xref:System.Activities.Statements.Sequence></span></span>  
  
7.  <span data-ttu-id="52204-200">Arrastrar y colocar un <xref:System.Activities.Statements.WriteLine> actividad después de la `PrintTransactionInfo` actividad y establezca su <xref:System.Activities.Statements.WriteLine.Text%2A> propiedad en "cliente: A partir de envío".</span><span class="sxs-lookup"><span data-stu-id="52204-200">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `PrintTransactionInfo` activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Beginning Send".</span></span> <span data-ttu-id="52204-201">El flujo de trabajo ahora debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="52204-201">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="52204-202">![Adición de actividades](../../../../docs/framework/wcf/feature-details/media/clientaddcbswriteline.JPG "ClientAddCBSWriteLine")</span><span class="sxs-lookup"><span data-stu-id="52204-202">![Adding activities](../../../../docs/framework/wcf/feature-details/media/clientaddcbswriteline.JPG "ClientAddCBSWriteLine")</span></span>  
  
8.  <span data-ttu-id="52204-203">Arrastre y coloque una actividad de <xref:System.ServiceModel.Activities.Send> después de la actividad de <xref:System.Activities.Statements.Assign> y establezca las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="52204-203">Drag and drop a <xref:System.ServiceModel.Activities.Send> activity after the <xref:System.Activities.Statements.Assign> activity and set the following properties:</span></span>  
  
    |<span data-ttu-id="52204-204">Property</span><span class="sxs-lookup"><span data-stu-id="52204-204">Property</span></span>|<span data-ttu-id="52204-205">Valor</span><span class="sxs-lookup"><span data-stu-id="52204-205">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="52204-206">EndpointConfigurationName</span><span class="sxs-lookup"><span data-stu-id="52204-206">EndpointConfigurationName</span></span>|<span data-ttu-id="52204-207">workflowServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="52204-207">workflowServiceEndpoint</span></span>|  
    |<span data-ttu-id="52204-208">OperationName</span><span class="sxs-lookup"><span data-stu-id="52204-208">OperationName</span></span>|<span data-ttu-id="52204-209">StartSample</span><span class="sxs-lookup"><span data-stu-id="52204-209">StartSample</span></span>|  
    |<span data-ttu-id="52204-210">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="52204-210">ServiceContractName</span></span>|<span data-ttu-id="52204-211">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="52204-211">ITransactionSample</span></span>|  
  
     <span data-ttu-id="52204-212">El flujo de trabajo ahora debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="52204-212">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="52204-213">![Establecer las propiedades de la actividad de envío](../../../../docs/framework/wcf/feature-details/media/clientsendsettings.JPG "ClientSendSettings")</span><span class="sxs-lookup"><span data-stu-id="52204-213">![Setting the Send activity properties](../../../../docs/framework/wcf/feature-details/media/clientsendsettings.JPG "ClientSendSettings")</span></span>  
  
9. <span data-ttu-id="52204-214">Haga clic en el **definir...**  vincular y realice la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="52204-214">Click the **Define...** link and make the following settings:</span></span>  
  
     <span data-ttu-id="52204-215">![Configuración de mensajes de actividad Send](../../../../docs/framework/wcf/feature-details/media/sendmessagesettings.JPG "SendMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="52204-215">![Send activity message settings](../../../../docs/framework/wcf/feature-details/media/sendmessagesettings.JPG "SendMessageSettings")</span></span>  
  
10. <span data-ttu-id="52204-216">Haga clic en el <xref:System.ServiceModel.Activities.Send> actividad y seleccione **crear ReceiveReply**.</span><span class="sxs-lookup"><span data-stu-id="52204-216">Right click the <xref:System.ServiceModel.Activities.Send> activity and select **Create ReceiveReply**.</span></span> <span data-ttu-id="52204-217">La actividad de <xref:System.ServiceModel.Activities.ReceiveReply> se colocará automáticamente después de la actividad de <xref:System.ServiceModel.Activities.Send>.</span><span class="sxs-lookup"><span data-stu-id="52204-217">The <xref:System.ServiceModel.Activities.ReceiveReply> activity will be automatically placed after the <xref:System.ServiceModel.Activities.Send> activity.</span></span>  
  
11. <span data-ttu-id="52204-218">Haga clic en el vínculo Definir... en la actividad ReceiveReplyForSend y realice la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="52204-218">Click the Define... link on the ReceiveReplyForSend activity and make the following settings:</span></span>  
  
     <span data-ttu-id="52204-219">![Establecer la configuración de mensajes ReceiveForSend](../../../../docs/framework/wcf/feature-details/media/clientreplymessagesettings.JPG "ClientReplyMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="52204-219">![Setting the ReceiveForSend message settings](../../../../docs/framework/wcf/feature-details/media/clientreplymessagesettings.JPG "ClientReplyMessageSettings")</span></span>  
  
12. <span data-ttu-id="52204-220">Arrastrar y colocar un <xref:System.Activities.Statements.WriteLine> actividad entre el <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Activities.ReceiveReply> actividades y establezca su <xref:System.Activities.Statements.WriteLine.Text%2A> propiedad en "cliente: Envío completado".</span><span class="sxs-lookup"><span data-stu-id="52204-220">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity between the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> activities and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Send complete."</span></span>  
  
13. <span data-ttu-id="52204-221">Arrastre y coloque un <xref:System.Activities.Statements.WriteLine> actividad después de la <xref:System.ServiceModel.Activities.ReceiveReply> actividad y establezca su <xref:System.Activities.Statements.WriteLine.Text%2A> propiedad a "del lado cliente: Respuesta recibida = "+ replyMessage</span><span class="sxs-lookup"><span data-stu-id="52204-221">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.ServiceModel.Activities.ReceiveReply> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client side: Reply received = " + replyMessage</span></span>  
  
14. <span data-ttu-id="52204-222">Arrastre y coloque una actividad de `PrintTransactionInfo` después de la actividad de <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="52204-222">Drag and drop a `PrintTransactionInfo` activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
15. <span data-ttu-id="52204-223">Arrastre y coloque una actividad de <xref:System.Activities.Statements.WriteLine> al final del flujo de trabajo y establezca su propiedad <xref:System.Activities.Statements.WriteLine.Text%2A> en "El flujo de cliente finaliza".</span><span class="sxs-lookup"><span data-stu-id="52204-223">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the end of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client workflow ends."</span></span> <span data-ttu-id="52204-224">El flujo de trabajo del cliente completado debería parecerse al del siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="52204-224">The completed client workflow should look like the following diagram.</span></span>  
  
     <span data-ttu-id="52204-225">![El workfliow cliente completado](../../../../docs/framework/wcf/feature-details/media/clientcompleteworkflow.jpg "ClientCompleteWorkflow")</span><span class="sxs-lookup"><span data-stu-id="52204-225">![The completed client workfliow](../../../../docs/framework/wcf/feature-details/media/clientcompleteworkflow.jpg "ClientCompleteWorkflow")</span></span>  
  
16. <span data-ttu-id="52204-226">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="52204-226">Build the solution.</span></span>  
  
### <a name="create-the-service-application"></a><span data-ttu-id="52204-227">Crear la aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="52204-227">Create the Service application</span></span>  
  
1.  <span data-ttu-id="52204-228">Agregue un nuevo proyecto Aplicación de consola denominado `Service` a la solución.</span><span class="sxs-lookup"><span data-stu-id="52204-228">Add a new Console Application project called `Service` to the solution.</span></span> <span data-ttu-id="52204-229">Agregue referencias a los siguientes ensamblados:</span><span class="sxs-lookup"><span data-stu-id="52204-229">Add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="52204-230">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="52204-230">System.Activities.dll</span></span>  
  
    2.  <span data-ttu-id="52204-231">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="52204-231">System.ServiceModel.dll</span></span>  
  
    3.  <span data-ttu-id="52204-232">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="52204-232">System.ServiceModel.Activities.dll</span></span>  
  
2.  <span data-ttu-id="52204-233">Abra el archivo Program.cs generado y el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="52204-233">Open the generated Program.cs file and the following code:</span></span>  
  
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
  
3.  <span data-ttu-id="52204-234">Agregue el archivo app.config siguiente al proyecto.</span><span class="sxs-lookup"><span data-stu-id="52204-234">Add the following app.config file to the project.</span></span>  
  
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
  
### <a name="create-the-client-application"></a><span data-ttu-id="52204-235">Crear la aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="52204-235">Create the client application</span></span>  
  
1.  <span data-ttu-id="52204-236">Agregue un nuevo proyecto Aplicación de consola denominado `Client` a la solución.</span><span class="sxs-lookup"><span data-stu-id="52204-236">Add a new Console Application project called `Client` to the solution.</span></span> <span data-ttu-id="52204-237">Agregue una referencia a System.Activities.dll.</span><span class="sxs-lookup"><span data-stu-id="52204-237">Add a reference to System.Activities.dll.</span></span>  
  
2.  <span data-ttu-id="52204-238">Abra el archivo Program.cs y agregue el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="52204-238">Open the program.cs file and add the following code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="52204-239">Vea también</span><span class="sxs-lookup"><span data-stu-id="52204-239">See also</span></span>

- [<span data-ttu-id="52204-240">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="52204-240">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="52204-241">Información general sobre las transacciones de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="52204-241">Windows Communication Foundation Transactions Overview</span></span>](../../../../docs/framework/wcf/feature-details/transactions-overview.md)
