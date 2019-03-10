---
title: Filtrar Crear un servicio de flujo de trabajo que consuma un contrato de servicio existente
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: 57babf216821665613da053f972ff25488418b7d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705069"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a><span data-ttu-id="efc0b-102">Filtrar Crear un servicio de flujo de trabajo que consuma un contrato de servicio existente</span><span class="sxs-lookup"><span data-stu-id="efc0b-102">How to: Create a workflow service that consumes an existing service contract</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="efc0b-103">presenta una mejor integración entre los servicios web y los flujos de trabajo en forma de desarrollo de flujo de trabajo de contrato primero.</span><span class="sxs-lookup"><span data-stu-id="efc0b-103">features better integration between web services and workflows in the form of contract-first workflow development.</span></span> <span data-ttu-id="efc0b-104">La herramienta de desarrollo de flujo de trabajo de contrato primero permite diseñar el contrato en Code First.</span><span class="sxs-lookup"><span data-stu-id="efc0b-104">The contract-first workflow development tool allows you to design the contract in code first.</span></span> <span data-ttu-id="efc0b-105">La herramienta después genera automáticamente una plantilla de actividad en el cuadro de herramientas para las operaciones del contrato.</span><span class="sxs-lookup"><span data-stu-id="efc0b-105">The tool then automatically generates an activity template in the toolbox for the operations in the contract.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efc0b-106">Este tema proporciona instrucciones paso a paso sobre cómo crear un servicio de flujo de trabajo de contrato primero.</span><span class="sxs-lookup"><span data-stu-id="efc0b-106">This topic provides step-by-step guidance on creating a contract-first workflow service.</span></span> <span data-ttu-id="efc0b-107">Para obtener más información sobre el desarrollo de servicio de flujo de trabajo de contrato primero, consulte [desarrollo de servicio de flujo de trabajo de contrato primero](contract-first-workflow-service-development.md).</span><span class="sxs-lookup"><span data-stu-id="efc0b-107">For more information about contract-first workflow service development, see [Contract First Workflow Service Development](contract-first-workflow-service-development.md).</span></span>  
  
### <a name="creating-the-workflow-project"></a><span data-ttu-id="efc0b-108">Crear el proyecto de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="efc0b-108">Creating the workflow project</span></span>  
  
1.  <span data-ttu-id="efc0b-109">En Visual Studio, seleccione **archivo**, **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="efc0b-109">In Visual Studio, select **File**, **New Project**.</span></span> <span data-ttu-id="efc0b-110">Seleccione el **WCF** nodo bajo el **C#** nodo en el **plantillas** del árbol y seleccione el **aplicación de servicio de flujo de trabajo de WCF** plantilla.</span><span class="sxs-lookup"><span data-stu-id="efc0b-110">Select the **WCF** node under the **C#** node in the **Templates** tree, and select the **WCF Workflow Service Application** template.</span></span>  
  
2.  <span data-ttu-id="efc0b-111">Asigne al nuevo proyecto `ContractFirst` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="efc0b-111">Name the new project `ContractFirst` and click **Ok**.</span></span>  
  
### <a name="creating-the-service-contract"></a><span data-ttu-id="efc0b-112">Crear el contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="efc0b-112">Creating the service contract</span></span>  
  
1.  <span data-ttu-id="efc0b-113">Haga clic en el proyecto en **el Explorador de soluciones** y seleccione **agregar**, **nuevo elemento...** .</span><span class="sxs-lookup"><span data-stu-id="efc0b-113">Right-click the project in **Solution Explorer** and select **Add**, **New Item…**.</span></span> <span data-ttu-id="efc0b-114">Seleccione el **código** nodo a la izquierda y el **clase** plantilla a la derecha.</span><span class="sxs-lookup"><span data-stu-id="efc0b-114">Select the **Code** node on the left, and the **Class** template on the right.</span></span> <span data-ttu-id="efc0b-115">Nombre de la nueva clase `IBookService` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="efc0b-115">Name the new class `IBookService` and click **Ok**.</span></span>  
  
2.  <span data-ttu-id="efc0b-116">En la parte superior de la ventana de código que aparece, agregue una instrucción Using a `System.Servicemodel`.</span><span class="sxs-lookup"><span data-stu-id="efc0b-116">In the top of the code window that appears, add a Using statement to `System.Servicemodel`.</span></span>  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3.  <span data-ttu-id="efc0b-117">Cambie la definición de clase de ejemplo a la definición de interfaz siguiente.</span><span class="sxs-lookup"><span data-stu-id="efc0b-117">Change the sample class definition to the following interface definition.</span></span>  
  
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
  
4.  <span data-ttu-id="efc0b-118">Compile el proyecto presionando **Ctrl + Mayús + B**.</span><span class="sxs-lookup"><span data-stu-id="efc0b-118">Build the project by pressing **Ctrl+Shift+B**.</span></span>  
  
### <a name="importing-the-service-contract"></a><span data-ttu-id="efc0b-119">Importar el contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="efc0b-119">Importing the service contract</span></span>  
  
1.  <span data-ttu-id="efc0b-120">Haga clic en el proyecto en **el Explorador de soluciones** y seleccione **importar contrato de servicio**.</span><span class="sxs-lookup"><span data-stu-id="efc0b-120">Right-click the project in **Solution Explorer** and select **Import Service Contract**.</span></span> <span data-ttu-id="efc0b-121">En  **\<proyecto actual >**, abra todos los subnodos y seleccione **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="efc0b-121">Under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="efc0b-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="efc0b-122">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="efc0b-123">Verá un cuadro de diálogo que avisa de que la operación se ha completado correctamente y de que las actividades generadas aparecerán en el cuadro de herramientas tras haber compilado el proyecto.</span><span class="sxs-lookup"><span data-stu-id="efc0b-123">A dialog will open, alerting you that the operation completed successfully, and that the generated activities will appear in the toolbox after you build the project.</span></span> <span data-ttu-id="efc0b-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="efc0b-124">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="efc0b-125">Compile el proyecto presionando **Ctrl + Mayús + B**, de modo que las actividades importadas aparezcan en el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="efc0b-125">Build the project by pressing **Ctrl+Shift+B**, so that the imported activities will appear in the toolbox.</span></span>  
  
4.  <span data-ttu-id="efc0b-126">En **el Explorador de soluciones**, abra Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="efc0b-126">In **Solution Explorer**, open Service1.xamlx.</span></span> <span data-ttu-id="efc0b-127">El servicio de flujo de trabajo aparecerá en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="efc0b-127">The workflow service will appear in the designer.</span></span>  
  
5.  <span data-ttu-id="efc0b-128">Seleccione el **secuencia** actividad.</span><span class="sxs-lookup"><span data-stu-id="efc0b-128">Select the **Sequence** activity.</span></span> <span data-ttu-id="efc0b-129">En la ventana Propiedades, haga clic en el **...**</span><span class="sxs-lookup"><span data-stu-id="efc0b-129">In the Properties window, click the **…**</span></span> <span data-ttu-id="efc0b-130">botón en el **ImplementedContract** propiedad.</span><span class="sxs-lookup"><span data-stu-id="efc0b-130">button in the **ImplementedContract** property.</span></span> <span data-ttu-id="efc0b-131">En el **Editor de la colección de tipo** ventana que aparece, haga clic en el **tipo** lista desplegable y seleccione el **buscar tipos...**</span><span class="sxs-lookup"><span data-stu-id="efc0b-131">In the **Type Collection Editor** window that appears, click the **Type** dropdown, and select the **Browse for Types…**</span></span> <span data-ttu-id="efc0b-132">entrada.</span><span class="sxs-lookup"><span data-stu-id="efc0b-132">entry.</span></span> <span data-ttu-id="efc0b-133">En el **examinar y seleccionar .net tipo** cuadro de diálogo, en  **\<proyecto actual >**, abra todos los subnodos y seleccione **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="efc0b-133">In the **Browse and Select a .Net Type** dialog, under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="efc0b-134">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="efc0b-134">Click **OK**.</span></span> <span data-ttu-id="efc0b-135">En el **Editor de la colección de tipo** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="efc0b-135">In the **Type Collection Editor** dialog, click **OK**.</span></span>  
  
6.  <span data-ttu-id="efc0b-136">Seleccione y elimine el **ReceiveRequest** y **SendResponse** actividades.</span><span class="sxs-lookup"><span data-stu-id="efc0b-136">Select and delete the **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
7.  <span data-ttu-id="efc0b-137">En el cuadro de herramientas, arrastre un **Buy_ReceiveAndSendReply** y un **Checkout_Receive** actividad en el **servicio secuencial** actividad.</span><span class="sxs-lookup"><span data-stu-id="efc0b-137">From the toolbox, drag a **Buy_ReceiveAndSendReply** and a **Checkout_Receive** activity onto the **Sequential Service** activity.</span></span>
