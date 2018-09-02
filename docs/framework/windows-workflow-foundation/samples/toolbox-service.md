---
title: Servicio de cuadro de herramientas
ms.date: 03/30/2017
ms.assetid: 742212d0-445e-41ed-9739-9ee848ce7f1b
ms.openlocfilehash: 0b21f10c763f3f82591f947eb4cc48cf90f4ac79
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43406467"
---
# <a name="toolbox-service"></a><span data-ttu-id="e4b6e-102">Servicio de cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="e4b6e-102">Toolbox Service</span></span>
<span data-ttu-id="e4b6e-103">En este ejemplo se muestra cómo actualizar las actividades de Cuadro de herramientas de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] en función del contexto del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-103">This sample demonstrates how to update the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] Toolbox activities based on the context of the workflow.</span></span> <span data-ttu-id="e4b6e-104">El ejemplo contiene un flujo de trabajo que cambia el contenido del Cuadro de herramientas si se selecciona una actividad personalizada.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-104">The sample contains a workflow that changes the toolbox contents based on whether a custom activity is selected.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="e4b6e-105">Explicación</span><span class="sxs-lookup"><span data-stu-id="e4b6e-105">Discussion</span></span>  
 <span data-ttu-id="e4b6e-106">Durante la creación de flujo de trabajo, por lo general los clientes desean que su cuadro de herramientas sea contextual.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-106">During workflow authoring, customers generally want their Toolbox to be context sensitive.</span></span> <span data-ttu-id="e4b6e-107">Por ejemplo, puede que el usuario desee asegurarse de que el Cuadro de herramientas muestra algunas actividades adicionales cuando se agrega una actividad específica al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-107">For example, the user may want to ensure that the Toolbox shows a few additional activities when a specific activity is added to the workflow.</span></span> <span data-ttu-id="e4b6e-108">Si las actividades se quitan del flujo de trabajo, el Cuadro de herramientas debe reaccionar adecuadamente en función de los requisitos de dominio.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-108">If the activities are removed from the workflow, the toolbox should react appropriately based on the domain requirements.</span></span>  
  
 <span data-ttu-id="e4b6e-109">En un diseñador de flujo de trabajo hospedado en otro host, el usuario controla el control Toolbox y puede asegurarse de que, en función de los cambios de modelo del flujo de trabajo, el host activa los cambios adecuados en el control Toolbox.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-109">In a re-hosted workflow designer, you control the Toolbox control and can ensure that based on the Model changes in the workflow, the host triggers appropriate changes in the Toolbox control.</span></span> <span data-ttu-id="e4b6e-110">Sin embargo, en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], el usuario no controla el Cuadro de herramientas, por lo que se necesita una interfaz para modificar su contenido.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-110">However, in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], the toolbox is not controlled by the user and thus an interface is required to modify its contents.</span></span> <span data-ttu-id="e4b6e-111">`IActivityToolboxService` es esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-111">`IActivityToolboxService` is that interface.</span></span>  
  
 <span data-ttu-id="e4b6e-112">La API ofrece los cuatro métodos siguientes.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-112">The API provides the following four methods.</span></span>  
  
```  
public interface IActivityToolboxService   
{   
        void AddCategory(string categoryName);   
        void RemoveCategory(string categoryName);   
        void AddItem(string qualifiedTypeName, string categoryName);   
        void RemoveItem(string qualifiedTypeName, string categoryName);   
        IList<string> EnumCategories();   
        IList<string> EnumItems(string categoryName);   
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e4b6e-113">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4b6e-113">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e4b6e-114">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución WorkflowSimulator.sln.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-114">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WorkflowSimulator.sln solution file.</span></span>  
  
2.  <span data-ttu-id="e4b6e-115">Compile la solución presionando CTRL+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-115">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="e4b6e-116">Abra el archivo Workflow.xaml.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-116">Open the Workflow.xaml file.</span></span>  
  
4.  <span data-ttu-id="e4b6e-117">Agregar un **CustomActivity** arrastrando y colocándola en el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-117">Add a **CustomActivity** by dragging and dropping it from the toolbox.</span></span> <span data-ttu-id="e4b6e-118">Tenga en cuenta que llama una categoría de cuadro de herramientas adicional: **New WF Category** con una actividad **asignar**.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-118">Notice that an additional Toolbox category called: **New WF Category** with an additional activity **Assign**.</span></span>  
  
5.  <span data-ttu-id="e4b6e-119">Ahora anule la selección de la **CustomActivity** arrastrando otra actividad en ella.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-119">Now unselect the **CustomActivity** by dragging another activity into it.</span></span>  
  
6.  <span data-ttu-id="e4b6e-120">El elemento **asignar** en la categoría **New WF Category** ahora se quita del cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-120">The item **Assign** in the category **New WF Category** under Toolbox is now removed.</span></span> <span data-ttu-id="e4b6e-121">Además, como ya no hay más elementos en la categoría, esta también se quita.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-121">Also, because there are no more items left in the category, the category is removed as well.</span></span>  
  
7.  <span data-ttu-id="e4b6e-122">Seleccione el **CustomActivity** nuevo y la categoría y **asignar** actividad se vuelven a agregar.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-122">Select the **CustomActivity** again and the category and **Assign** activity is added back.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e4b6e-123">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e4b6e-124">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e4b6e-125">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e4b6e-126">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\IActivityToolboxService`
