---
title: Crear un servicio de flujo de trabajo que consuma un contrato de servicio existente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a754875dc3f7968086f4f92044205b8ebceb01e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a><span data-ttu-id="c43f2-102">Crear un servicio de flujo de trabajo que consuma un contrato de servicio existente</span><span class="sxs-lookup"><span data-stu-id="c43f2-102">How to: Create a workflow service that consumes an existing service contract</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<span data-ttu-id="c43f2-103"> presenta una mejor integración entre los servicios web y los flujos de trabajo en forma de desarrollo de flujo de trabajo de contrato primero.</span><span class="sxs-lookup"><span data-stu-id="c43f2-103"> features better integration between web services and workflows in the form of contract-first workflow development.</span></span> <span data-ttu-id="c43f2-104">La herramienta de desarrollo de flujo de trabajo de contrato primero permite diseñar el contrato en Code First.</span><span class="sxs-lookup"><span data-stu-id="c43f2-104">The contract-first workflow development tool allows you to design the contract in code first.</span></span> <span data-ttu-id="c43f2-105">La herramienta después genera automáticamente una plantilla de actividad en el cuadro de herramientas para las operaciones del contrato.</span><span class="sxs-lookup"><span data-stu-id="c43f2-105">The tool then automatically generates an activity template in the toolbox for the operations in the contract.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c43f2-106">Este tema proporciona instrucciones paso a paso sobre cómo crear un servicio de flujo de trabajo de contrato primero.</span><span class="sxs-lookup"><span data-stu-id="c43f2-106">This topic provides step-by-step guidance on creating a contract-first workflow service.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="c43f2-107">desarrollo de servicios de flujo de trabajo de contrato primero, consulte [desarrollo de servicios de flujo de trabajo de primer contrato](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md).</span><span class="sxs-lookup"><span data-stu-id="c43f2-107"> contract-first workflow service development, see [Contract First Workflow Service Development](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md).</span></span>  
  
### <a name="creating-the-workflow-project"></a><span data-ttu-id="c43f2-108">Crear el proyecto de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="c43f2-108">Creating the workflow project</span></span>  
  
1.  <span data-ttu-id="c43f2-109">En [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)], seleccione **archivo**, **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c43f2-109">In [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)], select **File**, **New Project**.</span></span> <span data-ttu-id="c43f2-110">Seleccione el **WCF** nodo bajo el **C#** nodo en el **plantillas** del árbol y seleccione la **aplicación de servicio de flujo de trabajo de WCF** plantilla.</span><span class="sxs-lookup"><span data-stu-id="c43f2-110">Select the **WCF** node under the **C#** node in the **Templates** tree, and select the **WCF Workflow Service Application** template.</span></span>  
  
2.  <span data-ttu-id="c43f2-111">Asigne al nuevo proyecto `ContractFirst` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c43f2-111">Name the new project `ContractFirst` and click **Ok**.</span></span>  
  
### <a name="creating-the-service-contract"></a><span data-ttu-id="c43f2-112">Crear el contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="c43f2-112">Creating the service contract</span></span>  
  
1.  <span data-ttu-id="c43f2-113">Haga clic en el proyecto en **el Explorador de soluciones** y seleccione **agregar**, **nuevo elemento...** .</span><span class="sxs-lookup"><span data-stu-id="c43f2-113">Right-click the project in **Solution Explorer** and select **Add**, **New Item…**.</span></span> <span data-ttu-id="c43f2-114">Seleccione el **código** nodo a la izquierda y la **clase** plantilla a la derecha.</span><span class="sxs-lookup"><span data-stu-id="c43f2-114">Select the **Code** node on the left, and the **Class** template on the right.</span></span> <span data-ttu-id="c43f2-115">La nueva clase el nombre `IBookService` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c43f2-115">Name the new class `IBookService` and click **Ok**.</span></span>  
  
2.  <span data-ttu-id="c43f2-116">En la parte superior de la ventana de código que aparece, agregue una instrucción Using a `System.Servicemodel`.</span><span class="sxs-lookup"><span data-stu-id="c43f2-116">In the top of the code window that appears, add a Using statement to `System.Servicemodel`.</span></span>  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3.  <span data-ttu-id="c43f2-117">Cambie la definición de clase de ejemplo a la definición de interfaz siguiente.</span><span class="sxs-lookup"><span data-stu-id="c43f2-117">Change the sample class definition to the following interface definition.</span></span>  
  
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
  
4.  <span data-ttu-id="c43f2-118">Compile el proyecto presionando **Ctrl + Mayús + B**.</span><span class="sxs-lookup"><span data-stu-id="c43f2-118">Build the project by pressing **Ctrl+Shift+B**.</span></span>  
  
### <a name="importing-the-service-contract"></a><span data-ttu-id="c43f2-119">Importar el contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="c43f2-119">Importing the service contract</span></span>  
  
1.  <span data-ttu-id="c43f2-120">Haga clic en el proyecto en **el Explorador de soluciones** y seleccione **contrato de servicio de importación**.</span><span class="sxs-lookup"><span data-stu-id="c43f2-120">Right-click the project in **Solution Explorer** and select **Import Service Contract**.</span></span> <span data-ttu-id="c43f2-121">En  **\<proyecto actual >**, abra todos los subnodos y seleccione **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="c43f2-121">Under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="c43f2-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c43f2-122">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="c43f2-123">Verá un cuadro de diálogo que avisa de que la operación se ha completado correctamente y de que las actividades generadas aparecerán en el cuadro de herramientas tras haber compilado el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c43f2-123">A dialog will open, alerting you that the operation completed successfully, and that the generated activities will appear in the toolbox after you build the project.</span></span> <span data-ttu-id="c43f2-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c43f2-124">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="c43f2-125">Compile el proyecto presionando **Ctrl + Mayús + B**, de modo que las actividades importadas aparecerán en el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="c43f2-125">Build the project by pressing **Ctrl+Shift+B**, so that the imported activities will appear in the toolbox.</span></span>  
  
4.  <span data-ttu-id="c43f2-126">En **el Explorador de soluciones**, abra Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="c43f2-126">In **Solution Explorer**, open Service1.xamlx.</span></span> <span data-ttu-id="c43f2-127">El servicio de flujo de trabajo aparecerá en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="c43f2-127">The workflow service will appear in the designer.</span></span>  
  
5.  <span data-ttu-id="c43f2-128">Seleccione el **secuencia** actividad.</span><span class="sxs-lookup"><span data-stu-id="c43f2-128">Select the **Sequence** activity.</span></span> <span data-ttu-id="c43f2-129">En la ventana Propiedades, haga clic en el **...**</span><span class="sxs-lookup"><span data-stu-id="c43f2-129">In the Properties window, click the **…**</span></span> <span data-ttu-id="c43f2-130">botón en el **ImplementedContract** propiedad.</span><span class="sxs-lookup"><span data-stu-id="c43f2-130">button in the **ImplementedContract** property.</span></span> <span data-ttu-id="c43f2-131">En el **Editor de la colección de tipo** ventana que aparece, haga clic en el **tipo** lista desplegable y seleccione el **buscar tipos...**</span><span class="sxs-lookup"><span data-stu-id="c43f2-131">In the **Type Collection Editor** window that appears, click the **Type** dropdown, and select the **Browse for Types…**</span></span> <span data-ttu-id="c43f2-132">entrada.</span><span class="sxs-lookup"><span data-stu-id="c43f2-132">entry.</span></span> <span data-ttu-id="c43f2-133">En el **examinar y seleccionar .net tipo** cuadro de diálogo, en  **\<proyecto actual >**, abra todos los subnodos y seleccione **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="c43f2-133">In the **Browse and Select a .Net Type** dialog, under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="c43f2-134">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c43f2-134">Click **OK**.</span></span> <span data-ttu-id="c43f2-135">En el **Editor de la colección de tipo** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c43f2-135">In the **Type Collection Editor** dialog, click **OK**.</span></span>  
  
6.  <span data-ttu-id="c43f2-136">Seleccione y elimine la **ReceiveRequest** y **SendResponse** actividades.</span><span class="sxs-lookup"><span data-stu-id="c43f2-136">Select and delete the **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
7.  <span data-ttu-id="c43f2-137">En el cuadro de herramientas, arrastre un **Buy_ReceiveAndSendReply** y un **Checkout_Receive** actividad en el **servicio secuencial** actividad.</span><span class="sxs-lookup"><span data-stu-id="c43f2-137">From the toolbox, drag a **Buy_ReceiveAndSendReply** and a **Checkout_Receive** activity onto the **Sequential Service** activity.</span></span>
