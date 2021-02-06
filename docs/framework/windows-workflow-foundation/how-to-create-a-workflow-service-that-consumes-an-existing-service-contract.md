---
description: 'Más información acerca de cómo: crear un servicio de flujo de trabajo que consuma un contrato de servicio existente'
title: Procedimiento para crear un servicio de flujo de trabajo que consuma un contrato de servicio existente
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: 0a31f0f4e205c72b857b59726437e896a7c68231
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631260"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a><span data-ttu-id="6652b-103">Procedimiento para crear un servicio de flujo de trabajo que consuma un contrato de servicio existente</span><span class="sxs-lookup"><span data-stu-id="6652b-103">How to: Create a workflow service that consumes an existing service contract</span></span>

<span data-ttu-id="6652b-104">.NET Framework 4,5 ofrece una mejor integración entre los servicios web y los flujos de trabajo en forma de desarrollo de flujo de trabajo de contrato primero.</span><span class="sxs-lookup"><span data-stu-id="6652b-104">.NET Framework 4.5 features better integration between web services and workflows in the form of contract-first workflow development.</span></span> <span data-ttu-id="6652b-105">La herramienta de desarrollo de flujo de trabajo de contrato primero permite diseñar el contrato en Code First.</span><span class="sxs-lookup"><span data-stu-id="6652b-105">The contract-first workflow development tool allows you to design the contract in code first.</span></span> <span data-ttu-id="6652b-106">La herramienta después genera automáticamente una plantilla de actividad en el cuadro de herramientas para las operaciones del contrato.</span><span class="sxs-lookup"><span data-stu-id="6652b-106">The tool then automatically generates an activity template in the toolbox for the operations in the contract.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6652b-107">Este tema proporciona instrucciones paso a paso sobre cómo crear un servicio de flujo de trabajo de contrato primero.</span><span class="sxs-lookup"><span data-stu-id="6652b-107">This topic provides step-by-step guidance on creating a contract-first workflow service.</span></span> <span data-ttu-id="6652b-108">Para obtener más información sobre el desarrollo de servicios de flujo de trabajo de contrato primero, vea [contrato primer desarrollo de servicio de flujo de trabajo](contract-first-workflow-service-development.md).</span><span class="sxs-lookup"><span data-stu-id="6652b-108">For more information about contract-first workflow service development, see [Contract First Workflow Service Development](contract-first-workflow-service-development.md).</span></span>  
  
### <a name="creating-the-workflow-project"></a><span data-ttu-id="6652b-109">Crear el proyecto de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="6652b-109">Creating the workflow project</span></span>  
  
1. <span data-ttu-id="6652b-110">En Visual Studio, seleccione **Archivo**, **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6652b-110">In Visual Studio, select **File**, **New Project**.</span></span> <span data-ttu-id="6652b-111">Seleccione el nodo **WCF** en el nodo **C#** en el árbol **plantillas** y seleccione la plantilla **aplicación de servicio de flujo de trabajo WCF** .</span><span class="sxs-lookup"><span data-stu-id="6652b-111">Select the **WCF** node under the **C#** node in the **Templates** tree, and select the **WCF Workflow Service Application** template.</span></span>  
  
2. <span data-ttu-id="6652b-112">Asigne un nombre al nuevo proyecto `ContractFirst` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6652b-112">Name the new project `ContractFirst` and click **Ok**.</span></span>  
  
### <a name="creating-the-service-contract"></a><span data-ttu-id="6652b-113">Crear el contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="6652b-113">Creating the service contract</span></span>  
  
1. <span data-ttu-id="6652b-114">Haga clic con el botón derecho en el proyecto en **Explorador de soluciones** y seleccione **Agregar**, **nuevo elemento.**...</span><span class="sxs-lookup"><span data-stu-id="6652b-114">Right-click the project in **Solution Explorer** and select **Add**, **New Item…**.</span></span> <span data-ttu-id="6652b-115">Seleccione el nodo de **código** de la izquierda y la plantilla de **clase** a la derecha.</span><span class="sxs-lookup"><span data-stu-id="6652b-115">Select the **Code** node on the left, and the **Class** template on the right.</span></span> <span data-ttu-id="6652b-116">Asigne a la nueva clase el nombre `IBookService` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6652b-116">Name the new class `IBookService` and click **Ok**.</span></span>  
  
2. <span data-ttu-id="6652b-117">En la parte superior de la ventana de código que aparece, agregue una instrucción Using a `System.Servicemodel`.</span><span class="sxs-lookup"><span data-stu-id="6652b-117">In the top of the code window that appears, add a Using statement to `System.Servicemodel`.</span></span>  
  
    ```csharp  
    using System.ServiceModel;  
    ```  
  
3. <span data-ttu-id="6652b-118">Cambie la definición de clase de ejemplo a la definición de interfaz siguiente.</span><span class="sxs-lookup"><span data-stu-id="6652b-118">Change the sample class definition to the following interface definition.</span></span>  
  
    ```csharp  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4. <span data-ttu-id="6652b-119">Para compilar el proyecto, presione **Ctrl + Mayús + B**.</span><span class="sxs-lookup"><span data-stu-id="6652b-119">Build the project by pressing **Ctrl+Shift+B**.</span></span>  
  
### <a name="importing-the-service-contract"></a><span data-ttu-id="6652b-120">Importar el contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="6652b-120">Importing the service contract</span></span>  
  
1. <span data-ttu-id="6652b-121">Haga clic con el botón derecho en el proyecto en **Explorador de soluciones** y seleccione **importar contrato de servicio**.</span><span class="sxs-lookup"><span data-stu-id="6652b-121">Right-click the project in **Solution Explorer** and select **Import Service Contract**.</span></span> <span data-ttu-id="6652b-122">En **\<Current Project>** , Abra todos los subnodos y seleccione **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="6652b-122">Under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="6652b-123">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6652b-123">Click **OK**.</span></span>  
  
2. <span data-ttu-id="6652b-124">Verá un cuadro de diálogo que avisa de que la operación se ha completado correctamente y de que las actividades generadas aparecerán en el cuadro de herramientas tras haber compilado el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6652b-124">A dialog will open, alerting you that the operation completed successfully, and that the generated activities will appear in the toolbox after you build the project.</span></span> <span data-ttu-id="6652b-125">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6652b-125">Click **OK**.</span></span>  
  
3. <span data-ttu-id="6652b-126">Para compilar el proyecto, presione **Ctrl + Mayús + B**, de modo que las actividades importadas aparezcan en el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="6652b-126">Build the project by pressing **Ctrl+Shift+B**, so that the imported activities will appear in the toolbox.</span></span>  
  
4. <span data-ttu-id="6652b-127">En **Explorador de soluciones**, abra Service1. xamlx.</span><span class="sxs-lookup"><span data-stu-id="6652b-127">In **Solution Explorer**, open Service1.xamlx.</span></span> <span data-ttu-id="6652b-128">El servicio de flujo de trabajo aparecerá en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="6652b-128">The workflow service will appear in the designer.</span></span>  
  
5. <span data-ttu-id="6652b-129">Seleccione la actividad **secuencia** .</span><span class="sxs-lookup"><span data-stu-id="6652b-129">Select the **Sequence** activity.</span></span> <span data-ttu-id="6652b-130">En el ventana Propiedades, haga clic en **...**</span><span class="sxs-lookup"><span data-stu-id="6652b-130">In the Properties window, click the **…**</span></span> <span data-ttu-id="6652b-131">en la propiedad **ImplementedContract** .</span><span class="sxs-lookup"><span data-stu-id="6652b-131">button in the **ImplementedContract** property.</span></span> <span data-ttu-id="6652b-132">En la ventana **Editor de colección de tipos** que aparece, haga clic en la lista desplegable **tipo** y seleccione el botón **Buscar tipos..** .</span><span class="sxs-lookup"><span data-stu-id="6652b-132">In the **Type Collection Editor** window that appears, click the **Type** dropdown, and select the **Browse for Types…**</span></span> <span data-ttu-id="6652b-133">y haga clic en ella.</span><span class="sxs-lookup"><span data-stu-id="6652b-133">entry.</span></span> <span data-ttu-id="6652b-134">En el cuadro de diálogo **examinar y seleccionar un tipo .net** , en **\<Current Project>** , Abra todos los subnodos y seleccione **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="6652b-134">In the **Browse and Select a .NET Type** dialog, under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="6652b-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6652b-135">Click **OK**.</span></span> <span data-ttu-id="6652b-136">En el cuadro de diálogo **Editor de colección de tipos** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6652b-136">In the **Type Collection Editor** dialog, click **OK**.</span></span>  
  
6. <span data-ttu-id="6652b-137">Seleccione y elimine las actividades **ReceiveRequest** y **SendResponse** .</span><span class="sxs-lookup"><span data-stu-id="6652b-137">Select and delete the **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
7. <span data-ttu-id="6652b-138">En el cuadro de herramientas, arrastre un **Buy_ReceiveAndSendReply** y una actividad de **Checkout_Receive** a la actividad de **servicio secuencial** .</span><span class="sxs-lookup"><span data-stu-id="6652b-138">From the toolbox, drag a **Buy_ReceiveAndSendReply** and a **Checkout_Receive** activity onto the **Sequential Service** activity.</span></span>
