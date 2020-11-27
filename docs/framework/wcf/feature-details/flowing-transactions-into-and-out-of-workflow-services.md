---
title: Flujo de las transacciones en los servicios de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
ms.openlocfilehash: 8764f3c88fc978bc71ff993252b04fe58da4bbc9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290353"
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a><span data-ttu-id="06e31-102">Flujo de las transacciones en los servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="06e31-102">Flowing Transactions into and out of Workflow Services</span></span>

<span data-ttu-id="06e31-103">Los servicios y clientes de flujo de trabajo pueden participar en las transacciones.</span><span class="sxs-lookup"><span data-stu-id="06e31-103">Workflow services and clients can participate in transactions.</span></span>  <span data-ttu-id="06e31-104">Para que una operación de servicio se convierta en parte de una transacción de ambiente, coloque una actividad de <xref:System.ServiceModel.Activities.Receive> dentro de una actividad de <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="06e31-104">For a service operation to become part of an ambient transaction, place a <xref:System.ServiceModel.Activities.Receive> activity within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="06e31-105">En cualquier llamada realizada por un objeto <xref:System.ServiceModel.Activities.Send> o una actividad de <xref:System.ServiceModel.Activities.SendReply> dentro de <xref:System.ServiceModel.Activities.TransactedReceiveScope> también se realizará dentro de la transacción de ambiente.</span><span class="sxs-lookup"><span data-stu-id="06e31-105">Any calls made by a <xref:System.ServiceModel.Activities.Send> or a <xref:System.ServiceModel.Activities.SendReply> activity within the <xref:System.ServiceModel.Activities.TransactedReceiveScope> will also be made within the ambient transaction.</span></span> <span data-ttu-id="06e31-106">Una aplicación cliente del flujo de trabajo puede crear una transacción de ambiente utilizando la actividad de <xref:System.Activities.Statements.TransactionScope> y operaciones de servicio de llamada que usen la transacción de ambiente.</span><span class="sxs-lookup"><span data-stu-id="06e31-106">A workflow client application can create an ambient transaction by using the <xref:System.Activities.Statements.TransactionScope> activity and call service operations using the ambient transaction.</span></span> <span data-ttu-id="06e31-107">Este tema sirve de guía para crear un servicio de flujo de trabajo y un cliente de flujo de trabajo que participan en transacciones.</span><span class="sxs-lookup"><span data-stu-id="06e31-107">This topic walks you through creating a workflow service and workflow client that participate in transactions.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="06e31-108">Si una instancia de servicio de flujo de trabajo se carga dentro de una transacción y el flujo de trabajo contiene una <xref:System.Activities.Statements.Persist> actividad, la instancia de flujo de trabajo se bloqueará hasta que se agote el tiempo de espera de la transacción.</span><span class="sxs-lookup"><span data-stu-id="06e31-108">If a workflow service instance is loaded within a transaction and the workflow contains a <xref:System.Activities.Statements.Persist> activity, the workflow instance will block until the transaction times out.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="06e31-109">Siempre que use un objeto <xref:System.ServiceModel.Activities.TransactedReceiveScope> se recomienda que coloque todas las recepciones en el flujo de trabajo dentro de actividades <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="06e31-109">Whenever you use a <xref:System.ServiceModel.Activities.TransactedReceiveScope> it is recommended to place all Receives in the workflow within <xref:System.ServiceModel.Activities.TransactedReceiveScope> activities.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="06e31-110">Cuando se usa el objeto <xref:System.ServiceModel.Activities.TransactedReceiveScope> y los mensajes llegan en el orden incorrecto, el flujo de trabajo se anulará al intentar entregar el primer mensaje que lo indique.</span><span class="sxs-lookup"><span data-stu-id="06e31-110">When using <xref:System.ServiceModel.Activities.TransactedReceiveScope> and messages arrive in the incorrect order, the workflow will be aborted when trying to deliver the first out of order message.</span></span> <span data-ttu-id="06e31-111">Debe asegurarse de que el flujo de trabajo siempre está en un punto de detención coherente cuando el flujo de trabajo está inactivo.</span><span class="sxs-lookup"><span data-stu-id="06e31-111">You must make sure your workflow is always at a consistent stopping point when the workflow idles.</span></span> <span data-ttu-id="06e31-112">De este modo, podrá reiniciar el flujo de trabajo a partir de un punto de persistencia anterior si el flujo de trabajo se anula.</span><span class="sxs-lookup"><span data-stu-id="06e31-112">This will allow you to restart the workflow from a previous persistence point should the workflow be aborted.</span></span>  
  
### <a name="create-a-shared-library"></a><span data-ttu-id="06e31-113">Crear una biblioteca compartida</span><span class="sxs-lookup"><span data-stu-id="06e31-113">Create a shared library</span></span>  
  
1. <span data-ttu-id="06e31-114">Cree una nueva solución de Visual Studio vacía.</span><span class="sxs-lookup"><span data-stu-id="06e31-114">Create a new empty Visual Studio Solution.</span></span>  
  
2. <span data-ttu-id="06e31-115">Agregue un nuevo proyecto de biblioteca de clases denominado `Common`.</span><span class="sxs-lookup"><span data-stu-id="06e31-115">Add a new class library project called `Common`.</span></span> <span data-ttu-id="06e31-116">Agregue referencias a los siguientes ensamblados:</span><span class="sxs-lookup"><span data-stu-id="06e31-116">Add references to the following assemblies:</span></span>  
  
    - <span data-ttu-id="06e31-117">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="06e31-117">System.Activities.dll</span></span>  
  
    - <span data-ttu-id="06e31-118">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="06e31-118">System.ServiceModel.dll</span></span>  
  
    - <span data-ttu-id="06e31-119">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="06e31-119">System.ServiceModel.Activities.dll</span></span>  
  
    - <span data-ttu-id="06e31-120">System.Transactions.dll</span><span class="sxs-lookup"><span data-stu-id="06e31-120">System.Transactions.dll</span></span>  
  
3. <span data-ttu-id="06e31-121">Agregue una nueva clase denominada `PrintTransactionInfo` al proyecto `Common`.</span><span class="sxs-lookup"><span data-stu-id="06e31-121">Add a new class called `PrintTransactionInfo` to the `Common` project.</span></span> <span data-ttu-id="06e31-122">Esta clase se deriva de <xref:System.Activities.NativeActivity> y sobrecarga el método <xref:System.Activities.NativeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="06e31-122">This class is derived from <xref:System.Activities.NativeActivity> and overloads the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>  
  
    ```csharp
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
  
     <span data-ttu-id="06e31-123">Esta es una actividad nativa que muestra información acerca de la transacción de ambiente y se utiliza en ambos flujos de trabajo, de cliente y de servicio, que se usan en este tema.</span><span class="sxs-lookup"><span data-stu-id="06e31-123">This is a native activity that displays information about the ambient transaction and is used in both the service and client workflows used in this topic.</span></span> <span data-ttu-id="06e31-124">Compile la solución para que esta actividad esté disponible en la sección **común** del **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="06e31-124">Build the solution to make this activity available in the **Common** section of the **Toolbox**.</span></span>  
  
### <a name="implement-the-workflow-service"></a><span data-ttu-id="06e31-125">Implementar el servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="06e31-125">Implement the workflow service</span></span>  
  
1. <span data-ttu-id="06e31-126">Agregue un nuevo servicio de flujo de trabajo WCF, llamado `WorkflowService` al `Common` proyecto.</span><span class="sxs-lookup"><span data-stu-id="06e31-126">Add a new WCF Workflow Service, called `WorkflowService` to the `Common` project.</span></span> <span data-ttu-id="06e31-127">Para ello, haga clic con el botón derecho en el `Common` proyecto, seleccione **Agregar**, **nuevo elemento...**, seleccione **flujo de trabajo** en **plantillas instaladas** y seleccione **servicio de flujo de trabajo WCF**.</span><span class="sxs-lookup"><span data-stu-id="06e31-127">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **WCF Workflow Service**.</span></span>  
  
     ![Agregar un servicio de flujo de trabajo](./media/flowing-transactions-into-and-out-of-workflow-services/add-workflow-service.jpg)  
  
2. <span data-ttu-id="06e31-129">Elimine las actividades `ReceiveRequest` y `SendResponse` predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="06e31-129">Delete the default `ReceiveRequest` and `SendResponse` activities.</span></span>  
  
3. <span data-ttu-id="06e31-130">Arrastre y coloque una actividad de <xref:System.Activities.Statements.WriteLine> en la actividad de `Sequential Service`.</span><span class="sxs-lookup"><span data-stu-id="06e31-130">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity into the `Sequential Service` activity.</span></span> <span data-ttu-id="06e31-131">Establezca la propiedad de texto en `"Workflow Service starting ..."` como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="06e31-131">Set the text property to `"Workflow Service starting ..."` as shown in the following example.</span></span>  
  
     <span data-ttu-id="06e31-132">! [Agregar una actividad WriteLine a la actividad de servicio secuencial (./Media/Flowing-Transactions-into-and-out-of-Workflow-Services/add-writeline-sequential-service.jpg)</span><span class="sxs-lookup"><span data-stu-id="06e31-132">![Adding a WriteLine activity to the Sequential Service activity(./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-sequential-service.jpg)</span></span>  
  
4. <span data-ttu-id="06e31-133">Arrastre y coloque una actividad <xref:System.ServiceModel.Activities.TransactedReceiveScope> después de la actividad de <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="06e31-133">Drag and drop a <xref:System.ServiceModel.Activities.TransactedReceiveScope> after the <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="06e31-134">La <xref:System.ServiceModel.Activities.TransactedReceiveScope> actividad se puede encontrar en la sección **Mensajería** del **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="06e31-134">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity can be found in the **Messaging** section of the **Toolbox**.</span></span> <span data-ttu-id="06e31-135">La <xref:System.ServiceModel.Activities.TransactedReceiveScope> actividad se compone de dos secciones **solicitud** y **cuerpo**.</span><span class="sxs-lookup"><span data-stu-id="06e31-135">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity is composed of two sections **Request** and **Body**.</span></span> <span data-ttu-id="06e31-136">La sección de **solicitud** contiene la <xref:System.ServiceModel.Activities.Receive> actividad.</span><span class="sxs-lookup"><span data-stu-id="06e31-136">The **Request** section contains the <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="06e31-137">La sección de **cuerpo** contiene las actividades que se ejecutarán dentro de una transacción una vez recibido un mensaje.</span><span class="sxs-lookup"><span data-stu-id="06e31-137">The **Body** section contains the activities to execute within a transaction after a message has been received.</span></span>  
  
     ![Agregar una actividad TransactedReceiveScope](./media/flowing-transactions-into-and-out-of-workflow-services/transactedreceivescope-activity.jpg)  
  
5. <span data-ttu-id="06e31-139">Seleccione la <xref:System.ServiceModel.Activities.TransactedReceiveScope> actividad y haga clic en el botón **variables** .</span><span class="sxs-lookup"><span data-stu-id="06e31-139">Select the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity and click the **Variables** button.</span></span> <span data-ttu-id="06e31-140">Agregue las variables siguientes.</span><span class="sxs-lookup"><span data-stu-id="06e31-140">Add the following variables.</span></span>  
  
     ![Agregar variables a TransactedReceiveScope](./media/flowing-transactions-into-and-out-of-workflow-services/add-transactedreceivescope-variables.jpg)  
  
    > [!NOTE]
    > <span data-ttu-id="06e31-142">Puede eliminar la variable de datos que está allí de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="06e31-142">You can delete the data variable that is there by default.</span></span> <span data-ttu-id="06e31-143">También puede utilizar la variable de controlador existente.</span><span class="sxs-lookup"><span data-stu-id="06e31-143">You can also use the existing handle variable.</span></span>  
  
6. <span data-ttu-id="06e31-144">Arrastre y coloque una <xref:System.ServiceModel.Activities.Receive> actividad dentro de la sección **solicitud** de la <xref:System.ServiceModel.Activities.TransactedReceiveScope> actividad.</span><span class="sxs-lookup"><span data-stu-id="06e31-144">Drag and drop a <xref:System.ServiceModel.Activities.Receive> activity within the **Request** section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="06e31-145">Establezca las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="06e31-145">Set the following properties:</span></span>  
  
    |<span data-ttu-id="06e31-146">Propiedad</span><span class="sxs-lookup"><span data-stu-id="06e31-146">Property</span></span>|<span data-ttu-id="06e31-147">Valor</span><span class="sxs-lookup"><span data-stu-id="06e31-147">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="06e31-148">CanCreateInstance</span><span class="sxs-lookup"><span data-stu-id="06e31-148">CanCreateInstance</span></span>|<span data-ttu-id="06e31-149">True (activar la casilla)</span><span class="sxs-lookup"><span data-stu-id="06e31-149">True (check the checkbox)</span></span>|  
    |<span data-ttu-id="06e31-150">OperationName</span><span class="sxs-lookup"><span data-stu-id="06e31-150">OperationName</span></span>|<span data-ttu-id="06e31-151">StartSample</span><span class="sxs-lookup"><span data-stu-id="06e31-151">StartSample</span></span>|  
    |<span data-ttu-id="06e31-152">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="06e31-152">ServiceContractName</span></span>|<span data-ttu-id="06e31-153">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="06e31-153">ITransactionSample</span></span>|  
  
     <span data-ttu-id="06e31-154">El flujo de trabajo debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="06e31-154">The workflow should look like this:</span></span>  
  
     ![Agregar una actividad Receive](./media/flowing-transactions-into-and-out-of-workflow-services/add-receive-activity.jpg)  
  
7. <span data-ttu-id="06e31-156">Haga clic en el vínculo **definir...** en la <xref:System.ServiceModel.Activities.Receive> actividad y realice la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="06e31-156">Click the **Define...** link in the <xref:System.ServiceModel.Activities.Receive> activity and make the following settings:</span></span>  
  
     ![Establecer la configuración del mensaje para la actividad Receive](./media/flowing-transactions-into-and-out-of-workflow-services/receive-message-settings.jpg)  
  
8. <span data-ttu-id="06e31-158">Arrastre y coloque una actividad de <xref:System.Activities.Statements.Sequence> en la sección Cuerpo de <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="06e31-158">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the Body section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="06e31-159">Dentro de la actividad de <xref:System.Activities.Statements.Sequence>, arrastre las dos actividades de <xref:System.Activities.Statements.WriteLine> y establezca las propiedades <xref:System.Activities.Statements.WriteLine.Text%2A> como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="06e31-159">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop two <xref:System.Activities.Statements.WriteLine> activities and set the <xref:System.Activities.Statements.WriteLine.Text%2A> properties as shown in the following table.</span></span>  
  
    |<span data-ttu-id="06e31-160">Actividad</span><span class="sxs-lookup"><span data-stu-id="06e31-160">Activity</span></span>|<span data-ttu-id="06e31-161">Valor</span><span class="sxs-lookup"><span data-stu-id="06e31-161">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="06e31-162">Primera propiedad WriteLine</span><span class="sxs-lookup"><span data-stu-id="06e31-162">1st WriteLine</span></span>|<span data-ttu-id="06e31-163">"Servicio: recepción completada"</span><span class="sxs-lookup"><span data-stu-id="06e31-163">"Service: Receive Completed"</span></span>|  
    |<span data-ttu-id="06e31-164">Segunda propiedad WriteLine</span><span class="sxs-lookup"><span data-stu-id="06e31-164">2nd WriteLine</span></span>|<span data-ttu-id="06e31-165">"Servicio: recibido = " + requestMessage</span><span class="sxs-lookup"><span data-stu-id="06e31-165">"Service: Received = " + requestMessage</span></span>|  
  
     <span data-ttu-id="06e31-166">El flujo de trabajo ahora debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="06e31-166">The workflow should now look like this:</span></span>  
  
     ![Secuencia después de agregar actividades WriteLine](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-writelines.jpg)  
  
9. <span data-ttu-id="06e31-168">Arrastre y coloque la `PrintTransactionInfo` actividad después de la segunda <xref:System.Activities.Statements.WriteLine> actividad en el **cuerpo** de la <xref:System.ServiceModel.Activities.TransactedReceiveScope> actividad.</span><span class="sxs-lookup"><span data-stu-id="06e31-168">Drag and drop the `PrintTransactionInfo` activity after the second <xref:System.Activities.Statements.WriteLine> activity in the **Body** in the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span>  
  
     ![Secuencia después de agregar PrintTransactionInfo](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-printtransactioninfo.jpg )  
  
10. <span data-ttu-id="06e31-170">Arrastre y coloque una actividad de <xref:System.Activities.Statements.Assign> después de la actividad de `PrintTransactionInfo` y establezca sus propiedades según la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="06e31-170">Drag and drop an <xref:System.Activities.Statements.Assign> activity after the `PrintTransactionInfo` activity and set its properties according to the following table.</span></span>  
  
    |<span data-ttu-id="06e31-171">Propiedad</span><span class="sxs-lookup"><span data-stu-id="06e31-171">Property</span></span>|<span data-ttu-id="06e31-172">Valor</span><span class="sxs-lookup"><span data-stu-id="06e31-172">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="06e31-173">En</span><span class="sxs-lookup"><span data-stu-id="06e31-173">To</span></span>|<span data-ttu-id="06e31-174">replyMessage</span><span class="sxs-lookup"><span data-stu-id="06e31-174">replyMessage</span></span>|  
    |<span data-ttu-id="06e31-175">Valor</span><span class="sxs-lookup"><span data-stu-id="06e31-175">Value</span></span>|<span data-ttu-id="06e31-176">"Servicio: enviando respuesta."</span><span class="sxs-lookup"><span data-stu-id="06e31-176">"Service: Sending reply."</span></span>|  
  
11. <span data-ttu-id="06e31-177">Arrastre y coloque una actividad de <xref:System.Activities.Statements.WriteLine> después de la actividad de <xref:System.Activities.Statements.Assign> y establezca su propiedad <xref:System.Activities.Statements.WriteLine.Text%2A> en "Servicio: iniciar respuesta".</span><span class="sxs-lookup"><span data-stu-id="06e31-177">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.Activities.Statements.Assign> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Begin reply."</span></span>  
  
     <span data-ttu-id="06e31-178">El flujo de trabajo ahora debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="06e31-178">The workflow should now look like this:</span></span>  
  
     ![Después de agregar Assign y WriteLine](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-sbr-writeline.jpg)  
  
12. <span data-ttu-id="06e31-180">Haga clic con el botón derecho en la <xref:System.ServiceModel.Activities.Receive> actividad, seleccione **crear SendReply** y péguelo después de la última <xref:System.Activities.Statements.WriteLine> actividad.</span><span class="sxs-lookup"><span data-stu-id="06e31-180">Right click the <xref:System.ServiceModel.Activities.Receive> activity and select **Create SendReply** and paste it after the last <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="06e31-181">Haga clic en el vínculo **definir...** en la `SendReplyToReceive` actividad y realice la siguiente configuración.</span><span class="sxs-lookup"><span data-stu-id="06e31-181">Click the **Define...** link in the `SendReplyToReceive` activity and make the following settings.</span></span>  
  
     ![Configuración de mensajes de respuesta](./media/flowing-transactions-into-and-out-of-workflow-services/reply-message-settings.jpg)  
  
13. <span data-ttu-id="06e31-183">Arrastre y coloque una <xref:System.Activities.Statements.WriteLine> actividad después de la `SendReplyToReceive` actividad y establezca su <xref:System.Activities.Statements.WriteLine.Text%2A> propiedad en "servicio: respuesta enviada".</span><span class="sxs-lookup"><span data-stu-id="06e31-183">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `SendReplyToReceive` activity and set it’s <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Reply sent."</span></span>  
  
14. <span data-ttu-id="06e31-184">Arrastre y coloque una actividad de <xref:System.Activities.Statements.WriteLine> en la parte inferior del flujo de trabajo y establezca su propiedad <xref:System.Activities.Statements.WriteLine.Text%2A> en "Servicio: el flujo de trabajo finaliza, presione Entrar para salir".</span><span class="sxs-lookup"><span data-stu-id="06e31-184">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the bottom of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Workflow ends, press ENTER to exit."</span></span>  
  
     <span data-ttu-id="06e31-185">El flujo de trabajo del servicio completado debería ser similar a:</span><span class="sxs-lookup"><span data-stu-id="06e31-185">The completed service workflow should look like this:</span></span>  
  
     ![Flujo de trabajo de servicio completo](./media/flowing-transactions-into-and-out-of-workflow-services/service-complete-workflow.jpg)  
  
### <a name="implement-the-workflow-client"></a><span data-ttu-id="06e31-187">Implementar el cliente de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="06e31-187">Implement the workflow client</span></span>  
  
1. <span data-ttu-id="06e31-188">Agregue una nueva aplicación Flujo de trabajo WCF, denominada `WorkflowClient`, al proyecto `Common`.</span><span class="sxs-lookup"><span data-stu-id="06e31-188">Add a new WCF Workflow application, called `WorkflowClient` to the `Common` project.</span></span> <span data-ttu-id="06e31-189">Para ello, haga clic con el botón derecho en el `Common` proyecto, seleccione **Agregar**, **nuevo elemento.**.., seleccione **flujo de trabajo** en **plantillas instaladas** y seleccione **actividad**.</span><span class="sxs-lookup"><span data-stu-id="06e31-189">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **Activity**.</span></span>  
  
     ![Agregar un proyecto de actividad](./media/flowing-transactions-into-and-out-of-workflow-services/add-activity-project.jpg)  
  
2. <span data-ttu-id="06e31-191">Arrastre y coloque una actividad <xref:System.Activities.Statements.Sequence> en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="06e31-191">Drag and drop a <xref:System.Activities.Statements.Sequence> activity onto the design surface.</span></span>  
  
3. <span data-ttu-id="06e31-192">Dentro de la actividad <xref:System.Activities.Statements.Sequence>, arrastre y coloque una actividad de <xref:System.Activities.Statements.WriteLine> y establezca su propiedad <xref:System.Activities.Statements.WriteLine.Text%2A> en `"Client: Workflow starting"`.</span><span class="sxs-lookup"><span data-stu-id="06e31-192">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop a <xref:System.Activities.Statements.WriteLine> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to `"Client: Workflow starting"`.</span></span> <span data-ttu-id="06e31-193">El flujo de trabajo ahora debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="06e31-193">The workflow should now look like this:</span></span>  
  
     ![Agregar una actividad WriteLine](./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-activity.jpg)  
  
4. <span data-ttu-id="06e31-195">Arrastre y coloque una actividad de <xref:System.Activities.Statements.TransactionScope> después de la actividad de <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="06e31-195">Drag and drop a <xref:System.Activities.Statements.TransactionScope> activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  <span data-ttu-id="06e31-196">Seleccione la actividad de <xref:System.Activities.Statements.TransactionScope>, haga clic en el botón Variables y agregue las siguientes variables.</span><span class="sxs-lookup"><span data-stu-id="06e31-196">Select the <xref:System.Activities.Statements.TransactionScope> activity, click the Variables button and add the following variables.</span></span>  
  
     ![Agregar variables a TransactionScope](./media/flowing-transactions-into-and-out-of-workflow-services/transactionscope-variables.jpg)  
  
5. <span data-ttu-id="06e31-198">Arrastre y coloque una actividad de <xref:System.Activities.Statements.Sequence> en el cuerpo de la actividad de <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="06e31-198">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the body of the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
6. <span data-ttu-id="06e31-199">Arrastre y coloque una actividad de `PrintTransactionInfo` dentro de <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="06e31-199">Drag and drop a `PrintTransactionInfo` activity within the <xref:System.Activities.Statements.Sequence></span></span>  
  
7. <span data-ttu-id="06e31-200">Arrastre y coloque una <xref:System.Activities.Statements.WriteLine> actividad después de la `PrintTransactionInfo` actividad y establezca su <xref:System.Activities.Statements.WriteLine.Text%2A> propiedad en "cliente: iniciando envío".</span><span class="sxs-lookup"><span data-stu-id="06e31-200">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `PrintTransactionInfo` activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Beginning Send".</span></span> <span data-ttu-id="06e31-201">El flujo de trabajo ahora debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="06e31-201">The workflow should now look like this:</span></span>  
  
     ![Agregando cliente: iniciando actividades de envío](./media/flowing-transactions-into-and-out-of-workflow-services/client-add-cbs-writeline.jpg)  
  
8. <span data-ttu-id="06e31-203">Arrastre y coloque una actividad de <xref:System.ServiceModel.Activities.Send> después de la actividad de <xref:System.Activities.Statements.Assign> y establezca las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="06e31-203">Drag and drop a <xref:System.ServiceModel.Activities.Send> activity after the <xref:System.Activities.Statements.Assign> activity and set the following properties:</span></span>  
  
    |<span data-ttu-id="06e31-204">Propiedad</span><span class="sxs-lookup"><span data-stu-id="06e31-204">Property</span></span>|<span data-ttu-id="06e31-205">Valor</span><span class="sxs-lookup"><span data-stu-id="06e31-205">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="06e31-206">EndpointConfigurationName</span><span class="sxs-lookup"><span data-stu-id="06e31-206">EndpointConfigurationName</span></span>|<span data-ttu-id="06e31-207">workflowServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="06e31-207">workflowServiceEndpoint</span></span>|  
    |<span data-ttu-id="06e31-208">OperationName</span><span class="sxs-lookup"><span data-stu-id="06e31-208">OperationName</span></span>|<span data-ttu-id="06e31-209">StartSample</span><span class="sxs-lookup"><span data-stu-id="06e31-209">StartSample</span></span>|  
    |<span data-ttu-id="06e31-210">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="06e31-210">ServiceContractName</span></span>|<span data-ttu-id="06e31-211">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="06e31-211">ITransactionSample</span></span>|  
  
     <span data-ttu-id="06e31-212">El flujo de trabajo ahora debería ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="06e31-212">The workflow should now look like this:</span></span>  
  
     ![Establecer las propiedades de la actividad Send](./media/flowing-transactions-into-and-out-of-workflow-services/client-send-activity-settings.jpg)  
  
9. <span data-ttu-id="06e31-214">Haga clic en el vínculo **definir...** y realice la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="06e31-214">Click the **Define...** link and make the following settings:</span></span>  
  
     ![Configuración de mensajes de la actividad Send](./media/flowing-transactions-into-and-out-of-workflow-services/send-message-settings.jpg)  
  
10. <span data-ttu-id="06e31-216">Haga clic con el botón derecho en la <xref:System.ServiceModel.Activities.Send> actividad y seleccione **crear ReceiveReply**.</span><span class="sxs-lookup"><span data-stu-id="06e31-216">Right click the <xref:System.ServiceModel.Activities.Send> activity and select **Create ReceiveReply**.</span></span> <span data-ttu-id="06e31-217">La actividad de <xref:System.ServiceModel.Activities.ReceiveReply> se colocará automáticamente después de la actividad de <xref:System.ServiceModel.Activities.Send>.</span><span class="sxs-lookup"><span data-stu-id="06e31-217">The <xref:System.ServiceModel.Activities.ReceiveReply> activity will be automatically placed after the <xref:System.ServiceModel.Activities.Send> activity.</span></span>  
  
11. <span data-ttu-id="06e31-218">Haga clic en el vínculo Definir... en la actividad ReceiveReplyForSend y realice la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="06e31-218">Click the Define... link on the ReceiveReplyForSend activity and make the following settings:</span></span>  
  
     ![Establecer la configuración de mensajes ReceiveForSend](./media/flowing-transactions-into-and-out-of-workflow-services/client-reply-message-settings.jpg)  
  
12. <span data-ttu-id="06e31-220">Arrastre y coloque una actividad de <xref:System.Activities.Statements.WriteLine> entre las actividades de <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Activities.ReceiveReply>, y establezca su propiedad <xref:System.Activities.Statements.WriteLine.Text%2A> en "Cliente: envío completado".</span><span class="sxs-lookup"><span data-stu-id="06e31-220">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity between the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> activities and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Send complete."</span></span>  
  
13. <span data-ttu-id="06e31-221">Arrastre y coloque una actividad de <xref:System.Activities.Statements.WriteLine> después de la actividad de <xref:System.ServiceModel.Activities.ReceiveReply> y establezca su propiedad <xref:System.Activities.Statements.WriteLine.Text%2A> en "Cliente: respuesta recibida = " + replyMessage</span><span class="sxs-lookup"><span data-stu-id="06e31-221">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.ServiceModel.Activities.ReceiveReply> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client side: Reply received = " + replyMessage</span></span>  
  
14. <span data-ttu-id="06e31-222">Arrastre y coloque una actividad de `PrintTransactionInfo` después de la actividad de <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="06e31-222">Drag and drop a `PrintTransactionInfo` activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
15. <span data-ttu-id="06e31-223">Arrastre y coloque una actividad de <xref:System.Activities.Statements.WriteLine> al final del flujo de trabajo y establezca su propiedad <xref:System.Activities.Statements.WriteLine.Text%2A> en "El flujo de cliente finaliza".</span><span class="sxs-lookup"><span data-stu-id="06e31-223">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the end of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client workflow ends."</span></span> <span data-ttu-id="06e31-224">El flujo de trabajo del cliente completado debería parecerse al del siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="06e31-224">The completed client workflow should look like the following diagram.</span></span>  
  
     ![El flujo de trabajo del cliente completado](./media/flowing-transactions-into-and-out-of-workflow-services/client-complete-workflow.jpg)  
  
16. <span data-ttu-id="06e31-226">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="06e31-226">Build the solution.</span></span>  
  
### <a name="create-the-service-application"></a><span data-ttu-id="06e31-227">Crear la aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="06e31-227">Create the Service application</span></span>  
  
1. <span data-ttu-id="06e31-228">Agregue un nuevo proyecto Aplicación de consola denominado `Service` a la solución.</span><span class="sxs-lookup"><span data-stu-id="06e31-228">Add a new Console Application project called `Service` to the solution.</span></span> <span data-ttu-id="06e31-229">Agregue referencias a los siguientes ensamblados:</span><span class="sxs-lookup"><span data-stu-id="06e31-229">Add references to the following assemblies:</span></span>  
  
    1. <span data-ttu-id="06e31-230">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="06e31-230">System.Activities.dll</span></span>  
  
    2. <span data-ttu-id="06e31-231">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="06e31-231">System.ServiceModel.dll</span></span>  
  
    3. <span data-ttu-id="06e31-232">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="06e31-232">System.ServiceModel.Activities.dll</span></span>  
  
2. <span data-ttu-id="06e31-233">Abra el archivo Program.cs generado y el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="06e31-233">Open the generated Program.cs file and the following code:</span></span>  
  
    ```csharp
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
  
3. <span data-ttu-id="06e31-234">Agregue el archivo app.config siguiente al proyecto.</span><span class="sxs-lookup"><span data-stu-id="06e31-234">Add the following app.config file to the project.</span></span>  
  
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
  
### <a name="create-the-client-application"></a><span data-ttu-id="06e31-235">Creación de la aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="06e31-235">Create the client application</span></span>  
  
1. <span data-ttu-id="06e31-236">Agregue un nuevo proyecto Aplicación de consola denominado `Client` a la solución.</span><span class="sxs-lookup"><span data-stu-id="06e31-236">Add a new Console Application project called `Client` to the solution.</span></span> <span data-ttu-id="06e31-237">Agregue una referencia a System.Activities.dll.</span><span class="sxs-lookup"><span data-stu-id="06e31-237">Add a reference to System.Activities.dll.</span></span>  
  
2. <span data-ttu-id="06e31-238">Abra el archivo Program.cs y agregue el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="06e31-238">Open the program.cs file and add the following code.</span></span>  
  
    ```csharp
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
  
## <a name="see-also"></a><span data-ttu-id="06e31-239">Vea también</span><span class="sxs-lookup"><span data-stu-id="06e31-239">See also</span></span>

- [<span data-ttu-id="06e31-240">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="06e31-240">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="06e31-241">Información general sobre las transacciones de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="06e31-241">Windows Communication Foundation Transactions Overview</span></span>](transactions-overview.md)
