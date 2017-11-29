---
title: "Tutorial: Crear una aplicación extensible"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [.NET Framework], add-in pipeline
- host-side adapters for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], creating
- add-in-side adapter [.NET Framework]
- contracts for add-in pipelines [.NET Framework]
ms.assetid: 694a33c5-a040-450d-aed5-ac49fc88ce61
caps.latest.revision: "32"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6609f30844421f94965fbe05114db96ed8edbb31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-an-extensible-application"></a><span data-ttu-id="fa77a-102">Tutorial: Crear una aplicación extensible</span><span class="sxs-lookup"><span data-stu-id="fa77a-102">Walkthrough: Creating an Extensible Application</span></span>
<span data-ttu-id="fa77a-103">Este tutorial describe cómo crear una canalización para un complemento que realiza funciones de calculadora sencillo.</span><span class="sxs-lookup"><span data-stu-id="fa77a-103">This walkthrough describes how to create a pipeline for an add-in that performs simple calculator functions.</span></span> <span data-ttu-id="fa77a-104">No se muestra un escenario real; en su lugar, muestra la funcionalidad básica de una canalización y cómo un complemento puede proporcionar servicios para un host.</span><span class="sxs-lookup"><span data-stu-id="fa77a-104">It does not demonstrate a real-world scenario; rather, it demonstrates the basic functionality of a pipeline and how an add-in can provide services for a host.</span></span>  
  
 <span data-ttu-id="fa77a-105">En este tutorial se describe las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="fa77a-105">This walkthrough describes the following tasks:</span></span>  
  
-   <span data-ttu-id="fa77a-106">Crear una solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fa77a-106">Creating a Visual Studio solution.</span></span>  
  
-   <span data-ttu-id="fa77a-107">Crear la estructura de directorios de canalización.</span><span class="sxs-lookup"><span data-stu-id="fa77a-107">Creating the pipeline directory structure.</span></span>  
  
-   <span data-ttu-id="fa77a-108">Crear el contrato y vistas.</span><span class="sxs-lookup"><span data-stu-id="fa77a-108">Creating the contract and views.</span></span>  
  
-   <span data-ttu-id="fa77a-109">Crear el adaptador de conversión.</span><span class="sxs-lookup"><span data-stu-id="fa77a-109">Creating the add-in-side adapter.</span></span>  
  
-   <span data-ttu-id="fa77a-110">Crear el adaptador de host.</span><span class="sxs-lookup"><span data-stu-id="fa77a-110">Creating the host-side adapter.</span></span>  
  
-   <span data-ttu-id="fa77a-111">Crear el host.</span><span class="sxs-lookup"><span data-stu-id="fa77a-111">Creating the host.</span></span>  
  
-   <span data-ttu-id="fa77a-112">Crear el complemento.</span><span class="sxs-lookup"><span data-stu-id="fa77a-112">Creating the add-in.</span></span>  
  
-   <span data-ttu-id="fa77a-113">Implementar la canalización.</span><span class="sxs-lookup"><span data-stu-id="fa77a-113">Deploying the pipeline.</span></span>  
  
-   <span data-ttu-id="fa77a-114">Ejecutar la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="fa77a-114">Running the host application.</span></span>  
  
 <span data-ttu-id="fa77a-115">Esta canalización sólo pasa tipos serializables (<xref:System.Double> y <xref:System.String>), entre el host y el complemento.</span><span class="sxs-lookup"><span data-stu-id="fa77a-115">This pipeline passes only serializable types (<xref:System.Double> and <xref:System.String>), between the host and the add-in.</span></span> <span data-ttu-id="fa77a-116">Para obtener un ejemplo que muestra cómo pasar colecciones de tipos de datos complejos, vea [Tutorial: pasar colecciones entre Hosts y complementos](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5).</span><span class="sxs-lookup"><span data-stu-id="fa77a-116">For an example that shows how to pass collections of complex data types, see [Walkthrough: Passing Collections Between Hosts and Add-Ins](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5).</span></span>  
  
 <span data-ttu-id="fa77a-117">El contrato de esta canalización define un modelo de objetos de cuatro operaciones aritméticas: agregar, restar, multiplicar y dividir.</span><span class="sxs-lookup"><span data-stu-id="fa77a-117">The contract for this pipeline defines an object model of four arithmetic operations: add, subtract, multiply, and divide.</span></span> <span data-ttu-id="fa77a-118">El host proporciona el complemento con una ecuación para calcular, por ejemplo, 2 + 2, y el complemento devuelve el resultado al host.</span><span class="sxs-lookup"><span data-stu-id="fa77a-118">The host provides the add-in with an equation to calculate, such as 2 + 2, and the add-in returns the result to the host.</span></span>  
  
 <span data-ttu-id="fa77a-119">Versión 2 del complemento de calculadora proporciona otras posibilidades de cálculo y muestra el control de versiones.</span><span class="sxs-lookup"><span data-stu-id="fa77a-119">Version 2 of the calculator add-in provides more calculating possibilities and demonstrates versioning.</span></span> <span data-ttu-id="fa77a-120">Se describe en [Tutorial: habilitar la compatibilidad con versiones anteriores como los cambios de Host](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span><span class="sxs-lookup"><span data-stu-id="fa77a-120">It is described in [Walkthrough: Enabling Backward Compatibility as Your Host Changes](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fa77a-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fa77a-121">Prerequisites</span></span>  
 <span data-ttu-id="fa77a-122">Necesitas lo siguiente para poder llevar a cabo este tutorial:</span><span class="sxs-lookup"><span data-stu-id="fa77a-122">You need the following to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]<span data-ttu-id="fa77a-123">.</span><span class="sxs-lookup"><span data-stu-id="fa77a-123">.</span></span>  
  
## <a name="creating-a-visual-studio-solution"></a><span data-ttu-id="fa77a-124">Crear una solución de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fa77a-124">Creating a Visual Studio Solution</span></span>  
 <span data-ttu-id="fa77a-125">Usar una solución en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] que contenga los proyectos de los segmentos de canalización.</span><span class="sxs-lookup"><span data-stu-id="fa77a-125">Use a solution in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] to contain the projects of your pipeline segments.</span></span>  
  
#### <a name="to-create-the-pipeline-solution"></a><span data-ttu-id="fa77a-126">Para crear la solución de canalización</span><span class="sxs-lookup"><span data-stu-id="fa77a-126">To create the pipeline solution</span></span>  
  
1.  <span data-ttu-id="fa77a-127">En [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], cree un nuevo proyecto denominado `Calc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="fa77a-127">In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], create a new project named `Calc1Contract`.</span></span> <span data-ttu-id="fa77a-128">Basar en la **biblioteca de clases** plantilla.</span><span class="sxs-lookup"><span data-stu-id="fa77a-128">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="fa77a-129">Llame a la solución `CalculatorV1`.</span><span class="sxs-lookup"><span data-stu-id="fa77a-129">Name the solution `CalculatorV1`.</span></span>  
  
## <a name="creating-the-pipeline-directory-structure"></a><span data-ttu-id="fa77a-130">Crear la estructura de directorios de canalización</span><span class="sxs-lookup"><span data-stu-id="fa77a-130">Creating the Pipeline Directory Structure</span></span>  
 <span data-ttu-id="fa77a-131">El modelo de complementos requiere que los ensamblados de segmento de canalización se coloquen en una estructura de directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="fa77a-131">The add-in model requires the pipeline segment assemblies to be placed in a specified directory structure.</span></span> <span data-ttu-id="fa77a-132">Para obtener más información acerca de la estructura de canalización, consulte [requisitos del desarrollo de canalizaciones](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="fa77a-132">For more information about the pipeline structure, see [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
#### <a name="to-create-the-pipeline-directory-structure"></a><span data-ttu-id="fa77a-133">Para crear la estructura de directorios de canalización</span><span class="sxs-lookup"><span data-stu-id="fa77a-133">To create the pipeline directory structure</span></span>  
  
1.  <span data-ttu-id="fa77a-134">Crear una carpeta de la aplicación en cualquier lugar en el equipo.</span><span class="sxs-lookup"><span data-stu-id="fa77a-134">Create an application folder anywhere on your computer.</span></span>  
  
2.  <span data-ttu-id="fa77a-135">En esa carpeta, cree la siguiente estructura:</span><span class="sxs-lookup"><span data-stu-id="fa77a-135">In that folder, create the following structure:</span></span>  
  
    ```  
    Pipeline  
      AddIns  
        CalcV1  
        CalcV2  
      AddInSideAdapters  
      AddInViews  
      Contracts  
      HostSideAdapters  
    ```  
  
     <span data-ttu-id="fa77a-136">No es necesario poner la estructura de carpetas de la canalización en la carpeta de la aplicación; se hace aquí solo por conveniencia.</span><span class="sxs-lookup"><span data-stu-id="fa77a-136">It is not necessary to put the pipeline folder structure in your application folder; it is done here only for convenience.</span></span> <span data-ttu-id="fa77a-137">En el paso correspondiente, el tutorial, explica cómo cambiar el código si la estructura de carpetas de la canalización está en una ubicación diferente.</span><span class="sxs-lookup"><span data-stu-id="fa77a-137">At the appropriate step, the walkthrough explains how to change the code if the pipeline folder structure is in a different location.</span></span> <span data-ttu-id="fa77a-138">Vea la explicación de los requisitos de directorio de canalización en [requisitos del desarrollo de canalizaciones](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="fa77a-138">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fa77a-139">El `CalcV2` carpeta no se utiliza en este tutorial; es un marcador de posición para [Tutorial: habilitar la compatibilidad con versiones anteriores como los cambios de Host](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span><span class="sxs-lookup"><span data-stu-id="fa77a-139">The `CalcV2` folder is not used in this walkthrough; it is a placeholder for [Walkthrough: Enabling Backward Compatibility as Your Host Changes](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="creating-the-contract-and-views"></a><span data-ttu-id="fa77a-140">Crear el contrato y vistas</span><span class="sxs-lookup"><span data-stu-id="fa77a-140">Creating the Contract and Views</span></span>  
 <span data-ttu-id="fa77a-141">El segmento de contrato de esta canalización define la `ICalc1Contract` interfaz que define cuatro métodos: `add`, `subtract`, `multiply`, y `divide`.</span><span class="sxs-lookup"><span data-stu-id="fa77a-141">The contract segment for this pipeline defines the `ICalc1Contract` interface, which defines four methods: `add`, `subtract`, `multiply`, and `divide`.</span></span>  
  
#### <a name="to-create-the-contract"></a><span data-ttu-id="fa77a-142">Para crear el contrato</span><span class="sxs-lookup"><span data-stu-id="fa77a-142">To create the contract</span></span>  
  
1.  <span data-ttu-id="fa77a-143">En la solución de Visual Studio denominada `CalculatorV1`, abra el `Calc1Contract` proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa77a-143">In the Visual Studio solution named `CalculatorV1`, open the `Calc1Contract` project.</span></span>  
  
2.  <span data-ttu-id="fa77a-144">En **el Explorador de soluciones**, agregue referencias a los ensamblados siguientes a la `Calc1Contract` proyecto:</span><span class="sxs-lookup"><span data-stu-id="fa77a-144">In **Solution Explorer**, add references to the following assemblies to the `Calc1Contract` project:</span></span>  
  
     <span data-ttu-id="fa77a-145">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="fa77a-145">System.AddIn.Contract.dll</span></span>  
  
     <span data-ttu-id="fa77a-146">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="fa77a-146">System.AddIn.dll</span></span>  
  
3.  <span data-ttu-id="fa77a-147">En **el Explorador de soluciones**, excluya la clase predeterminada que se agrega al nuevo **biblioteca de clases** proyectos.</span><span class="sxs-lookup"><span data-stu-id="fa77a-147">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects.</span></span>  
  
4.  <span data-ttu-id="fa77a-148">En **el Explorador de soluciones**, agregar un nuevo elemento al proyecto, mediante el **interfaz** plantilla.</span><span class="sxs-lookup"><span data-stu-id="fa77a-148">In **Solution Explorer**, add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="fa77a-149">En el **Agregar nuevo elemento** cuadro de diálogo, el nombre de la interfaz `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="fa77a-149">In the **Add New Item** dialog box, name the interface `ICalc1Contract`.</span></span>  
  
5.  <span data-ttu-id="fa77a-150">En el archivo de interfaz, agregue referencias de espacio de nombres a <xref:System.AddIn.Contract> y <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="fa77a-150">In the interface file, add namespace references to <xref:System.AddIn.Contract> and <xref:System.AddIn.Pipeline>.</span></span>  
  
6.  <span data-ttu-id="fa77a-151">Utilice el código siguiente para completar este segmento de contrato.</span><span class="sxs-lookup"><span data-stu-id="fa77a-151">Use the following code to complete this contract segment.</span></span> <span data-ttu-id="fa77a-152">Tenga en cuenta que esta interfaz debe tener la <xref:System.AddIn.Pipeline.AddInContractAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="fa77a-152">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInContractAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  <span data-ttu-id="fa77a-153">Si lo desea, compile la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fa77a-153">Optionally, build the Visual Studio solution.</span></span> <span data-ttu-id="fa77a-154">La solución no se puede ejecutar hasta que el procedimiento final, pero compilarlas después de cada procedimiento, se garantiza que cada proyecto es corregir.</span><span class="sxs-lookup"><span data-stu-id="fa77a-154">The solution cannot be run until the final procedure, but building it after each procedure ensures that each project is correct.</span></span>  
  
 <span data-ttu-id="fa77a-155">Como la vista del complemento y el host de la vista de complemento normalmente tienen el mismo código, especialmente en la primera versión de un complemento, puede crear fácilmente las vistas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="fa77a-155">Because the add-in view and the host view of the add-in usually have the same code, especially in the first version of an add-in, you can easily create the views at the same time.</span></span> <span data-ttu-id="fa77a-156">Se diferencian en sólo un factor: la vista de complemento requiere el <xref:System.AddIn.Pipeline.AddInBaseAttribute> atributo, mientras que la vista de host del complemento no requiere ningún atributo.</span><span class="sxs-lookup"><span data-stu-id="fa77a-156">They differ by only one factor: the add-in view requires the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute, while the host view of the add-in does not require any attributes.</span></span>  
  
#### <a name="to-create-the-add-in-view"></a><span data-ttu-id="fa77a-157">Para crear la vista de complemento</span><span class="sxs-lookup"><span data-stu-id="fa77a-157">To create the add-in view</span></span>  
  
1.  <span data-ttu-id="fa77a-158">Agregue un nuevo proyecto denominado `Calc1AddInView` a la `CalculatorV1` solución.</span><span class="sxs-lookup"><span data-stu-id="fa77a-158">Add a new project named `Calc1AddInView` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="fa77a-159">Basar en la **biblioteca de clases** plantilla.</span><span class="sxs-lookup"><span data-stu-id="fa77a-159">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="fa77a-160">En **el Explorador de soluciones**, agregue una referencia a System.AddIn.dll para el `Calc1AddInView` proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa77a-160">In **Solution Explorer**, add a reference to System.AddIn.dll to the `Calc1AddInView` project.</span></span>  
  
3.  <span data-ttu-id="fa77a-161">En **el Explorador de soluciones**, excluya la clase predeterminada que se agrega al nuevo **biblioteca de clases** proyectos y agregar un nuevo elemento al proyecto, mediante el **interfaz** plantilla.</span><span class="sxs-lookup"><span data-stu-id="fa77a-161">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="fa77a-162">En el **Agregar nuevo elemento** cuadro de diálogo, el nombre de la interfaz `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="fa77a-162">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
4.  <span data-ttu-id="fa77a-163">En el archivo de interfaz, agregue una referencia de espacio de nombres para <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="fa77a-163">In the interface file, add a namespace reference to <xref:System.AddIn.Pipeline>.</span></span>  
  
5.  <span data-ttu-id="fa77a-164">Utilice el código siguiente para completar esta vista de complemento.</span><span class="sxs-lookup"><span data-stu-id="fa77a-164">Use the following code to complete this add-in view.</span></span> <span data-ttu-id="fa77a-165">Tenga en cuenta que esta interfaz debe tener la <xref:System.AddIn.Pipeline.AddInBaseAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="fa77a-165">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  <span data-ttu-id="fa77a-166">Si lo desea, compile la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fa77a-166">Optionally, build the Visual Studio solution.</span></span>  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a><span data-ttu-id="fa77a-167">Para crear la vista de host del complemento</span><span class="sxs-lookup"><span data-stu-id="fa77a-167">To create the host view of the add-in</span></span>  
  
1.  <span data-ttu-id="fa77a-168">Agregue un nuevo proyecto denominado `Calc1HVA` a la `CalculatorV1` solución.</span><span class="sxs-lookup"><span data-stu-id="fa77a-168">Add a new project named `Calc1HVA` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="fa77a-169">Basar en la **biblioteca de clases** plantilla.</span><span class="sxs-lookup"><span data-stu-id="fa77a-169">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="fa77a-170">En **el Explorador de soluciones**, excluya la clase predeterminada que se agrega al nuevo **biblioteca de clases** proyectos y agregar un nuevo elemento al proyecto, mediante el **interfaz** plantilla.</span><span class="sxs-lookup"><span data-stu-id="fa77a-170">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="fa77a-171">En el **Agregar nuevo elemento** cuadro de diálogo, el nombre de la interfaz `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="fa77a-171">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
3.  <span data-ttu-id="fa77a-172">En el archivo de interfaz, use el código siguiente para completar la vista de host del complemento.</span><span class="sxs-lookup"><span data-stu-id="fa77a-172">In the interface file, use the following code to complete the host view of the add-in.</span></span>  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  <span data-ttu-id="fa77a-173">Si lo desea, compile la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fa77a-173">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in-side-adapter"></a><span data-ttu-id="fa77a-174">Crear el adaptador de conversión</span><span class="sxs-lookup"><span data-stu-id="fa77a-174">Creating the Add-in-side Adapter</span></span>  
 <span data-ttu-id="fa77a-175">Este adaptador de conversión se compone de un adaptador de vista a contrato.</span><span class="sxs-lookup"><span data-stu-id="fa77a-175">This add-in-side adapter consists of one view-to-contract adapter.</span></span> <span data-ttu-id="fa77a-176">Este segmento de la canalización convierte a los tipos de la vista del complemento al contrato.</span><span class="sxs-lookup"><span data-stu-id="fa77a-176">This pipeline segment converts the types from the add-in view to the contract.</span></span>  
  
 <span data-ttu-id="fa77a-177">En esta canalización, el complemento proporciona un servicio al host y los tipos de fluyan desde el complemento al host.</span><span class="sxs-lookup"><span data-stu-id="fa77a-177">In this pipeline, the add-in provides a service to the host, and the types flow from the add-in to the host.</span></span> <span data-ttu-id="fa77a-178">Dado que ningún tipo fluye desde el host para el complemento, no es necesario incluir un adaptador de contrato a vista en el lado del complemento de esta canalización.</span><span class="sxs-lookup"><span data-stu-id="fa77a-178">Because no types flow from the host to the add-in, you do not have to include a contract-to-view adapter on the add-in side of this pipeline.</span></span>  
  
#### <a name="to-create-the-add-in-side-adapter"></a><span data-ttu-id="fa77a-179">Para crear el adaptador de conversión</span><span class="sxs-lookup"><span data-stu-id="fa77a-179">To create the add-in-side adapter</span></span>  
  
1.  <span data-ttu-id="fa77a-180">Agregue un nuevo proyecto denominado `Calc1AddInSideAdapter` a la `CalculatorV1` solución.</span><span class="sxs-lookup"><span data-stu-id="fa77a-180">Add a new project named `Calc1AddInSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="fa77a-181">Basar en la **biblioteca de clases** plantilla.</span><span class="sxs-lookup"><span data-stu-id="fa77a-181">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="fa77a-182">En **el Explorador de soluciones**, agregue referencias a los ensamblados siguientes a la `Calc1AddInSideAdapter` proyecto:</span><span class="sxs-lookup"><span data-stu-id="fa77a-182">In **Solution Explorer**, add references to the following assemblies to the `Calc1AddInSideAdapter` project:</span></span>  
  
     <span data-ttu-id="fa77a-183">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="fa77a-183">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="fa77a-184">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="fa77a-184">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="fa77a-185">Agregar referencias de proyecto a los proyectos para los segmentos de canalización adyacentes:</span><span class="sxs-lookup"><span data-stu-id="fa77a-185">Add project references to the projects for the adjacent pipeline segments:</span></span>  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  <span data-ttu-id="fa77a-186">Seleccione cada referencia de proyecto y en **propiedades** establecer **Copy Local** a **False**.</span><span class="sxs-lookup"><span data-stu-id="fa77a-186">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="fa77a-187">En Visual Basic, utilice la **referencias** ficha de **propiedades del proyecto** establecer **Copy Local** a **False** para las dos referencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa77a-187">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="fa77a-188">Cambiar el nombre de la clase del proyecto predeterminado `CalculatorViewToContractAddInSideAdapter`.</span><span class="sxs-lookup"><span data-stu-id="fa77a-188">Rename the project's default class `CalculatorViewToContractAddInSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="fa77a-189">En el archivo de clase, agregue referencias de espacio de nombres a <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="fa77a-189">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="fa77a-190">En el archivo de clase, agregue referencias de espacio de nombres para los segmentos adyacentes: `CalcAddInViews` y `CalculatorContracts`.</span><span class="sxs-lookup"><span data-stu-id="fa77a-190">In the class file, add namespace references for the adjacent segments: `CalcAddInViews` and `CalculatorContracts`.</span></span> <span data-ttu-id="fa77a-191">(En Visual Basic, estas referencias de espacio de nombres son `Calc1AddInView.CalcAddInViews` y `Calc1Contract.CalculatorContracts`, a menos que haya desactivado los espacios de nombres de forma predeterminada en los proyectos de Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="fa77a-191">(In Visual Basic, these namespace references are `Calc1AddInView.CalcAddInViews` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="fa77a-192">Aplicar el <xref:System.AddIn.Pipeline.AddInAdapterAttribute> atribuir a la `CalculatorViewToContractAddInSideAdapter` (clase), que se identifique como el adaptador de conversión.</span><span class="sxs-lookup"><span data-stu-id="fa77a-192">Apply the <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attribute to the `CalculatorViewToContractAddInSideAdapter` class, to identify it as the add-in-side adapter.</span></span>  
  
9. <span data-ttu-id="fa77a-193">Realizar la `CalculatorViewToContractAddInSideAdapter` heredan de la clase <xref:System.AddIn.Pipeline.ContractBase>, lo que proporciona una implementación predeterminada de la <xref:System.AddIn.Contract.IContract> interfaz e implementar la interfaz de contrato para la canalización, `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="fa77a-193">Make the `CalculatorViewToContractAddInSideAdapter` class inherit <xref:System.AddIn.Pipeline.ContractBase>, which provides a default implementation of the <xref:System.AddIn.Contract.IContract> interface, and implement the contract interface for the pipeline, `ICalc1Contract`.</span></span>  
  
10. <span data-ttu-id="fa77a-194">Agregue un constructor público que acepta un `ICalculator`, lo almacena en caché en un campo privado y llama al constructor de clase base.</span><span class="sxs-lookup"><span data-stu-id="fa77a-194">Add a public constructor that accepts an `ICalculator`, caches it in a private field, and calls the base class constructor.</span></span>  
  
11. <span data-ttu-id="fa77a-195">Para implementar los miembros de `ICalc1Contract`, basta con llamar a los miembros correspondientes de la `ICalculator` instancia que se pasa al constructor y devolver los resultados.</span><span class="sxs-lookup"><span data-stu-id="fa77a-195">To implement the members of `ICalc1Contract`, simply call the corresponding members of the `ICalculator` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="fa77a-196">Este modo adapta la vista (`ICalculator`) al contrato (`ICalc1Contract`).</span><span class="sxs-lookup"><span data-stu-id="fa77a-196">This adapts the view (`ICalculator`) to the contract (`ICalc1Contract`).</span></span>  
  
     <span data-ttu-id="fa77a-197">El código siguiente muestra el adaptador de conversión completado.</span><span class="sxs-lookup"><span data-stu-id="fa77a-197">The following code shows the completed add-in-side adapter.</span></span>  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. <span data-ttu-id="fa77a-198">Si lo desea, compile la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fa77a-198">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host-side-adapter"></a><span data-ttu-id="fa77a-199">Crear el adaptador de Host</span><span class="sxs-lookup"><span data-stu-id="fa77a-199">Creating the Host-side Adapter</span></span>  
 <span data-ttu-id="fa77a-200">Este adaptador del host se compone de un adaptador de contrato a vista.</span><span class="sxs-lookup"><span data-stu-id="fa77a-200">This host-side adapter consists of one contract-to-view adapter.</span></span> <span data-ttu-id="fa77a-201">Este segmento adapta el contrato a la vista de host del complemento.</span><span class="sxs-lookup"><span data-stu-id="fa77a-201">This segment adapts the contract to the host view of the add-in.</span></span>  
  
 <span data-ttu-id="fa77a-202">Esta canalización, el complemento proporciona un servicio para el host y el flujo de tipos desde el complemento en el host.</span><span class="sxs-lookup"><span data-stu-id="fa77a-202">In this pipeline, the add-in provides a service to the host and the types flow from the add-in to the host.</span></span> <span data-ttu-id="fa77a-203">Dado que ningún tipo fluye desde el host para el complemento, es necesario que incluir un adaptador de vista a contrato.</span><span class="sxs-lookup"><span data-stu-id="fa77a-203">Because no types flow from the host to the add-in, you do not have to include a view-to-contract adapter.</span></span>  
  
 <span data-ttu-id="fa77a-204">Para implementar la administración de la duración, use un <xref:System.AddIn.Pipeline.ContractHandle> objeto que se va a asociar un token de duración al contrato.</span><span class="sxs-lookup"><span data-stu-id="fa77a-204">To implement lifetime management, use a <xref:System.AddIn.Pipeline.ContractHandle> object to attach a lifetime token to the contract.</span></span> <span data-ttu-id="fa77a-205">Debe mantener una referencia a este identificador en orden para que funcione la administración de vigencia.</span><span class="sxs-lookup"><span data-stu-id="fa77a-205">You must keep a reference to this handle in order for lifetime management to work.</span></span> <span data-ttu-id="fa77a-206">Después de que se aplica el token, es necesaria ninguna programación adicional porque el sistema del complemento puede desechar los objetos cuando ya no se usan y que estén disponibles para la recolección.</span><span class="sxs-lookup"><span data-stu-id="fa77a-206">After the token is applied, no additional programming is required because the add-in system can dispose of objects when they are no longer being used and make them available for garbage collection.</span></span> <span data-ttu-id="fa77a-207">Para más información, consulte [Administración de la duración](http://msdn.microsoft.com/en-us/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span><span class="sxs-lookup"><span data-stu-id="fa77a-207">For more information, see [Lifetime Management](http://msdn.microsoft.com/en-us/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span></span>  
  
#### <a name="to-create-the-host-side-adapter"></a><span data-ttu-id="fa77a-208">Para crear el adaptador del lado del host</span><span class="sxs-lookup"><span data-stu-id="fa77a-208">To create the host-side adapter</span></span>  
  
1.  <span data-ttu-id="fa77a-209">Agregue un nuevo proyecto denominado `Calc1HostSideAdapter` a la `CalculatorV1` solución.</span><span class="sxs-lookup"><span data-stu-id="fa77a-209">Add a new project named `Calc1HostSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="fa77a-210">Basar en la **biblioteca de clases** plantilla.</span><span class="sxs-lookup"><span data-stu-id="fa77a-210">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="fa77a-211">En **el Explorador de soluciones**, agregue referencias a los ensamblados siguientes a la `Calc1HostSideAdapter` proyecto:</span><span class="sxs-lookup"><span data-stu-id="fa77a-211">In **Solution Explorer**, add references to the following assemblies to the `Calc1HostSideAdapter` project:</span></span>  
  
     <span data-ttu-id="fa77a-212">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="fa77a-212">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="fa77a-213">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="fa77a-213">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="fa77a-214">Agregar referencias de proyecto a los proyectos en los segmentos adyacentes:</span><span class="sxs-lookup"><span data-stu-id="fa77a-214">Add project references to the projects for the adjacent segments:</span></span>  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  <span data-ttu-id="fa77a-215">Seleccione cada referencia de proyecto y en **propiedades** establecer **Copy Local** a **False**.</span><span class="sxs-lookup"><span data-stu-id="fa77a-215">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="fa77a-216">En Visual Basic, utilice la **referencias** ficha de **propiedades del proyecto** establecer **Copy Local** a **False** para las dos referencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa77a-216">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="fa77a-217">Cambiar el nombre de la clase del proyecto predeterminado `CalculatorContractToViewHostSideAdapter`.</span><span class="sxs-lookup"><span data-stu-id="fa77a-217">Rename the project's default class `CalculatorContractToViewHostSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="fa77a-218">En el archivo de clase, agregue referencias de espacio de nombres a <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="fa77a-218">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="fa77a-219">En el archivo de clase, agregue referencias de espacio de nombres para los segmentos adyacentes: `CalcHVAs` y `CalculatorContracts`.</span><span class="sxs-lookup"><span data-stu-id="fa77a-219">In the class file, add namespace references for the adjacent segments: `CalcHVAs` and `CalculatorContracts`.</span></span> <span data-ttu-id="fa77a-220">(En Visual Basic, estas referencias de espacio de nombres son `Calc1HVA.CalcHVAs` y `Calc1Contract.CalculatorContracts`, a menos que haya desactivado los espacios de nombres de forma predeterminada en los proyectos de Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="fa77a-220">(In Visual Basic, these namespace references are `Calc1HVA.CalcHVAs` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="fa77a-221">Aplicar el <xref:System.AddIn.Pipeline.HostAdapterAttribute> atribuir a la `CalculatorContractToViewHostSideAdapter` (clase), que se identifique como el segmento del adaptador del lado del host.</span><span class="sxs-lookup"><span data-stu-id="fa77a-221">Apply the <xref:System.AddIn.Pipeline.HostAdapterAttribute> attribute to the `CalculatorContractToViewHostSideAdapter` class, to identify it as the host-side adapter segment.</span></span>  
  
9. <span data-ttu-id="fa77a-222">Realizar la `CalculatorContractToViewHostSideAdapter` clase implementa la interfaz que representa la vista de host del complemento: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="fa77a-222">Make the `CalculatorContractToViewHostSideAdapter` class implement the interface that represents the host view of the add-in: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).</span></span>  
  
10. <span data-ttu-id="fa77a-223">Agregue un constructor público que acepte el tipo de contrato de la canalización, `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="fa77a-223">Add a public constructor that accepts the pipeline contract type, `ICalc1Contract`.</span></span> <span data-ttu-id="fa77a-224">El constructor debe almacenar en caché la referencia al contrato.</span><span class="sxs-lookup"><span data-stu-id="fa77a-224">The constructor must cache the reference to the contract.</span></span> <span data-ttu-id="fa77a-225">También debe crear y almacenar en caché un nuevo <xref:System.AddIn.Pipeline.ContractHandle> para el contrato, para administrar la vigencia del complemento.</span><span class="sxs-lookup"><span data-stu-id="fa77a-225">It must also create and cache a new <xref:System.AddIn.Pipeline.ContractHandle> for the contract, to manage the lifetime of the add-in.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="fa77a-226">El <xref:System.AddIn.Pipeline.ContractHandle> es fundamental para la administración de la duración.</span><span class="sxs-lookup"><span data-stu-id="fa77a-226">The <xref:System.AddIn.Pipeline.ContractHandle> is critical to lifetime management.</span></span> <span data-ttu-id="fa77a-227">Si no puede mantener una referencia a la <xref:System.AddIn.Pipeline.ContractHandle> objeto, recopilación de elementos no utilizados lo reclamará y la canalización se cerrará cuando el programa no lo espera.</span><span class="sxs-lookup"><span data-stu-id="fa77a-227">If you fail to keep a reference to the <xref:System.AddIn.Pipeline.ContractHandle> object, garbage collection will reclaim it, and the pipeline will shut down when your program does not expect it.</span></span> <span data-ttu-id="fa77a-228">Esto puede conducir a errores que son difíciles de diagnosticar, como <xref:System.AppDomainUnloadedException>.</span><span class="sxs-lookup"><span data-stu-id="fa77a-228">This can lead to errors that are difficult to diagnose, such as <xref:System.AppDomainUnloadedException>.</span></span> <span data-ttu-id="fa77a-229">Cierre es una etapa normal en la vida de una canalización, así que no hay ningún medio para que el código de administración de vigencia detectar que esta condición es un error.</span><span class="sxs-lookup"><span data-stu-id="fa77a-229">Shutdown is a normal stage in the life of a pipeline, so there is no way for the lifetime management code to detect that this condition is an error.</span></span>  
  
11. <span data-ttu-id="fa77a-230">Para implementar los miembros de `ICalculator`, basta con llamar a los miembros correspondientes de la `ICalc1Contract` instancia que se pasa al constructor y devolver los resultados.</span><span class="sxs-lookup"><span data-stu-id="fa77a-230">To implement the members of `ICalculator`, simply call the corresponding members of the `ICalc1Contract` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="fa77a-231">Este modo adapta el contrato (`ICalc1Contract`) a la vista (`ICalculator`).</span><span class="sxs-lookup"><span data-stu-id="fa77a-231">This adapts the contract (`ICalc1Contract`) to the view (`ICalculator`).</span></span>  
  
     <span data-ttu-id="fa77a-232">El código siguiente muestra el adaptador del host completado.</span><span class="sxs-lookup"><span data-stu-id="fa77a-232">The following code shows the completed host-side adapter.</span></span>  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. <span data-ttu-id="fa77a-233">Si lo desea, compile la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fa77a-233">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host"></a><span data-ttu-id="fa77a-234">Crear el Host</span><span class="sxs-lookup"><span data-stu-id="fa77a-234">Creating the Host</span></span>  
 <span data-ttu-id="fa77a-235">Una aplicación host interactúa con el complemento a través de la vista de host del complemento.</span><span class="sxs-lookup"><span data-stu-id="fa77a-235">A host application interacts with the add-in through the host view of the add-in.</span></span> <span data-ttu-id="fa77a-236">Usa el complemento de detección y activación métodos proporcionados por el <xref:System.AddIn.Hosting.AddInStore> y <xref:System.AddIn.Hosting.AddInToken> clases para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa77a-236">It uses add-in discovery and activation methods provided by the <xref:System.AddIn.Hosting.AddInStore> and <xref:System.AddIn.Hosting.AddInToken> classes to do the following:</span></span>  
  
-   <span data-ttu-id="fa77a-237">Actualizar la caché de información de canalización y el complemento.</span><span class="sxs-lookup"><span data-stu-id="fa77a-237">Update the cache of pipeline and add-in information.</span></span>  
  
-   <span data-ttu-id="fa77a-238">Buscar complementos del tipo de vista del host, `ICalculator`, bajo el directorio de raíz de la canalización especificada.</span><span class="sxs-lookup"><span data-stu-id="fa77a-238">Find add-ins of the host view type, `ICalculator`, under the specified pipeline root directory.</span></span>  
  
-   <span data-ttu-id="fa77a-239">Solicitar al usuario que especifique que complemento a usar.</span><span class="sxs-lookup"><span data-stu-id="fa77a-239">Prompt the user to specify which add-in to use.</span></span>  
  
-   <span data-ttu-id="fa77a-240">Activar el complemento seleccionado en un nuevo dominio de aplicación con un nivel de confianza de seguridad especificado.</span><span class="sxs-lookup"><span data-stu-id="fa77a-240">Activate the selected add-in in a new application domain with a specified security trust level.</span></span>  
  
-   <span data-ttu-id="fa77a-241">Ejecutar personalizado `RunCalculator` método, que llama a los métodos del complemento según lo especificado por la vista de host del complemento.</span><span class="sxs-lookup"><span data-stu-id="fa77a-241">Run the custom `RunCalculator` method, which calls the add-in's methods as specified by the host view of the add-in.</span></span>  
  
#### <a name="to-create-the-host"></a><span data-ttu-id="fa77a-242">Para crear el host</span><span class="sxs-lookup"><span data-stu-id="fa77a-242">To create the host</span></span>  
  
1.  <span data-ttu-id="fa77a-243">Agregue un nuevo proyecto denominado `Calc1Host` a la `CalculatorV1` solución.</span><span class="sxs-lookup"><span data-stu-id="fa77a-243">Add a new project named `Calc1Host` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="fa77a-244">Basar en la **aplicación de consola** plantilla.</span><span class="sxs-lookup"><span data-stu-id="fa77a-244">Base it on the **Console Application** template.</span></span>  
  
2.  <span data-ttu-id="fa77a-245">En **el Explorador de soluciones**, agregue una referencia al ensamblado System.AddIn.dll para el `Calc1Host` proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa77a-245">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the `Calc1Host` project.</span></span>  
  
3.  <span data-ttu-id="fa77a-246">Agregue una referencia de proyecto a la `Calc1HVA` proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa77a-246">Add a project reference to the `Calc1HVA` project.</span></span> <span data-ttu-id="fa77a-247">Seleccione la referencia de proyecto y en **propiedades** establecer **Copy Local** a **False**.</span><span class="sxs-lookup"><span data-stu-id="fa77a-247">Select the project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="fa77a-248">En Visual Basic, utilice la **referencias** ficha de **propiedades del proyecto** establecer **Copy Local** a **False**.</span><span class="sxs-lookup"><span data-stu-id="fa77a-248">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False**.</span></span>  
  
4.  <span data-ttu-id="fa77a-249">Cambiar el nombre del archivo de clase (módulo en Visual Basic) `MathHost1`.</span><span class="sxs-lookup"><span data-stu-id="fa77a-249">Rename the class file (module in Visual Basic) `MathHost1`.</span></span>  
  
5.  <span data-ttu-id="fa77a-250">En Visual Basic, utilice la **aplicación** pestaña de la **propiedades del proyecto** cuadro de diálogo para establecer **objeto de inicio** a **Sub Main**.</span><span class="sxs-lookup"><span data-stu-id="fa77a-250">In Visual Basic, use the **Application** tab of the **Project Properties** dialog box to set **Startup object** to **Sub Main**.</span></span>  
  
6.  <span data-ttu-id="fa77a-251">En el archivo de clase o módulo, agregue una referencia de espacio de nombres a <xref:System.AddIn.Hosting>.</span><span class="sxs-lookup"><span data-stu-id="fa77a-251">In the class or module file, add a namespace reference to <xref:System.AddIn.Hosting>.</span></span>  
  
7.  <span data-ttu-id="fa77a-252">En el archivo de clase o módulo, agregue una referencia de espacio de nombres para la vista de host del complemento: `CalcHVAs`.</span><span class="sxs-lookup"><span data-stu-id="fa77a-252">In the class or module file, add a namespace reference for the host view of the add-in: `CalcHVAs`.</span></span> <span data-ttu-id="fa77a-253">(En Visual Basic, esta referencia de espacio de nombres es `Calc1HVA.CalcHVAs`, a menos que haya desactivado los espacios de nombres de forma predeterminada en los proyectos de Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="fa77a-253">(In Visual Basic, this namespace reference is `Calc1HVA.CalcHVAs`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="fa77a-254">En **el Explorador de soluciones**, seleccione la solución y desde el **proyecto** menú elija **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fa77a-254">In **Solution Explorer**, select the solution and from the **Project** menu choose **Properties**.</span></span> <span data-ttu-id="fa77a-255">En el **páginas de propiedades de solución** cuadro de diálogo, establezca la **proyecto de inicio único** sea este proyecto de aplicación de host.</span><span class="sxs-lookup"><span data-stu-id="fa77a-255">In the **Solution Property Pages** dialog box, set the **Single Startup Project** to be this host application project.</span></span>  
  
9. <span data-ttu-id="fa77a-256">En el archivo de clase o módulo, use el <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> método para actualizar la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="fa77a-256">In the class or module file, use the <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> method to update the cache.</span></span> <span data-ttu-id="fa77a-257">Utilice la <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> método para obtener una colección de tokens y utilice la <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> método para activar un complemento.</span><span class="sxs-lookup"><span data-stu-id="fa77a-257">Use the <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> method to get a collection of tokens, and use the <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> method to activate an add-in.</span></span>  
  
     <span data-ttu-id="fa77a-258">El código siguiente muestra la aplicación host completada.</span><span class="sxs-lookup"><span data-stu-id="fa77a-258">The following code shows the completed host application.</span></span>  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="fa77a-259">Este código supone que la estructura de carpetas de la canalización se encuentra en la carpeta de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fa77a-259">This code assumes that the pipeline folder structure is located in the application folder.</span></span> <span data-ttu-id="fa77a-260">Si se encuentra en otra parte, cambie la línea de código que establece la `addInRoot` variable, por lo que la variable contiene la ruta de acceso a la estructura de directorios de canalización.</span><span class="sxs-lookup"><span data-stu-id="fa77a-260">If you located it elsewhere, change the line of code that sets the `addInRoot` variable, so that the variable contains the path to your pipeline directory structure.</span></span>  
  
     <span data-ttu-id="fa77a-261">El código usa un `ChooseCalculator` método para enumerar los tokens y solicitar al usuario que elija un complemento.</span><span class="sxs-lookup"><span data-stu-id="fa77a-261">The code uses a `ChooseCalculator` method to list the tokens and to prompt the user to choose an add-in.</span></span> <span data-ttu-id="fa77a-262">El `RunCalculator` método pide al usuario que escriba expresiones matemáticas simples, analiza las expresiones utilizando la `Parser` clase y muestra los resultados devuelven por el complemento.</span><span class="sxs-lookup"><span data-stu-id="fa77a-262">The `RunCalculator` method prompts the user for simple math expressions, parses the expressions using the `Parser` class, and displays the results returned by the add-in.</span></span>  
  
10. <span data-ttu-id="fa77a-263">Si lo desea, compile la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fa77a-263">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in"></a><span data-ttu-id="fa77a-264">Crear el complemento</span><span class="sxs-lookup"><span data-stu-id="fa77a-264">Creating the Add-In</span></span>  
 <span data-ttu-id="fa77a-265">Un complemento implementa los métodos especificados por la vista del complemento.</span><span class="sxs-lookup"><span data-stu-id="fa77a-265">An add-in implements the methods specified by the add-in view.</span></span> <span data-ttu-id="fa77a-266">Este complemento implementa el `Add`, `Subtract`, `Multiply`, y `Divide` las operaciones y devuelve los resultados al host.</span><span class="sxs-lookup"><span data-stu-id="fa77a-266">This add-in implements the `Add`, `Subtract`, `Multiply`, and `Divide` operations and returns the results to the host.</span></span>  
  
#### <a name="to-create-the-add-in"></a><span data-ttu-id="fa77a-267">Para crear el complemento</span><span class="sxs-lookup"><span data-stu-id="fa77a-267">To create the add-in</span></span>  
  
1.  <span data-ttu-id="fa77a-268">Agregue un nuevo proyecto denominado `AddInCalcV1` a la `CalculatorV1` solución.</span><span class="sxs-lookup"><span data-stu-id="fa77a-268">Add a new project named `AddInCalcV1` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="fa77a-269">Basar en la **biblioteca de clases** plantilla.</span><span class="sxs-lookup"><span data-stu-id="fa77a-269">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="fa77a-270">En **el Explorador de soluciones**, agregue una referencia del ensamblado System.AddIn.dll al proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa77a-270">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the project.</span></span>  
  
3.  <span data-ttu-id="fa77a-271">Agregue una referencia de proyecto a la `Calc1AddInView` proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa77a-271">Add a project reference to the `Calc1AddInView` project.</span></span> <span data-ttu-id="fa77a-272">Seleccione la referencia de proyecto y en **propiedades**, establezca **Copy Local** a **False**.</span><span class="sxs-lookup"><span data-stu-id="fa77a-272">Select the project reference, and in **Properties**, set **Copy Local** to **False**.</span></span> <span data-ttu-id="fa77a-273">En Visual Basic, utilice la **referencias** ficha de **propiedades del proyecto** establecer **Copy Local** a **False** para la referencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa77a-273">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the project reference.</span></span>  
  
4.  <span data-ttu-id="fa77a-274">Cambiar el nombre de la clase `AddInCalcV1`.</span><span class="sxs-lookup"><span data-stu-id="fa77a-274">Rename the class `AddInCalcV1`.</span></span>  
  
5.  <span data-ttu-id="fa77a-275">En el archivo de clase, agregue una referencia de espacio de nombres a <xref:System.AddIn> y el segmento de vista del complemento: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="fa77a-275">In the class file, add a namespace reference to <xref:System.AddIn> and the add-in view segment: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).</span></span>  
  
6.  <span data-ttu-id="fa77a-276">Aplicar el <xref:System.AddIn.AddInAttribute> atribuir a la `AddInCalcV1` (clase), para identificar la clase como un complemento.</span><span class="sxs-lookup"><span data-stu-id="fa77a-276">Apply the <xref:System.AddIn.AddInAttribute> attribute to the `AddInCalcV1` class, to identify the class as an add-in.</span></span>  
  
7.  <span data-ttu-id="fa77a-277">Realizar la `AddInCalcV1` clase implementa la interfaz que representa la vista del complemento: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="fa77a-277">Make the `AddInCalcV1` class implement the interface that represents the add-in view: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).</span></span>  
  
8.  <span data-ttu-id="fa77a-278">Implemente los miembros de `ICalculator` devolviendo los resultados de los cálculos adecuados.</span><span class="sxs-lookup"><span data-stu-id="fa77a-278">Implement the members of `ICalculator` by returning the results of the appropriate calculations.</span></span>  
  
     <span data-ttu-id="fa77a-279">El código siguiente muestra el complemento completado.</span><span class="sxs-lookup"><span data-stu-id="fa77a-279">The following code shows the completed add-in.</span></span>  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. <span data-ttu-id="fa77a-280">Si lo desea, compile la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fa77a-280">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="deploying-the-pipeline"></a><span data-ttu-id="fa77a-281">Implementar la canalización</span><span class="sxs-lookup"><span data-stu-id="fa77a-281">Deploying the Pipeline</span></span>  
 <span data-ttu-id="fa77a-282">Ahora está listo para compilar e implementar los segmentos de complemento en la estructura de directorios de canalización requerida.</span><span class="sxs-lookup"><span data-stu-id="fa77a-282">You are now ready to build and deploy the add-in segments to the required pipeline directory structure.</span></span>  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a><span data-ttu-id="fa77a-283">Para implementar los segmentos en la canalización</span><span class="sxs-lookup"><span data-stu-id="fa77a-283">To deploy the segments to the pipeline</span></span>  
  
1.  <span data-ttu-id="fa77a-284">En cada proyecto de la solución, utilice la **generar** ficha de **propiedades del proyecto** (la **compilar** pestaña en Visual Basic) para establecer el valor de la **ruta de acceso de salida**  (la **ruta de acceso de salida de compilación** en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="fa77a-284">For each project in the solution, use the **Build** tab of **Project Properties** (the **Compile** tab in Visual Basic) to set the value of the **Output path** (the **Build output path** in Visual Basic).</span></span> <span data-ttu-id="fa77a-285">Si con el nombre de la carpeta de la aplicación `MyApp`, por ejemplo, podrían generar los proyectos en las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="fa77a-285">If you named your application folder `MyApp`, for example, your projects would build into the following folders:</span></span>  
  
    |<span data-ttu-id="fa77a-286">Proyecto</span><span class="sxs-lookup"><span data-stu-id="fa77a-286">Project</span></span>|<span data-ttu-id="fa77a-287">Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="fa77a-287">Path</span></span>|  
    |-------------|----------|  
    |<span data-ttu-id="fa77a-288">AddInCalcV1</span><span class="sxs-lookup"><span data-stu-id="fa77a-288">AddInCalcV1</span></span>|<span data-ttu-id="fa77a-289">MyApp\Pipeline\AddIns\CalcV1</span><span class="sxs-lookup"><span data-stu-id="fa77a-289">MyApp\Pipeline\AddIns\CalcV1</span></span>|  
    |<span data-ttu-id="fa77a-290">Calc1AddInSideAdapter</span><span class="sxs-lookup"><span data-stu-id="fa77a-290">Calc1AddInSideAdapter</span></span>|<span data-ttu-id="fa77a-291">MyApp\Pipeline\AddInSideAdapters</span><span class="sxs-lookup"><span data-stu-id="fa77a-291">MyApp\Pipeline\AddInSideAdapters</span></span>|  
    |<span data-ttu-id="fa77a-292">Calc1AddInView</span><span class="sxs-lookup"><span data-stu-id="fa77a-292">Calc1AddInView</span></span>|<span data-ttu-id="fa77a-293">MyApp\Pipeline\AddInViews</span><span class="sxs-lookup"><span data-stu-id="fa77a-293">MyApp\Pipeline\AddInViews</span></span>|  
    |<span data-ttu-id="fa77a-294">Calc1Contract</span><span class="sxs-lookup"><span data-stu-id="fa77a-294">Calc1Contract</span></span>|<span data-ttu-id="fa77a-295">MyApp\Pipeline\Contracts</span><span class="sxs-lookup"><span data-stu-id="fa77a-295">MyApp\Pipeline\Contracts</span></span>|  
    |<span data-ttu-id="fa77a-296">Calc1Host</span><span class="sxs-lookup"><span data-stu-id="fa77a-296">Calc1Host</span></span>|<span data-ttu-id="fa77a-297">MyApp</span><span class="sxs-lookup"><span data-stu-id="fa77a-297">MyApp</span></span>|  
    |<span data-ttu-id="fa77a-298">Calc1HostSideAdapter</span><span class="sxs-lookup"><span data-stu-id="fa77a-298">Calc1HostSideAdapter</span></span>|<span data-ttu-id="fa77a-299">MyApp\Pipeline\HostSideAdapters</span><span class="sxs-lookup"><span data-stu-id="fa77a-299">MyApp\Pipeline\HostSideAdapters</span></span>|  
    |<span data-ttu-id="fa77a-300">Calc1HVA</span><span class="sxs-lookup"><span data-stu-id="fa77a-300">Calc1HVA</span></span>|<span data-ttu-id="fa77a-301">MyApp</span><span class="sxs-lookup"><span data-stu-id="fa77a-301">MyApp</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="fa77a-302">Si ha decidido poner la estructura de carpetas de la canalización en una ubicación distinta de la carpeta de la aplicación, debe modificar las rutas de acceso que se muestra en la tabla en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="fa77a-302">If you decided to put your pipeline folder structure in a location other than your application folder, you must modify the paths shown in the table accordingly.</span></span> <span data-ttu-id="fa77a-303">Vea la explicación de los requisitos de directorio de canalización en [requisitos del desarrollo de canalizaciones](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="fa77a-303">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
2.  <span data-ttu-id="fa77a-304">Compile la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fa77a-304">Build the Visual Studio solution.</span></span>  
  
3.  <span data-ttu-id="fa77a-305">Compruebe los directorios de la canalización y la aplicación para asegurarse de que los ensamblados se copiaron en los directorios correctos y que se han instalado ninguna copia adicional de los ensamblados en carpetas equivocadas.</span><span class="sxs-lookup"><span data-stu-id="fa77a-305">Check the application and pipeline directories to ensure that the assemblies were copied to the correct directories and that no extra copies of assemblies were installed in the wrong folders.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fa77a-306">Si no ha cambiado **Copy Local** a **False** para el `Calc1AddInView` proyecto referencia en el `AddInCalcV1` proyecto, problemas de contexto de cargador impedirá que el complemento se encuentra.</span><span class="sxs-lookup"><span data-stu-id="fa77a-306">If you did not change **Copy Local** to **False** for the `Calc1AddInView` project reference in the `AddInCalcV1` project, loader context problems will prevent the add-in from being located.</span></span>  
  
     <span data-ttu-id="fa77a-307">Para obtener información acerca de la implementación a la canalización, consulte [requisitos del desarrollo de canalizaciones](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="fa77a-307">For information about deploying to the pipeline, see [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
## <a name="running-the-host-application"></a><span data-ttu-id="fa77a-308">Ejecutar la aplicación de Host</span><span class="sxs-lookup"><span data-stu-id="fa77a-308">Running the Host Application</span></span>  
 <span data-ttu-id="fa77a-309">Ahora está listo para ejecutar el host e interactuar con el complemento.</span><span class="sxs-lookup"><span data-stu-id="fa77a-309">You are now ready to run the host and interact with the add-in.</span></span>  
  
#### <a name="to-run-the-host-application"></a><span data-ttu-id="fa77a-310">Para ejecutar la aplicación de host</span><span class="sxs-lookup"><span data-stu-id="fa77a-310">To run the host application</span></span>  
  
1.  <span data-ttu-id="fa77a-311">En el símbolo del sistema, vaya al directorio de la aplicación y ejecute la aplicación host, `Calc1Host.exe`.</span><span class="sxs-lookup"><span data-stu-id="fa77a-311">At the command prompt, go to the application directory and run the host application, `Calc1Host.exe`.</span></span>  
  
2.  <span data-ttu-id="fa77a-312">El host busca todos los complementos disponibles de su tipo y se le pedirá que seleccione un complemento.</span><span class="sxs-lookup"><span data-stu-id="fa77a-312">The host finds all available add-ins of its type and prompts you to select an add-in.</span></span> <span data-ttu-id="fa77a-313">Escriba **1** para el complemento solo está disponible.</span><span class="sxs-lookup"><span data-stu-id="fa77a-313">Enter **1** for the only available add-in.</span></span>  
  
3.  <span data-ttu-id="fa77a-314">Escriba una ecuación para la Calculadora, como **2 + 2**.</span><span class="sxs-lookup"><span data-stu-id="fa77a-314">Enter an equation for the calculator, such as **2 + 2**.</span></span> <span data-ttu-id="fa77a-315">Debe haber espacios entre los números y el operador.</span><span class="sxs-lookup"><span data-stu-id="fa77a-315">There must be spaces between the numbers and the operator.</span></span>  
  
4.  <span data-ttu-id="fa77a-316">Tipo de **salir** y presione la **ENTRAR** tecla para cerrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fa77a-316">Type **exit** and press the **Enter** key to close the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa77a-317">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa77a-317">See Also</span></span>  
 [<span data-ttu-id="fa77a-318">Tutorial: Habilitar la compatibilidad con versiones anteriores como los cambios de Host</span><span class="sxs-lookup"><span data-stu-id="fa77a-318">Walkthrough: Enabling Backward Compatibility as Your Host Changes</span></span>](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
 [<span data-ttu-id="fa77a-319">Tutorial: Pasar colecciones entre Hosts y complementos</span><span class="sxs-lookup"><span data-stu-id="fa77a-319">Walkthrough: Passing Collections Between Hosts and Add-Ins</span></span>](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5)  
 [<span data-ttu-id="fa77a-320">Requisitos del desarrollo de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="fa77a-320">Pipeline Development Requirements</span></span>](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
 [<span data-ttu-id="fa77a-321">Contratos, vistas y adaptadores</span><span class="sxs-lookup"><span data-stu-id="fa77a-321">Contracts, Views, and Adapters</span></span>](http://msdn.microsoft.com/en-us/a6460173-9507-4b87-8c07-d4ee245d715c)  
 [<span data-ttu-id="fa77a-322">Pipeline Development</span><span class="sxs-lookup"><span data-stu-id="fa77a-322">Pipeline Development</span></span>](../../../docs/framework/add-ins/pipeline-development.md)
