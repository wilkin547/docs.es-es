---
title: Programar el árbol de elementos de modelo
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: f14b140fdac95f3763cc5625841a725793876fa4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142698"
---
# <a name="programming-model-item-tree"></a><span data-ttu-id="ac030-102">Programar el árbol de elementos de modelo</span><span class="sxs-lookup"><span data-stu-id="ac030-102">Programming Model Item Tree</span></span>
<span data-ttu-id="ac030-103">En este ejemplo se <xref:System.Activities.Presentation.Model.ModelItem> muestra cómo navegar por el árbol mediante el enlace de datos declarativo desde la vista de árbol de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="ac030-103">This sample demonstrates how to navigate the <xref:System.Activities.Presentation.Model.ModelItem> tree using declarative data binding from the Windows Presentation Foundation (WPF) Tree View.</span></span>

## <a name="sample-details"></a><span data-ttu-id="ac030-104">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac030-104">Sample Details</span></span>
 <span data-ttu-id="ac030-105">El <xref:System.Activities.Presentation.Model.ModelItem> árbol es la abstracción que usa la infraestructura del Diseñador de flujo de trabajo de Windows para exponer los datos sobre la instancia subyacente que se está editando.</span><span class="sxs-lookup"><span data-stu-id="ac030-105">The <xref:System.Activities.Presentation.Model.ModelItem> tree is the abstraction that is used by the Windows Workflow Designer infrastructure to expose the data about the underlying instance being edited.</span></span> <span data-ttu-id="ac030-106">La siguiente ilustración es una representación de las distintas capas de infraestructura dentro del Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ac030-106">The following illustration is a depiction of the various layers of infrastructure within the Workflow Designer.</span></span>

 ![Diagrama que muestra la arquitectura del Diseñador de flujo de trabajo.](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 <span data-ttu-id="ac030-108">Un objeto <xref:System.Activities.Presentation.Model.ModelItem> consta de un puntero al valor subyacente, así como de una colección de objetos <xref:System.Activities.Presentation.Model.ModelProperty>.</span><span class="sxs-lookup"><span data-stu-id="ac030-108">A <xref:System.Activities.Presentation.Model.ModelItem> consists of a pointer to the underlying value, as well as a collection of <xref:System.Activities.Presentation.Model.ModelProperty> objects.</span></span> <span data-ttu-id="ac030-109">Un objeto <xref:System.Activities.Presentation.Model.ModelProperty> a su vez consta de datos como el nombre y tipo de la propiedad, y un puntero al valor que, a su vez, es otro objeto <xref:System.Activities.Presentation.Model.ModelItem>.</span><span class="sxs-lookup"><span data-stu-id="ac030-109">A <xref:System.Activities.Presentation.Model.ModelProperty> object in turn, consists of data such as the name and type of the property and then a pointer to the value, which in turn, is another <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="ac030-110">Se utiliza un convertidor de valores para manipular algunos de los objetos <xref:System.Activities.Presentation.Model.ModelItem> que devuelve <xref:System.Activities.Presentation.Model.ModelProperty> para que aparezcan correctamente en la vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="ac030-110">A value converter is used to manipulate some of the <xref:System.Activities.Presentation.Model.ModelItem>s returned from a <xref:System.Activities.Presentation.Model.ModelProperty> to make them appear correctly in the tree view.</span></span> <span data-ttu-id="ac030-111">A continuación, el ejemplo muestra cómo programar de manera imperativa en el árbol <xref:System.Activities.Presentation.Model.ModelItem> utilizando la sintaxis imperativa, tal y como se puede ver en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ac030-111">The sample then demonstrates how to imperatively program against the <xref:System.Activities.Presentation.Model.ModelItem> tree using the imperative syntax, as seen in the following example.</span></span>

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="ac030-112">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac030-112">To use this sample</span></span>

1. <span data-ttu-id="ac030-113">Abra la solución ProgrammingModelItemTree.sln en Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="ac030-113">Open the ProgrammingModelItemTree.sln solution in Visual Studio 2010.</span></span>

2. <span data-ttu-id="ac030-114">Compile la solución seleccionando **Compilar solución** en el menú **Compilar.**</span><span class="sxs-lookup"><span data-stu-id="ac030-114">Build the solution by selecting **Build Solution** from the **Build** menu.</span></span>

3. <span data-ttu-id="ac030-115">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ac030-115">Press F5 to run the application.</span></span> <span data-ttu-id="ac030-116">A continuación, se muestra el formulario WPFWPF.</span><span class="sxs-lookup"><span data-stu-id="ac030-116">The WPF form is then displayed.</span></span>

4. <span data-ttu-id="ac030-117">Haga clic en el <xref:System.Activities.Presentation.Model.ModelItem> botón Cargar **WF** para cargarlo y enlazarlo a la vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="ac030-117">Click the **Load WF** button to load the <xref:System.Activities.Presentation.Model.ModelItem> and bind it to the tree view.</span></span>

5. <span data-ttu-id="ac030-118">Al hacer clic en el botón Cambiar árbol de **elementos** del modelo se ejecuta el código anterior para agregar un elemento al árbol y establecer una propiedad.</span><span class="sxs-lookup"><span data-stu-id="ac030-118">Clicking the **Change Model Item Tree** button executes the preceding code to add an item into the tree and set a property.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac030-119">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ac030-119">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ac030-120">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ac030-120">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="ac030-121">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ac030-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ac030-122">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="ac030-122">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a><span data-ttu-id="ac030-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac030-123">See also</span></span>

- <xref:System.Windows.Data.IValueConverter>
