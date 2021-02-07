---
description: Más información acerca de cómo programar el árbol de elementos de modelo
title: Programar el árbol de elementos de modelo
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: 8dfcab99bb5e32d202fe2bdc09d63d8b7da6e748
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741866"
---
# <a name="programming-model-item-tree"></a><span data-ttu-id="7a443-103">Programar el árbol de elementos de modelo</span><span class="sxs-lookup"><span data-stu-id="7a443-103">Programming Model Item Tree</span></span>

<span data-ttu-id="7a443-104">En este ejemplo se muestra cómo navegar por el <xref:System.Activities.Presentation.Model.ModelItem> árbol utilizando el enlace de datos declarativo de la vista de árbol Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="7a443-104">This sample demonstrates how to navigate the <xref:System.Activities.Presentation.Model.ModelItem> tree using declarative data binding from the Windows Presentation Foundation (WPF) Tree View.</span></span>

## <a name="sample-details"></a><span data-ttu-id="7a443-105">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a443-105">Sample Details</span></span>

 <span data-ttu-id="7a443-106">El <xref:System.Activities.Presentation.Model.ModelItem> árbol es la abstracción que usa la infraestructura de diseñador de flujo de trabajo de Windows para exponer los datos sobre la instancia subyacente que se está editando.</span><span class="sxs-lookup"><span data-stu-id="7a443-106">The <xref:System.Activities.Presentation.Model.ModelItem> tree is the abstraction that is used by the Windows Workflow Designer infrastructure to expose the data about the underlying instance being edited.</span></span> <span data-ttu-id="7a443-107">La ilustración siguiente es una representación de los distintos niveles de infraestructura dentro del Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7a443-107">The following illustration is a depiction of the various layers of infrastructure within the Workflow Designer.</span></span>

 ![Diagrama que muestra la arquitectura de Diseñador de flujo de trabajo.](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 <span data-ttu-id="7a443-109">Un objeto <xref:System.Activities.Presentation.Model.ModelItem> consta de un puntero al valor subyacente, así como de una colección de objetos <xref:System.Activities.Presentation.Model.ModelProperty>.</span><span class="sxs-lookup"><span data-stu-id="7a443-109">A <xref:System.Activities.Presentation.Model.ModelItem> consists of a pointer to the underlying value, as well as a collection of <xref:System.Activities.Presentation.Model.ModelProperty> objects.</span></span> <span data-ttu-id="7a443-110">Un objeto <xref:System.Activities.Presentation.Model.ModelProperty> a su vez consta de datos como el nombre y tipo de la propiedad, y un puntero al valor que, a su vez, es otro objeto <xref:System.Activities.Presentation.Model.ModelItem>.</span><span class="sxs-lookup"><span data-stu-id="7a443-110">A <xref:System.Activities.Presentation.Model.ModelProperty> object in turn, consists of data such as the name and type of the property and then a pointer to the value, which in turn, is another <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="7a443-111">Se utiliza un convertidor de valores para manipular algunos de los objetos <xref:System.Activities.Presentation.Model.ModelItem> que devuelve <xref:System.Activities.Presentation.Model.ModelProperty> para que aparezcan correctamente en la vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="7a443-111">A value converter is used to manipulate some of the <xref:System.Activities.Presentation.Model.ModelItem>s returned from a <xref:System.Activities.Presentation.Model.ModelProperty> to make them appear correctly in the tree view.</span></span> <span data-ttu-id="7a443-112">A continuación, el ejemplo muestra cómo programar de manera imperativa en el árbol <xref:System.Activities.Presentation.Model.ModelItem> utilizando la sintaxis imperativa, tal y como se puede ver en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7a443-112">The sample then demonstrates how to imperatively program against the <xref:System.Activities.Presentation.Model.ModelItem> tree using the imperative syntax, as seen in the following example.</span></span>

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="7a443-113">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a443-113">To use this sample</span></span>

1. <span data-ttu-id="7a443-114">Abra la solución ProgrammingModelItemTree. sln en Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="7a443-114">Open the ProgrammingModelItemTree.sln solution in Visual Studio 2010.</span></span>

2. <span data-ttu-id="7a443-115">Para compilar la solución, seleccione **compilar solución** en el menú **compilar** .</span><span class="sxs-lookup"><span data-stu-id="7a443-115">Build the solution by selecting **Build Solution** from the **Build** menu.</span></span>

3. <span data-ttu-id="7a443-116">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7a443-116">Press F5 to run the application.</span></span> <span data-ttu-id="7a443-117">A continuación, se muestra el formulario de WPF.</span><span class="sxs-lookup"><span data-stu-id="7a443-117">The WPF form is then displayed.</span></span>

4. <span data-ttu-id="7a443-118">Haga clic en el botón **cargar WF** para cargar <xref:System.Activities.Presentation.Model.ModelItem> y enlazarlo a la vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="7a443-118">Click the **Load WF** button to load the <xref:System.Activities.Presentation.Model.ModelItem> and bind it to the tree view.</span></span>

5. <span data-ttu-id="7a443-119">Al hacer clic en el botón **cambiar árbol de elementos de modelo** , se ejecuta el código anterior para agregar un elemento al árbol y establecer una propiedad.</span><span class="sxs-lookup"><span data-stu-id="7a443-119">Clicking the **Change Model Item Tree** button executes the preceding code to add an item into the tree and set a property.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a443-120">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="7a443-120">The samples may already be installed on your computer.</span></span> <span data-ttu-id="7a443-121">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="7a443-121">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="7a443-122">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="7a443-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7a443-123">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="7a443-123">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a><span data-ttu-id="7a443-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a443-124">See also</span></span>

- <xref:System.Windows.Data.IValueConverter>
