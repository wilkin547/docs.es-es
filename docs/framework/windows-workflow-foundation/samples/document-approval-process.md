---
title: Proceso de aprobación de un documento
ms.date: 03/30/2017
ms.assetid: 9b240937-76a7-45cd-8823-7f82c34d03bd
ms.openlocfilehash: 20167cd1c06c2ae57dfe48fd07ab3a0e2adf9927
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70038223"
---
# <a name="document-approval-process"></a><span data-ttu-id="0bee4-102">Proceso de aprobación de un documento</span><span class="sxs-lookup"><span data-stu-id="0bee4-102">Document Approval Process</span></span>

<span data-ttu-id="0bee4-103">Este ejemplo muestra el uso conjunto de muchas características de Windows Workflow Foundation (WF) y Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0bee4-103">This sample demonstrates the use of many Windows Workflow Foundation (WF) and Windows Communication Foundation (WCF) features together.</span></span> <span data-ttu-id="0bee4-104">Juntas implementan un escenario de proceso de aprobación de un documento.</span><span class="sxs-lookup"><span data-stu-id="0bee4-104">Together they implement a document approval process scenario.</span></span> <span data-ttu-id="0bee4-105">Una aplicación cliente puede enviar documentos para su aprobación y aprobar documentos.</span><span class="sxs-lookup"><span data-stu-id="0bee4-105">A client application can submit documents for approval and approve documents.</span></span> <span data-ttu-id="0bee4-106">Existe una aplicación de administrador de aprobaciones para facilitar las comunicaciones entre los clientes y aplicar las reglas del proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="0bee4-106">An approval manager application exists to facilitate communications between clients and to enforce the rules of the approval process.</span></span> <span data-ttu-id="0bee4-107">El proceso de aprobación es un flujo de trabajo que puede ejecutar varios tipos de aprobación.</span><span class="sxs-lookup"><span data-stu-id="0bee4-107">The approval process is a workflow that can execute several types of approval.</span></span> <span data-ttu-id="0bee4-108">Existen actividades para obtener una aprobación única, una aprobación de quórum (un porcentaje de un conjunto de aprobadores) y un proceso de aprobación compleja que consta de una aprobación de quórum y una aprobación única en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="0bee4-108">Activities exist to get a single approval, a quorum approval (a percentage of set of approvers), and a complex approval process that consists of a quorum and single approval in a sequence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bee4-109">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="0bee4-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0bee4-110">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="0bee4-110">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="0bee4-111">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y ejemplos.</span><span class="sxs-lookup"><span data-stu-id="0bee4-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0bee4-112">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="0bee4-112">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\DocumentApprovalProcess`

## <a name="sample-details"></a><span data-ttu-id="0bee4-113">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="0bee4-113">Sample Details</span></span>

<span data-ttu-id="0bee4-114">En el gráfico siguiente se muestra el flujo de trabajo del proceso de aprobación de documentos:</span><span class="sxs-lookup"><span data-stu-id="0bee4-114">The following graphic demonstrates the document approval process workflow:</span></span>

![Flujo de trabajo del proceso de aprobación de un documento](./media/document-approval-process/document-approval-process.jpg)

<span data-ttu-id="0bee4-116">Desde la perspectiva del cliente, el proceso de aprobación funciona del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="0bee4-116">From the client's perspective, the approval process functions as follows:</span></span>

1. <span data-ttu-id="0bee4-117">Un cliente realiza una suscripción para convertirse en usuario en el sistema del proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="0bee4-117">A client subscribes to be a user in the approval process system.</span></span>

2. <span data-ttu-id="0bee4-118">Un cliente WCF envía a un servicio WCF hospedado por la aplicación de administrador de aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="0bee4-118">A WCF client sends to a WCF service hosted by the approval manager application.</span></span>

3. <span data-ttu-id="0bee4-119">Se devuelve un Id. de usuario único al cliente.</span><span class="sxs-lookup"><span data-stu-id="0bee4-119">A unique user ID is returned to the client.</span></span> <span data-ttu-id="0bee4-120">El cliente puede participar ahora en los procesos de aprobación.</span><span class="sxs-lookup"><span data-stu-id="0bee4-120">The client can now participate in approval processes.</span></span>

4. <span data-ttu-id="0bee4-121">Una vez admitido, un cliente puede enviar un documento para su aprobación mediante un proceso de aprobación única, de quórum o compleja.</span><span class="sxs-lookup"><span data-stu-id="0bee4-121">Once joined, a client can send a document for approval using single, quorum or complex approval processes.</span></span>

5. <span data-ttu-id="0bee4-122">Al hacer clic en un botón de la interfaz del cliente, se inicia una instancia de flujo de trabajo en un host de servicio de flujo de trabajo del cliente.</span><span class="sxs-lookup"><span data-stu-id="0bee4-122">A button in the client’s interface is clicked, starting a workflow instance in a client Workflow Service Host.</span></span>

6. <span data-ttu-id="0bee4-123">El flujo de trabajo envía una solicitud de aprobación a la aplicación de administrador de aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="0bee4-123">The workflow sends an approval request to the approval manager application.</span></span>

7. <span data-ttu-id="0bee4-124">El administrador del flujo de trabajo inicia un flujo de trabajo por su parte para representar un proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="0bee4-124">The workflow manager starts a workflow on its own side to represent an approval process.</span></span>

8. <span data-ttu-id="0bee4-125">Una vez ejecutado el flujo de trabajo de aprobación del administrador, los resultados se devuelven al cliente.</span><span class="sxs-lookup"><span data-stu-id="0bee4-125">Once the manager approval workflow executes, the results are sent back to the client.</span></span>

9. <span data-ttu-id="0bee4-126">El cliente muestra los resultados.</span><span class="sxs-lookup"><span data-stu-id="0bee4-126">The client displays the results.</span></span>

10. <span data-ttu-id="0bee4-127">Un cliente puede recibir una solicitud de aprobación y responder a la solicitud en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="0bee4-127">A client may receive an approval request and respond to the request at any point in time.</span></span>

11. <span data-ttu-id="0bee4-128">Un servicio WCF hospedado en el cliente puede recibir una solicitud de aprobación de la aplicación del administrador de aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="0bee4-128">A WCF service hosted on the client can receive an approval request from the approval manager application.</span></span>

12. <span data-ttu-id="0bee4-129">La información del documento se presenta en el cliente para revisión.</span><span class="sxs-lookup"><span data-stu-id="0bee4-129">The document information is presented on the client for review.</span></span>

13. <span data-ttu-id="0bee4-130">El usuario puede aprobar o rechazar el documento.</span><span class="sxs-lookup"><span data-stu-id="0bee4-130">The user can approve or reject the document.</span></span>

14. <span data-ttu-id="0bee4-131">Un cliente de WCF se usa para devolver una respuesta de aprobación a la aplicación de administrador de aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="0bee4-131">A WCF client is used to send an approval response back to the approval manager application.</span></span>

<span data-ttu-id="0bee4-132">Desde el punto de vista de la aplicación de administrador de aprobaciones, el proceso de aprobación funciona del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="0bee4-132">From the approval manager application’s point of view, the approval process functions as follows:</span></span>

1. <span data-ttu-id="0bee4-133">Un cliente solicita al sistema del proceso de aprobación participar.</span><span class="sxs-lookup"><span data-stu-id="0bee4-133">A client requests to participate to the approval process system.</span></span>

2. <span data-ttu-id="0bee4-134">Un servicio WCF en el administrador de aprobaciones recibe una solicitud para formar parte del sistema del proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="0bee4-134">A WCF service on the approval manager receives a request to be part of the approval process system.</span></span>

3. <span data-ttu-id="0bee4-135">Se genera un identificador único para el cliente.</span><span class="sxs-lookup"><span data-stu-id="0bee4-135">A unique ID is generated for the client.</span></span> <span data-ttu-id="0bee4-136">La información sobre el usuario se almacena en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="0bee4-136">The user information is stored in a database.</span></span>

4. <span data-ttu-id="0bee4-137">El identificador único se envía al usuario.</span><span class="sxs-lookup"><span data-stu-id="0bee4-137">The unique ID is sent back to the user.</span></span>

5. <span data-ttu-id="0bee4-138">Se recibe una solicitud de aprobación.</span><span class="sxs-lookup"><span data-stu-id="0bee4-138">An approval request is receive.</span></span> <span data-ttu-id="0bee4-139">El administrador de aprobaciones ejecuta un proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="0bee4-139">The approval manager executes an approval process.</span></span>

6. <span data-ttu-id="0bee4-140">El administrador de aprobaciones recibe una solicitud de aprobación, lo que inicia un nuevo flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0bee4-140">An approval request is received by the approval manager, starting a new workflow.</span></span>

7. <span data-ttu-id="0bee4-141">Según el tipo de solicitud (simple, quórum o compleja), se ejecuta una actividad diferente.</span><span class="sxs-lookup"><span data-stu-id="0bee4-141">Depending on the type of request (simple, quorum, or complex) a different activity is executed.</span></span>

8. <span data-ttu-id="0bee4-142">Las actividades Send y Receive con correlación se utilizan para enviar la solicitud de aprobación al cliente para su revisión y recibir la respuesta.</span><span class="sxs-lookup"><span data-stu-id="0bee4-142">Send and Receive activities with correlation are used to send the approval request to the client for review and receive the response.</span></span>

9. <span data-ttu-id="0bee4-143">El resultado del flujo de trabajo del proceso de aprobación se envía al cliente.</span><span class="sxs-lookup"><span data-stu-id="0bee4-143">The result of the approval process workflow is sent to the client.</span></span>

## <a name="using-the-sample"></a><span data-ttu-id="0bee4-144">Utilizar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="0bee4-144">Using the Sample</span></span>

##### <a name="to-set-up-the-database"></a><span data-ttu-id="0bee4-145">Para configurar la base de datos</span><span class="sxs-lookup"><span data-stu-id="0bee4-145">To set up the database</span></span>

1. <span data-ttu-id="0bee4-146">Desde un símbolo del sistema de Visual Studio 2010 abierto con privilegios de administrador, vaya a esta carpeta DocumentApprovalProcess y ejecute setup. cmd.</span><span class="sxs-lookup"><span data-stu-id="0bee4-146">From a Visual Studio 2010 command prompt opened with Administrator privileges, navigate to this DocumentApprovalProcess folder and run Setup.cmd.</span></span>

##### <a name="to-set-up-the-application"></a><span data-ttu-id="0bee4-147">Para configurar la aplicación</span><span class="sxs-lookup"><span data-stu-id="0bee4-147">To set up the application</span></span>

1. <span data-ttu-id="0bee4-148">Con Visual Studio 2010, abra el archivo de solución DocumentApprovalProcess. sln.</span><span class="sxs-lookup"><span data-stu-id="0bee4-148">Using Visual Studio 2010, open the DocumentApprovalProcess.sln solution file.</span></span>

2. <span data-ttu-id="0bee4-149">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="0bee4-149">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="0bee4-150">Para ejecutar la solución, inicie la aplicación del administrador de aprobaciones; para ello, haga clic con el->botón secundario en el proyecto ApprovalManager en el **Explorador de soluciones** y haga clic en depurar**iniciar** nueva instancia en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="0bee4-150">To run the solution, launch the Approval Manager Application by right-clicking the ApprovalManager project in the **Solution Explorer** and clicking **Debug**->**Start** new instance from the right-click menu.</span></span>

    <span data-ttu-id="0bee4-151">Espere a que el resultado del administrador le indique que está listo.</span><span class="sxs-lookup"><span data-stu-id="0bee4-151">Wait for the manager’s output to let you know that it is ready.</span></span>

##### <a name="to-run-the-single-approval-scenario"></a><span data-ttu-id="0bee4-152">Para ejecutar el escenario de aprobación única</span><span class="sxs-lookup"><span data-stu-id="0bee4-152">To run the single approval scenario</span></span>

1. <span data-ttu-id="0bee4-153">Abra un símbolo del sistema con permisos de administrador.</span><span class="sxs-lookup"><span data-stu-id="0bee4-153">Open a command prompt with administrator permission.</span></span>

2. <span data-ttu-id="0bee4-154">Navegue al directorio que contiene la solución.</span><span class="sxs-lookup"><span data-stu-id="0bee4-154">Navigate to the directory that contains the solution.</span></span>

3. <span data-ttu-id="0bee4-155">Navegue a la carpeta ApprovalClient\Bin\Debug y ejecute dos instancias de ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="0bee4-155">Navigate to the ApprovalClient\Bin\Debug folder and execute two instances of ApprovalClient.exe.</span></span>

4. <span data-ttu-id="0bee4-156">Haga clic en **detectar**, espere hasta que se habilite el botón **suscribir** .</span><span class="sxs-lookup"><span data-stu-id="0bee4-156">Click **discover**, wait until the **subscribe** button is enabled.</span></span>

5. <span data-ttu-id="0bee4-157">Escriba cualquier nombre de usuario yhaga clic en suscribirse.</span><span class="sxs-lookup"><span data-stu-id="0bee4-157">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="0bee4-158">Para un cliente, use `UserType1` y para el otro, escriba `UserType2`.</span><span class="sxs-lookup"><span data-stu-id="0bee4-158">For one client, use `UserType1` and the other type `UserType2`.</span></span>

6. <span data-ttu-id="0bee4-159">En el cliente `UserType1`, seleccione el tipo de aprobación única en el menú desplegable y escriba un nombre de documento y su contenido.</span><span class="sxs-lookup"><span data-stu-id="0bee4-159">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="0bee4-160">Haga clic en **solicitar aprobación**.</span><span class="sxs-lookup"><span data-stu-id="0bee4-160">Click **Request Approval**.</span></span>

7. <span data-ttu-id="0bee4-161">En el cliente `UserType2`, aparecerá un documento a la espera de aprobación.</span><span class="sxs-lookup"><span data-stu-id="0bee4-161">In the `UserType2` client, a document awaiting approval appears.</span></span> <span data-ttu-id="0bee4-162">Selecciónelo y presione **aprobar** o **rechazar**.</span><span class="sxs-lookup"><span data-stu-id="0bee4-162">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="0bee4-163">Los resultados deberían mostrarse en el cliente `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="0bee4-163">The results should show in the `UserType1` client.</span></span>

##### <a name="to-run-the-quorum-approval-scenario"></a><span data-ttu-id="0bee4-164">Para ejecutar el escenario de aprobación de quórum</span><span class="sxs-lookup"><span data-stu-id="0bee4-164">To run the quorum approval scenario</span></span>

1. <span data-ttu-id="0bee4-165">Abra un símbolo del sistema con permisos de administrador.</span><span class="sxs-lookup"><span data-stu-id="0bee4-165">Open a command prompt with administrator permission.</span></span>

2. <span data-ttu-id="0bee4-166">Navegue al directorio que contiene la solución.</span><span class="sxs-lookup"><span data-stu-id="0bee4-166">Navigate to the directory that contains the solution.</span></span>

3. <span data-ttu-id="0bee4-167">Navegue a la carpeta ApprovalClient\Bin\Debug y ejecute tres instancias de ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="0bee4-167">Navigate to the ApprovalClient\Bin\Debug folder and execute three instances of ApprovalClient.exe.</span></span>

4. <span data-ttu-id="0bee4-168">Haga clic en **detectar**, espere hasta que se habilite el botón **suscribir** .</span><span class="sxs-lookup"><span data-stu-id="0bee4-168">Click **discover**, wait until the **subscribe** button is enabled.</span></span>

5. <span data-ttu-id="0bee4-169">Escriba cualquier nombre de usuario yhaga clic en suscribirse.</span><span class="sxs-lookup"><span data-stu-id="0bee4-169">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="0bee4-170">Para un cliente, use `UserType1` y para los otros dos, escriba `UserType2`.</span><span class="sxs-lookup"><span data-stu-id="0bee4-170">For one client use `UserType1` and the other two type `UserType2`.</span></span>

6. <span data-ttu-id="0bee4-171">En el cliente `UserType1`, seleccione el tipo de aprobación de quórum en el menú desplegable y escriba un nombre de documento y su contenido.</span><span class="sxs-lookup"><span data-stu-id="0bee4-171">In the `UserType1` client, select the quorum approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="0bee4-172">Haga clic en **solicitar aprobación**.</span><span class="sxs-lookup"><span data-stu-id="0bee4-172">Click **Request Approval**.</span></span> <span data-ttu-id="0bee4-173">Este tipo de aprobación requieres que los dos clientes `UserType2` aprueben o rechacen el documento.</span><span class="sxs-lookup"><span data-stu-id="0bee4-173">This requests that the two `UserType2` clients approve or reject the document.</span></span> <span data-ttu-id="0bee4-174">Aunque los dos clientes `UserType2` deben responder, solo uno de ellos necesita aprobar el documento para que se considere aprobado.</span><span class="sxs-lookup"><span data-stu-id="0bee4-174">While both `UserType2` clients must respond, only one client must approve the document for it to be approved.</span></span>

7. <span data-ttu-id="0bee4-175">En los clientes `UserType2`, aparecerá un documento a la espera de aprobación.</span><span class="sxs-lookup"><span data-stu-id="0bee4-175">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="0bee4-176">Selecciónelo y presione **aprobar** o **rechazar**.</span><span class="sxs-lookup"><span data-stu-id="0bee4-176">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="0bee4-177">Los resultados deberían mostrarse en el cliente `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="0bee4-177">The results should show in the `UserType1` client.</span></span>

##### <a name="to-run-the-complex-approval-scenario"></a><span data-ttu-id="0bee4-178">Para ejecutar el escenario de aprobación compleja</span><span class="sxs-lookup"><span data-stu-id="0bee4-178">To run the complex approval scenario</span></span>

1. <span data-ttu-id="0bee4-179">Abra un símbolo del sistema con permisos de administrador.</span><span class="sxs-lookup"><span data-stu-id="0bee4-179">Open a command prompt with administrator permission.</span></span>

2. <span data-ttu-id="0bee4-180">Navegue al directorio que contiene la solución.</span><span class="sxs-lookup"><span data-stu-id="0bee4-180">Navigate to the directory that contains the solution.</span></span>

3. <span data-ttu-id="0bee4-181">Navegue a la carpeta ApprovalClient\Bin\Debug y ejecute cuatro instancias de ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="0bee4-181">Navigate to the ApprovalClient\Bin\Debug folder and execute four instances of ApprovalClient.exe.</span></span>

4. <span data-ttu-id="0bee4-182">Haga clic en **detectar**, espere hasta que se habilite el botón **suscribir** .</span><span class="sxs-lookup"><span data-stu-id="0bee4-182">Click **discover**, wait until the **subscribe** button is enabled.</span></span>

5. <span data-ttu-id="0bee4-183">Escriba cualquier nombre de usuario yhaga clic en suscribirse.</span><span class="sxs-lookup"><span data-stu-id="0bee4-183">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="0bee4-184">Para un cliente, use `UserType1`, para los otros dos, escriba `UserType2` y en el último, use `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="0bee4-184">For one client use `UserType1`, in two uses type `UserType2`, and in the last use `UserType3`.</span></span>

6. <span data-ttu-id="0bee4-185">En el cliente `UserType1`, seleccione el tipo de aprobación única en el menú desplegable y escriba un nombre de documento y su contenido.</span><span class="sxs-lookup"><span data-stu-id="0bee4-185">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="0bee4-186">Haga clic en **solicitar aprobación**.</span><span class="sxs-lookup"><span data-stu-id="0bee4-186">Click **Request Approval**.</span></span>

7. <span data-ttu-id="0bee4-187">En los clientes `UserType2`, aparecerá un documento a la espera de aprobación.</span><span class="sxs-lookup"><span data-stu-id="0bee4-187">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="0bee4-188">Selecciónelo y presione **aprobar**; el documento se pasa al `UserType3` cliente.</span><span class="sxs-lookup"><span data-stu-id="0bee4-188">Select it and press **approve**, the document is passed to the `UserType3` client.</span></span>

    <span data-ttu-id="0bee4-189">Si el primer quórum `UserType2` aprueba el documento, el documento se pasa al cliente `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="0bee4-189">If the document is approved by the first `UserType2` quorum, the document is passed to the `UserType3` client.</span></span>

8. <span data-ttu-id="0bee4-190">Apruebe o rechace el documento en el cliente `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="0bee4-190">Approve or reject the document from the `UserType3` client.</span></span> <span data-ttu-id="0bee4-191">Los resultados deberían mostrarse en el cliente `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="0bee4-191">The results should show in the `UserType1` client.</span></span>

##### <a name="to-clean-up"></a><span data-ttu-id="0bee4-192">Para realizar una limpieza</span><span class="sxs-lookup"><span data-stu-id="0bee4-192">To clean up</span></span>

1. <span data-ttu-id="0bee4-193">Desde un símbolo del sistema de Visual Studio 2010, vaya a la carpeta DocumentApprovalProcess y ejecute Cleanup. cmd.</span><span class="sxs-lookup"><span data-stu-id="0bee4-193">From a Visual Studio 2010 command prompt, navigate to the DocumentApprovalProcess folder and run Cleanup.cmd.</span></span>
