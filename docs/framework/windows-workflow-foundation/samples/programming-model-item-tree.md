---
title: Programar el árbol de elementos de modelo
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: 59c1f0c3722d6e68a9f629504f5012377dbacc5f
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2019
ms.locfileid: "67170071"
---
# <a name="programming-model-item-tree"></a><span data-ttu-id="f4cc1-102">Programar el árbol de elementos de modelo</span><span class="sxs-lookup"><span data-stu-id="f4cc1-102">Programming Model Item Tree</span></span>
<span data-ttu-id="f4cc1-103">Este ejemplo muestra cómo navegar por la <xref:System.Activities.Presentation.Model.ModelItem> árbol mediante enlace de datos declarativo de la vista de árbol de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="f4cc1-103">This sample demonstrates how to navigate the <xref:System.Activities.Presentation.Model.ModelItem> tree using declarative data binding from the Windows Presentation Foundation (WPF) Tree View.</span></span>

## <a name="sample-details"></a><span data-ttu-id="f4cc1-104">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4cc1-104">Sample Details</span></span>
 <span data-ttu-id="f4cc1-105">El árbol <xref:System.Activities.Presentation.Model.ModelItem> es la abstracción que usa la infraestructura de [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] para mostrar los datos sobre la instancia subyacente que se está editando.</span><span class="sxs-lookup"><span data-stu-id="f4cc1-105">The <xref:System.Activities.Presentation.Model.ModelItem> tree is the abstraction that is used by the [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] infrastructure to expose the data about the underlying instance being edited.</span></span> <span data-ttu-id="f4cc1-106">La siguiente ilustración describe los diferentes niveles de infraestructura dentro de [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4cc1-106">The following illustration is a depiction of the various layers of infrastructure within the [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span>

 ![Diagrama que muestra la arquitectura del Diseñador de flujo de trabajo.](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 <span data-ttu-id="f4cc1-108">Un objeto <xref:System.Activities.Presentation.Model.ModelItem> consta de un puntero al valor subyacente, así como de una colección de objetos <xref:System.Activities.Presentation.Model.ModelProperty>.</span><span class="sxs-lookup"><span data-stu-id="f4cc1-108">A <xref:System.Activities.Presentation.Model.ModelItem> consists of a pointer to the underlying value, as well as a collection of <xref:System.Activities.Presentation.Model.ModelProperty> objects.</span></span> <span data-ttu-id="f4cc1-109">Un objeto <xref:System.Activities.Presentation.Model.ModelProperty> a su vez consta de datos como el nombre y tipo de la propiedad, y un puntero al valor que, a su vez, es otro objeto <xref:System.Activities.Presentation.Model.ModelItem>.</span><span class="sxs-lookup"><span data-stu-id="f4cc1-109">A <xref:System.Activities.Presentation.Model.ModelProperty> object in turn, consists of data such as the name and type of the property and then a pointer to the value, which in turn, is another <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="f4cc1-110">Se utiliza un convertidor de valores para manipular algunos de los objetos <xref:System.Activities.Presentation.Model.ModelItem> que devuelve <xref:System.Activities.Presentation.Model.ModelProperty> para que aparezcan correctamente en la vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="f4cc1-110">A value converter is used to manipulate some of the <xref:System.Activities.Presentation.Model.ModelItem>s returned from a <xref:System.Activities.Presentation.Model.ModelProperty> to make them appear correctly in the tree view.</span></span> <span data-ttu-id="f4cc1-111">A continuación, el ejemplo muestra cómo programar de manera imperativa en el árbol <xref:System.Activities.Presentation.Model.ModelItem> utilizando la sintaxis imperativa, tal y como se puede ver en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f4cc1-111">The sample then demonstrates how to imperatively program against the <xref:System.Activities.Presentation.Model.ModelItem> tree using the imperative syntax, as seen in the following example.</span></span>

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="f4cc1-112">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4cc1-112">To use this sample</span></span>

1. <span data-ttu-id="f4cc1-113">Abra la solución ProgrammingModelItemTree.sln en Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="f4cc1-113">Open the ProgrammingModelItemTree.sln solution in Visual Studio 2010.</span></span>

2. <span data-ttu-id="f4cc1-114">Compile la solución seleccionando **compilar solución** desde el **compilar** menú.</span><span class="sxs-lookup"><span data-stu-id="f4cc1-114">Build the solution by selecting **Build Solution** from the **Build** menu.</span></span>

3. <span data-ttu-id="f4cc1-115">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4cc1-115">Press F5 to run the application.</span></span> <span data-ttu-id="f4cc1-116">A continuación, se muestra el formulario WPF.</span><span class="sxs-lookup"><span data-stu-id="f4cc1-116">The WPF form is then displayed.</span></span>

4. <span data-ttu-id="f4cc1-117">Haga clic en el **cargar WF** botón para cargar el <xref:System.Activities.Presentation.Model.ModelItem> y enlazarlo a la vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="f4cc1-117">Click the **Load WF** button to load the <xref:System.Activities.Presentation.Model.ModelItem> and bind it to the tree view.</span></span>

5. <span data-ttu-id="f4cc1-118">Al hacer clic en el **Change Model Item Tree** botón ejecuta el código anterior para agregar un elemento en el árbol y establecer una propiedad.</span><span class="sxs-lookup"><span data-stu-id="f4cc1-118">Clicking the **Change Model Item Tree** button executes the preceding code to add an item into the tree and set a property.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="f4cc1-119">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="f4cc1-119">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f4cc1-120">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="f4cc1-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f4cc1-121">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f4cc1-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f4cc1-122">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="f4cc1-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a><span data-ttu-id="f4cc1-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4cc1-123">See also</span></span>

- <xref:System.Windows.Data.IValueConverter>
