---
title: Procedimiento para crear un servicio de flujo de trabajo que consuma un contrato de servicio existente
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: c2ca9c349718c3939d74d052ff0ed448879cd045
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945579"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a><span data-ttu-id="ff184-102">Procedimiento para crear un servicio de flujo de trabajo que consuma un contrato de servicio existente</span><span class="sxs-lookup"><span data-stu-id="ff184-102">How to: Create a workflow service that consumes an existing service contract</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="ff184-103">presenta una mejor integración entre los servicios web y los flujos de trabajo en forma de desarrollo de flujo de trabajo de contrato primero.</span><span class="sxs-lookup"><span data-stu-id="ff184-103">features better integration between web services and workflows in the form of contract-first workflow development.</span></span> <span data-ttu-id="ff184-104">La herramienta de desarrollo de flujo de trabajo de contrato primero permite diseñar el contrato en Code First.</span><span class="sxs-lookup"><span data-stu-id="ff184-104">The contract-first workflow development tool allows you to design the contract in code first.</span></span> <span data-ttu-id="ff184-105">La herramienta después genera automáticamente una plantilla de actividad en el cuadro de herramientas para las operaciones del contrato.</span><span class="sxs-lookup"><span data-stu-id="ff184-105">The tool then automatically generates an activity template in the toolbox for the operations in the contract.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff184-106">Este tema proporciona instrucciones paso a paso sobre cómo crear un servicio de flujo de trabajo de contrato primero.</span><span class="sxs-lookup"><span data-stu-id="ff184-106">This topic provides step-by-step guidance on creating a contract-first workflow service.</span></span> <span data-ttu-id="ff184-107">Para obtener más información sobre el desarrollo de servicio de flujo de trabajo de contrato primero, consulte [desarrollo de servicio de flujo de trabajo de contrato primero](contract-first-workflow-service-development.md).</span><span class="sxs-lookup"><span data-stu-id="ff184-107">For more information about contract-first workflow service development, see [Contract First Workflow Service Development](contract-first-workflow-service-development.md).</span></span>  
  
### <a name="creating-the-workflow-project"></a><span data-ttu-id="ff184-108">Crear el proyecto de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="ff184-108">Creating the workflow project</span></span>  
  
1. <span data-ttu-id="ff184-109">En Visual Studio, seleccione **archivo**, **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="ff184-109">In Visual Studio, select **File**, **New Project**.</span></span> <span data-ttu-id="ff184-110">Seleccione el **WCF** nodo bajo el **C#** nodo en el **plantillas** del árbol y seleccione el **aplicación de servicio de flujo de trabajo de WCF** plantilla.</span><span class="sxs-lookup"><span data-stu-id="ff184-110">Select the **WCF** node under the **C#** node in the **Templates** tree, and select the **WCF Workflow Service Application** template.</span></span>  
  
2. <span data-ttu-id="ff184-111">Asigne al nuevo proyecto `ContractFirst` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff184-111">Name the new project `ContractFirst` and click **Ok**.</span></span>  
  
### <a name="creating-the-service-contract"></a><span data-ttu-id="ff184-112">Crear el contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="ff184-112">Creating the service contract</span></span>  
  
1. <span data-ttu-id="ff184-113">Haga clic en el proyecto en **el Explorador de soluciones** y seleccione **agregar**, **nuevo elemento...** .</span><span class="sxs-lookup"><span data-stu-id="ff184-113">Right-click the project in **Solution Explorer** and select **Add**, **New Item…**.</span></span> <span data-ttu-id="ff184-114">Seleccione el **código** nodo a la izquierda y el **clase** plantilla a la derecha.</span><span class="sxs-lookup"><span data-stu-id="ff184-114">Select the **Code** node on the left, and the **Class** template on the right.</span></span> <span data-ttu-id="ff184-115">Nombre de la nueva clase `IBookService` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff184-115">Name the new class `IBookService` and click **Ok**.</span></span>  
  
2. <span data-ttu-id="ff184-116">En la parte superior de la ventana de código que aparece, agregue una instrucción Using a `System.Servicemodel`.</span><span class="sxs-lookup"><span data-stu-id="ff184-116">In the top of the code window that appears, add a Using statement to `System.Servicemodel`.</span></span>  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3. <span data-ttu-id="ff184-117">Cambie la definición de clase de ejemplo a la definición de interfaz siguiente.</span><span class="sxs-lookup"><span data-stu-id="ff184-117">Change the sample class definition to the following interface definition.</span></span>  
  
    ```  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4. <span data-ttu-id="ff184-118">Compile el proyecto presionando **Ctrl + Mayús + B**.</span><span class="sxs-lookup"><span data-stu-id="ff184-118">Build the project by pressing **Ctrl+Shift+B**.</span></span>  
  
### <a name="importing-the-service-contract"></a><span data-ttu-id="ff184-119">Importar el contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="ff184-119">Importing the service contract</span></span>  
  
1. <span data-ttu-id="ff184-120">Haga clic en el proyecto en **el Explorador de soluciones** y seleccione **importar contrato de servicio**.</span><span class="sxs-lookup"><span data-stu-id="ff184-120">Right-click the project in **Solution Explorer** and select **Import Service Contract**.</span></span> <span data-ttu-id="ff184-121">En  **\<proyecto actual >**, abra todos los subnodos y seleccione **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="ff184-121">Under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="ff184-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff184-122">Click **OK**.</span></span>  
  
2. <span data-ttu-id="ff184-123">Verá un cuadro de diálogo que avisa de que la operación se ha completado correctamente y de que las actividades generadas aparecerán en el cuadro de herramientas tras haber compilado el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ff184-123">A dialog will open, alerting you that the operation completed successfully, and that the generated activities will appear in the toolbox after you build the project.</span></span> <span data-ttu-id="ff184-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff184-124">Click **OK**.</span></span>  
  
3. <span data-ttu-id="ff184-125">Compile el proyecto presionando **Ctrl + Mayús + B**, de modo que las actividades importadas aparezcan en el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="ff184-125">Build the project by pressing **Ctrl+Shift+B**, so that the imported activities will appear in the toolbox.</span></span>  
  
4. <span data-ttu-id="ff184-126">En **el Explorador de soluciones**, abra Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="ff184-126">In **Solution Explorer**, open Service1.xamlx.</span></span> <span data-ttu-id="ff184-127">El servicio de flujo de trabajo aparecerá en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="ff184-127">The workflow service will appear in the designer.</span></span>  
  
5. <span data-ttu-id="ff184-128">Seleccione el **secuencia** actividad.</span><span class="sxs-lookup"><span data-stu-id="ff184-128">Select the **Sequence** activity.</span></span> <span data-ttu-id="ff184-129">En la ventana Propiedades, haga clic en el **...**</span><span class="sxs-lookup"><span data-stu-id="ff184-129">In the Properties window, click the **…**</span></span> <span data-ttu-id="ff184-130">botón en el **ImplementedContract** propiedad.</span><span class="sxs-lookup"><span data-stu-id="ff184-130">button in the **ImplementedContract** property.</span></span> <span data-ttu-id="ff184-131">En el **Editor de la colección de tipo** ventana que aparece, haga clic en el **tipo** lista desplegable y seleccione el **buscar tipos...**</span><span class="sxs-lookup"><span data-stu-id="ff184-131">In the **Type Collection Editor** window that appears, click the **Type** dropdown, and select the **Browse for Types…**</span></span> <span data-ttu-id="ff184-132">entrada.</span><span class="sxs-lookup"><span data-stu-id="ff184-132">entry.</span></span> <span data-ttu-id="ff184-133">En el **examinar y seleccionar un tipo .NET** cuadro de diálogo, en  **\<proyecto actual >**, abra todos los subnodos y seleccione **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="ff184-133">In the **Browse and Select a .NET Type** dialog, under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="ff184-134">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff184-134">Click **OK**.</span></span> <span data-ttu-id="ff184-135">En el **Editor de la colección de tipo** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff184-135">In the **Type Collection Editor** dialog, click **OK**.</span></span>  
  
6. <span data-ttu-id="ff184-136">Seleccione y elimine el **ReceiveRequest** y **SendResponse** actividades.</span><span class="sxs-lookup"><span data-stu-id="ff184-136">Select and delete the **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
7. <span data-ttu-id="ff184-137">En el cuadro de herramientas, arrastre un **Buy_ReceiveAndSendReply** y un **Checkout_Receive** actividad en el **servicio secuencial** actividad.</span><span class="sxs-lookup"><span data-stu-id="ff184-137">From the toolbox, drag a **Buy_ReceiveAndSendReply** and a **Checkout_Receive** activity onto the **Sequential Service** activity.</span></span>
