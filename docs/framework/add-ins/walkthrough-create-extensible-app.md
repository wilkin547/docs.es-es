---
title: 'Tutorial: Crear una aplicación Extensible'
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63780583d035d6fab6b3a79424857b82a910ef09
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155082"
---
# <a name="walkthrough-creating-an-extensible-application"></a><span data-ttu-id="31c99-102">Tutorial: Crear una aplicación Extensible</span><span class="sxs-lookup"><span data-stu-id="31c99-102">Walkthrough: Creating an Extensible Application</span></span>
<span data-ttu-id="31c99-103">Este tutorial describe cómo crear una canalización para un complemento que realiza funciones de la calculadora simple.</span><span class="sxs-lookup"><span data-stu-id="31c99-103">This walkthrough describes how to create a pipeline for an add-in that performs simple calculator functions.</span></span> <span data-ttu-id="31c99-104">No se muestra un escenario real; en su lugar, muestra la funcionalidad básica de una canalización y cómo un complemento puede proporcionar servicios para un host.</span><span class="sxs-lookup"><span data-stu-id="31c99-104">It does not demonstrate a real-world scenario; rather, it demonstrates the basic functionality of a pipeline and how an add-in can provide services for a host.</span></span>  
  
 <span data-ttu-id="31c99-105">En este tutorial se describe las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="31c99-105">This walkthrough describes the following tasks:</span></span>  
  
-   <span data-ttu-id="31c99-106">Creación de una solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31c99-106">Creating a Visual Studio solution.</span></span>  
  
-   <span data-ttu-id="31c99-107">Creación de la estructura de directorios de la canalización.</span><span class="sxs-lookup"><span data-stu-id="31c99-107">Creating the pipeline directory structure.</span></span>  
  
-   <span data-ttu-id="31c99-108">Crear el contrato y vistas.</span><span class="sxs-lookup"><span data-stu-id="31c99-108">Creating the contract and views.</span></span>  
  
-   <span data-ttu-id="31c99-109">Crear el adaptador de conversión.</span><span class="sxs-lookup"><span data-stu-id="31c99-109">Creating the add-in-side adapter.</span></span>  
  
-   <span data-ttu-id="31c99-110">Crear el adaptador del host.</span><span class="sxs-lookup"><span data-stu-id="31c99-110">Creating the host-side adapter.</span></span>  
  
-   <span data-ttu-id="31c99-111">Crear el host.</span><span class="sxs-lookup"><span data-stu-id="31c99-111">Creating the host.</span></span>  
  
-   <span data-ttu-id="31c99-112">Crear el complemento.</span><span class="sxs-lookup"><span data-stu-id="31c99-112">Creating the add-in.</span></span>  
  
-   <span data-ttu-id="31c99-113">Implementar la canalización.</span><span class="sxs-lookup"><span data-stu-id="31c99-113">Deploying the pipeline.</span></span>  
  
-   <span data-ttu-id="31c99-114">Ejecutar la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="31c99-114">Running the host application.</span></span>  
  
 <span data-ttu-id="31c99-115">Esta canalización sólo pasa tipos serializables (<xref:System.Double> y <xref:System.String>), entre el host y el complemento.</span><span class="sxs-lookup"><span data-stu-id="31c99-115">This pipeline passes only serializable types (<xref:System.Double> and <xref:System.String>), between the host and the add-in.</span></span> <span data-ttu-id="31c99-116">Para obtener un ejemplo que muestra cómo pasar colecciones de tipos de datos complejos, vea [Tutorial: Pasar colecciones entre Hosts y complementos](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5).</span><span class="sxs-lookup"><span data-stu-id="31c99-116">For an example that shows how to pass collections of complex data types, see [Walkthrough: Passing Collections Between Hosts and Add-Ins](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5).</span></span>  
  
 <span data-ttu-id="31c99-117">El contrato de esta canalización define un modelo de objetos de cuatro operaciones aritméticas: agregar, restar, multiplicar y dividir.</span><span class="sxs-lookup"><span data-stu-id="31c99-117">The contract for this pipeline defines an object model of four arithmetic operations: add, subtract, multiply, and divide.</span></span> <span data-ttu-id="31c99-118">El host proporciona el complemento con una ecuación para calcular, por ejemplo, 2 + 2, y el complemento devuelve el resultado al host.</span><span class="sxs-lookup"><span data-stu-id="31c99-118">The host provides the add-in with an equation to calculate, such as 2 + 2, and the add-in returns the result to the host.</span></span>  
  
 <span data-ttu-id="31c99-119">Versión 2 del complemento de calculadora proporciona otras posibilidades de cálculo y muestra el control de versiones.</span><span class="sxs-lookup"><span data-stu-id="31c99-119">Version 2 of the calculator add-in provides more calculating possibilities and demonstrates versioning.</span></span> <span data-ttu-id="31c99-120">Se describe en [Tutorial: Habilita la compatibilidad con versiones anteriores como los cambios de Host](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span><span class="sxs-lookup"><span data-stu-id="31c99-120">It is described in [Walkthrough: Enabling Backward Compatibility as Your Host Changes](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="31c99-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="31c99-121">Prerequisites</span></span>  
 <span data-ttu-id="31c99-122">Necesitas lo siguiente para poder llevar a cabo este tutorial:</span><span class="sxs-lookup"><span data-stu-id="31c99-122">You need the following to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="31c99-123">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31c99-123">Visual Studio.</span></span>  
  
## <a name="creating-a-visual-studio-solution"></a><span data-ttu-id="31c99-124">Creación de una solución de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="31c99-124">Creating a Visual Studio Solution</span></span>  
 <span data-ttu-id="31c99-125">Utilice una solución de Visual Studio que contenga los proyectos de los segmentos de canalización.</span><span class="sxs-lookup"><span data-stu-id="31c99-125">Use a solution in Visual Studio to contain the projects of your pipeline segments.</span></span>  
  
#### <a name="to-create-the-pipeline-solution"></a><span data-ttu-id="31c99-126">Para crear la solución de canalización</span><span class="sxs-lookup"><span data-stu-id="31c99-126">To create the pipeline solution</span></span>  
  
1.  <span data-ttu-id="31c99-127">En Visual Studio, cree un nuevo proyecto denominado `Calc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="31c99-127">In Visual Studio, create a new project named `Calc1Contract`.</span></span> <span data-ttu-id="31c99-128">Basarlo en el **biblioteca de clases** plantilla.</span><span class="sxs-lookup"><span data-stu-id="31c99-128">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="31c99-129">Asigne a la solución el nombre `CalculatorV1`.</span><span class="sxs-lookup"><span data-stu-id="31c99-129">Name the solution `CalculatorV1`.</span></span>  
  
## <a name="creating-the-pipeline-directory-structure"></a><span data-ttu-id="31c99-130">Creación de la estructura de directorios de canalización</span><span class="sxs-lookup"><span data-stu-id="31c99-130">Creating the Pipeline Directory Structure</span></span>  
 <span data-ttu-id="31c99-131">El modelo del complemento requiere que los ensamblados de segmento de canalización se coloquen en una estructura de directorios especificado.</span><span class="sxs-lookup"><span data-stu-id="31c99-131">The add-in model requires the pipeline segment assemblies to be placed in a specified directory structure.</span></span> <span data-ttu-id="31c99-132">Para obtener más información acerca de la estructura de la canalización, consulte [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="31c99-132">For more information about the pipeline structure, see [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
#### <a name="to-create-the-pipeline-directory-structure"></a><span data-ttu-id="31c99-133">Para crear la estructura de directorios de canalización</span><span class="sxs-lookup"><span data-stu-id="31c99-133">To create the pipeline directory structure</span></span>  
  
1.  <span data-ttu-id="31c99-134">Cree una carpeta de la aplicación en cualquier lugar en el equipo.</span><span class="sxs-lookup"><span data-stu-id="31c99-134">Create an application folder anywhere on your computer.</span></span>  
  
2.  <span data-ttu-id="31c99-135">En esa carpeta, cree la siguiente estructura:</span><span class="sxs-lookup"><span data-stu-id="31c99-135">In that folder, create the following structure:</span></span>  
  
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
  
     <span data-ttu-id="31c99-136">No es necesario poner la estructura de carpetas de la canalización en la carpeta de aplicación; se hace aquí solo por comodidad.</span><span class="sxs-lookup"><span data-stu-id="31c99-136">It is not necessary to put the pipeline folder structure in your application folder; it is done here only for convenience.</span></span> <span data-ttu-id="31c99-137">En el paso correspondiente, el tutorial explica cómo cambiar el código si la estructura de carpetas de la canalización está en una ubicación diferente.</span><span class="sxs-lookup"><span data-stu-id="31c99-137">At the appropriate step, the walkthrough explains how to change the code if the pipeline folder structure is in a different location.</span></span> <span data-ttu-id="31c99-138">Vea la explicación de los requisitos de directorio de canalización en [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="31c99-138">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31c99-139">El `CalcV2` carpeta no se usa en este tutorial; es un marcador de posición [Tutorial: Habilita la compatibilidad con versiones anteriores como los cambios de Host](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span><span class="sxs-lookup"><span data-stu-id="31c99-139">The `CalcV2` folder is not used in this walkthrough; it is a placeholder for [Walkthrough: Enabling Backward Compatibility as Your Host Changes](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="creating-the-contract-and-views"></a><span data-ttu-id="31c99-140">Crear el contrato y vistas</span><span class="sxs-lookup"><span data-stu-id="31c99-140">Creating the Contract and Views</span></span>  
 <span data-ttu-id="31c99-141">El segmento de contrato de esta canalización define la `ICalc1Contract` interfaz, que define cuatro métodos: `add`, `subtract`, `multiply`, y `divide`.</span><span class="sxs-lookup"><span data-stu-id="31c99-141">The contract segment for this pipeline defines the `ICalc1Contract` interface, which defines four methods: `add`, `subtract`, `multiply`, and `divide`.</span></span>  
  
#### <a name="to-create-the-contract"></a><span data-ttu-id="31c99-142">Para crear el contrato</span><span class="sxs-lookup"><span data-stu-id="31c99-142">To create the contract</span></span>  
  
1.  <span data-ttu-id="31c99-143">En la solución de Visual Studio denominada `CalculatorV1`, abra el `Calc1Contract` proyecto.</span><span class="sxs-lookup"><span data-stu-id="31c99-143">In the Visual Studio solution named `CalculatorV1`, open the `Calc1Contract` project.</span></span>  
  
2.  <span data-ttu-id="31c99-144">En **el Explorador de soluciones**, agregue referencias a los siguientes ensamblados a los `Calc1Contract` proyecto:</span><span class="sxs-lookup"><span data-stu-id="31c99-144">In **Solution Explorer**, add references to the following assemblies to the `Calc1Contract` project:</span></span>  
  
     <span data-ttu-id="31c99-145">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="31c99-145">System.AddIn.Contract.dll</span></span>  
  
     <span data-ttu-id="31c99-146">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="31c99-146">System.AddIn.dll</span></span>  
  
3.  <span data-ttu-id="31c99-147">En **el Explorador de soluciones**, excluya la clase predeterminada que se agrega al nuevo **biblioteca de clases** proyectos.</span><span class="sxs-lookup"><span data-stu-id="31c99-147">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects.</span></span>  
  
4.  <span data-ttu-id="31c99-148">En **el Explorador de soluciones**, agregar un nuevo elemento al proyecto, mediante el **interfaz** plantilla.</span><span class="sxs-lookup"><span data-stu-id="31c99-148">In **Solution Explorer**, add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="31c99-149">En el **Agregar nuevo elemento** cuadro de diálogo, el nombre de la interfaz `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="31c99-149">In the **Add New Item** dialog box, name the interface `ICalc1Contract`.</span></span>  
  
5.  <span data-ttu-id="31c99-150">En el archivo de interfaz, agregue referencias de espacio de nombres a <xref:System.AddIn.Contract> y <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="31c99-150">In the interface file, add namespace references to <xref:System.AddIn.Contract> and <xref:System.AddIn.Pipeline>.</span></span>  
  
6.  <span data-ttu-id="31c99-151">Utilice el código siguiente para completar este segmento de contrato.</span><span class="sxs-lookup"><span data-stu-id="31c99-151">Use the following code to complete this contract segment.</span></span> <span data-ttu-id="31c99-152">Tenga en cuenta que esta interfaz debe tener el <xref:System.AddIn.Pipeline.AddInContractAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="31c99-152">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInContractAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  <span data-ttu-id="31c99-153">Si lo desea, compile la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31c99-153">Optionally, build the Visual Studio solution.</span></span> <span data-ttu-id="31c99-154">La solución no se puede ejecutar hasta que corrija el procedimiento final, pero compila después de cada procedimiento garantiza que cada proyecto.</span><span class="sxs-lookup"><span data-stu-id="31c99-154">The solution cannot be run until the final procedure, but building it after each procedure ensures that each project is correct.</span></span>  
  
 <span data-ttu-id="31c99-155">Como la vista de complemento y el host de la vista de complemento suelen tener el mismo código, especialmente en la primera versión de un complemento, puede crear fácilmente las vistas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="31c99-155">Because the add-in view and the host view of the add-in usually have the same code, especially in the first version of an add-in, you can easily create the views at the same time.</span></span> <span data-ttu-id="31c99-156">Se diferencian en un solo factor: la vista de complemento requiere el <xref:System.AddIn.Pipeline.AddInBaseAttribute> atributo, mientras que la vista host del complemento no requiere ningún atributo.</span><span class="sxs-lookup"><span data-stu-id="31c99-156">They differ by only one factor: the add-in view requires the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute, while the host view of the add-in does not require any attributes.</span></span>  
  
#### <a name="to-create-the-add-in-view"></a><span data-ttu-id="31c99-157">Para crear la vista de complemento</span><span class="sxs-lookup"><span data-stu-id="31c99-157">To create the add-in view</span></span>  
  
1.  <span data-ttu-id="31c99-158">Agregue un nuevo proyecto denominado `Calc1AddInView` a la `CalculatorV1` solución.</span><span class="sxs-lookup"><span data-stu-id="31c99-158">Add a new project named `Calc1AddInView` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="31c99-159">Basarlo en el **biblioteca de clases** plantilla.</span><span class="sxs-lookup"><span data-stu-id="31c99-159">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="31c99-160">En **el Explorador de soluciones**, agregue una referencia a System.AddIn.dll a la `Calc1AddInView` proyecto.</span><span class="sxs-lookup"><span data-stu-id="31c99-160">In **Solution Explorer**, add a reference to System.AddIn.dll to the `Calc1AddInView` project.</span></span>  
  
3.  <span data-ttu-id="31c99-161">En **el Explorador de soluciones**, excluya la clase predeterminada que se agrega al nuevo **biblioteca de clases** proyectos y agregar un nuevo elemento al proyecto, mediante el **interfaz** plantilla.</span><span class="sxs-lookup"><span data-stu-id="31c99-161">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="31c99-162">En el **Agregar nuevo elemento** cuadro de diálogo, el nombre de la interfaz `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="31c99-162">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
4.  <span data-ttu-id="31c99-163">En el archivo de interfaz, agregue una referencia de espacio de nombres a <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="31c99-163">In the interface file, add a namespace reference to <xref:System.AddIn.Pipeline>.</span></span>  
  
5.  <span data-ttu-id="31c99-164">Utilice el código siguiente para completar esta vista de complemento.</span><span class="sxs-lookup"><span data-stu-id="31c99-164">Use the following code to complete this add-in view.</span></span> <span data-ttu-id="31c99-165">Tenga en cuenta que esta interfaz debe tener el <xref:System.AddIn.Pipeline.AddInBaseAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="31c99-165">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  <span data-ttu-id="31c99-166">Si lo desea, compile la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31c99-166">Optionally, build the Visual Studio solution.</span></span>  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a><span data-ttu-id="31c99-167">Para crear la vista de host del complemento:</span><span class="sxs-lookup"><span data-stu-id="31c99-167">To create the host view of the add-in</span></span>  
  
1.  <span data-ttu-id="31c99-168">Agregue un nuevo proyecto denominado `Calc1HVA` a la `CalculatorV1` solución.</span><span class="sxs-lookup"><span data-stu-id="31c99-168">Add a new project named `Calc1HVA` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="31c99-169">Basarlo en el **biblioteca de clases** plantilla.</span><span class="sxs-lookup"><span data-stu-id="31c99-169">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="31c99-170">En **el Explorador de soluciones**, excluya la clase predeterminada que se agrega al nuevo **biblioteca de clases** proyectos y agregar un nuevo elemento al proyecto, mediante el **interfaz** plantilla.</span><span class="sxs-lookup"><span data-stu-id="31c99-170">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="31c99-171">En el **Agregar nuevo elemento** cuadro de diálogo, el nombre de la interfaz `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="31c99-171">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
3.  <span data-ttu-id="31c99-172">En el archivo de interfaz, utilice el código siguiente para completar la vista host del complemento.</span><span class="sxs-lookup"><span data-stu-id="31c99-172">In the interface file, use the following code to complete the host view of the add-in.</span></span>  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  <span data-ttu-id="31c99-173">Si lo desea, compile la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31c99-173">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in-side-adapter"></a><span data-ttu-id="31c99-174">Crear el adaptador de conversión</span><span class="sxs-lookup"><span data-stu-id="31c99-174">Creating the Add-in-side Adapter</span></span>  
 <span data-ttu-id="31c99-175">Este adaptador de conversión consta de un adaptador de vista a contrato.</span><span class="sxs-lookup"><span data-stu-id="31c99-175">This add-in-side adapter consists of one view-to-contract adapter.</span></span> <span data-ttu-id="31c99-176">Este segmento de canalización convierte a los tipos de la vista de complemento, el contrato.</span><span class="sxs-lookup"><span data-stu-id="31c99-176">This pipeline segment converts the types from the add-in view to the contract.</span></span>  
  
 <span data-ttu-id="31c99-177">En esta canalización, el complemento proporciona un servicio al host y los tipos que fluyen desde el complemento al host.</span><span class="sxs-lookup"><span data-stu-id="31c99-177">In this pipeline, the add-in provides a service to the host, and the types flow from the add-in to the host.</span></span> <span data-ttu-id="31c99-178">Dado que no hay tipos fluyen desde el host para el complemento, no es necesario incluir un adaptador de contrato a vista en el lado del complemento de esta canalización.</span><span class="sxs-lookup"><span data-stu-id="31c99-178">Because no types flow from the host to the add-in, you do not have to include a contract-to-view adapter on the add-in side of this pipeline.</span></span>  
  
#### <a name="to-create-the-add-in-side-adapter"></a><span data-ttu-id="31c99-179">Para crear el adaptador de conversión</span><span class="sxs-lookup"><span data-stu-id="31c99-179">To create the add-in-side adapter</span></span>  
  
1.  <span data-ttu-id="31c99-180">Agregue un nuevo proyecto denominado `Calc1AddInSideAdapter` a la `CalculatorV1` solución.</span><span class="sxs-lookup"><span data-stu-id="31c99-180">Add a new project named `Calc1AddInSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="31c99-181">Basarlo en el **biblioteca de clases** plantilla.</span><span class="sxs-lookup"><span data-stu-id="31c99-181">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="31c99-182">En **el Explorador de soluciones**, agregue referencias a los siguientes ensamblados a los `Calc1AddInSideAdapter` proyecto:</span><span class="sxs-lookup"><span data-stu-id="31c99-182">In **Solution Explorer**, add references to the following assemblies to the `Calc1AddInSideAdapter` project:</span></span>  
  
     <span data-ttu-id="31c99-183">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="31c99-183">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="31c99-184">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="31c99-184">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="31c99-185">Agregue referencias a los proyectos para los segmentos de canalización adyacente:</span><span class="sxs-lookup"><span data-stu-id="31c99-185">Add project references to the projects for the adjacent pipeline segments:</span></span>  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  <span data-ttu-id="31c99-186">Seleccione cada referencia de proyecto y en **propiedades** establecer **Copy Local** a **False**.</span><span class="sxs-lookup"><span data-stu-id="31c99-186">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="31c99-187">En Visual Basic, utilice el **referencias** ficha de **las propiedades del proyecto** establecer **Copy Local** a **False** para las dos referencias de proyecto.</span><span class="sxs-lookup"><span data-stu-id="31c99-187">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="31c99-188">Cambiar el nombre de la clase del proyecto predeterminado `CalculatorViewToContractAddInSideAdapter`.</span><span class="sxs-lookup"><span data-stu-id="31c99-188">Rename the project's default class `CalculatorViewToContractAddInSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="31c99-189">En el archivo de clase, agregue referencias de espacio de nombres a <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="31c99-189">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="31c99-190">En el archivo de clase, agregue referencias de espacio de nombres para los segmentos adyacentes: `CalcAddInViews` y `CalculatorContracts`.</span><span class="sxs-lookup"><span data-stu-id="31c99-190">In the class file, add namespace references for the adjacent segments: `CalcAddInViews` and `CalculatorContracts`.</span></span> <span data-ttu-id="31c99-191">(En Visual Basic, estas referencias de espacio de nombres son `Calc1AddInView.CalcAddInViews` y `Calc1Contract.CalculatorContracts`, a menos que haya desactivado los espacios de nombres predeterminado en los proyectos de Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="31c99-191">(In Visual Basic, these namespace references are `Calc1AddInView.CalcAddInViews` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="31c99-192">Aplicar el <xref:System.AddIn.Pipeline.AddInAdapterAttribute> atributo a la `CalculatorViewToContractAddInSideAdapter` (clase), que la identifica como el adaptador de conversión.</span><span class="sxs-lookup"><span data-stu-id="31c99-192">Apply the <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attribute to the `CalculatorViewToContractAddInSideAdapter` class, to identify it as the add-in-side adapter.</span></span>  
  
9. <span data-ttu-id="31c99-193">Realizar el `CalculatorViewToContractAddInSideAdapter` heredan de la clase <xref:System.AddIn.Pipeline.ContractBase>, que proporciona una implementación predeterminada de la <xref:System.AddIn.Contract.IContract> interfaz e implemente la interfaz del contrato de la canalización, `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="31c99-193">Make the `CalculatorViewToContractAddInSideAdapter` class inherit <xref:System.AddIn.Pipeline.ContractBase>, which provides a default implementation of the <xref:System.AddIn.Contract.IContract> interface, and implement the contract interface for the pipeline, `ICalc1Contract`.</span></span>  
  
10. <span data-ttu-id="31c99-194">Agregue un constructor público que acepta un `ICalculator`, lo almacena en caché en un campo privado y llama al constructor de clase base.</span><span class="sxs-lookup"><span data-stu-id="31c99-194">Add a public constructor that accepts an `ICalculator`, caches it in a private field, and calls the base class constructor.</span></span>  
  
11. <span data-ttu-id="31c99-195">Para implementar los miembros de `ICalc1Contract`, basta con llamar a los miembros correspondientes de la `ICalculator` instancia que se pasa al constructor y devolver los resultados.</span><span class="sxs-lookup"><span data-stu-id="31c99-195">To implement the members of `ICalc1Contract`, simply call the corresponding members of the `ICalculator` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="31c99-196">Esto adapta a la vista (`ICalculator`) para el contrato (`ICalc1Contract`).</span><span class="sxs-lookup"><span data-stu-id="31c99-196">This adapts the view (`ICalculator`) to the contract (`ICalc1Contract`).</span></span>  
  
     <span data-ttu-id="31c99-197">El código siguiente muestra el adaptador de conversión completado.</span><span class="sxs-lookup"><span data-stu-id="31c99-197">The following code shows the completed add-in-side adapter.</span></span>  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. <span data-ttu-id="31c99-198">Si lo desea, compile la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31c99-198">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host-side-adapter"></a><span data-ttu-id="31c99-199">Crear el adaptador del Host</span><span class="sxs-lookup"><span data-stu-id="31c99-199">Creating the Host-side Adapter</span></span>  
 <span data-ttu-id="31c99-200">Este adaptador del host se compone de un adaptador de contrato a vista.</span><span class="sxs-lookup"><span data-stu-id="31c99-200">This host-side adapter consists of one contract-to-view adapter.</span></span> <span data-ttu-id="31c99-201">Este segmento adapta el contrato a la vista de host del complemento.</span><span class="sxs-lookup"><span data-stu-id="31c99-201">This segment adapts the contract to the host view of the add-in.</span></span>  
  
 <span data-ttu-id="31c99-202">En esta canalización, el complemento proporciona un servicio que el host y el flujo de tipos desde el complemento al host.</span><span class="sxs-lookup"><span data-stu-id="31c99-202">In this pipeline, the add-in provides a service to the host and the types flow from the add-in to the host.</span></span> <span data-ttu-id="31c99-203">Dado que no hay tipos fluyen desde el host para el complemento, no es necesario incluir un adaptador de vista a contrato.</span><span class="sxs-lookup"><span data-stu-id="31c99-203">Because no types flow from the host to the add-in, you do not have to include a view-to-contract adapter.</span></span>  
  
 <span data-ttu-id="31c99-204">Para implementar la administración de la duración, use un <xref:System.AddIn.Pipeline.ContractHandle> objeto va a asociar un token de duración del contrato.</span><span class="sxs-lookup"><span data-stu-id="31c99-204">To implement lifetime management, use a <xref:System.AddIn.Pipeline.ContractHandle> object to attach a lifetime token to the contract.</span></span> <span data-ttu-id="31c99-205">Debe mantener una referencia a este identificador en orden para que funcione la administración de vigencia.</span><span class="sxs-lookup"><span data-stu-id="31c99-205">You must keep a reference to this handle in order for lifetime management to work.</span></span> <span data-ttu-id="31c99-206">Después de que se aplica el token, ninguna programación adicional es necesaria porque el sistema del complemento puede desechar objetos cuando ya no se usan y que estén disponibles para la recolección.</span><span class="sxs-lookup"><span data-stu-id="31c99-206">After the token is applied, no additional programming is required because the add-in system can dispose of objects when they are no longer being used and make them available for garbage collection.</span></span> <span data-ttu-id="31c99-207">Para más información, consulte [Administración de la duración](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span><span class="sxs-lookup"><span data-stu-id="31c99-207">For more information, see [Lifetime Management](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span></span>  
  
#### <a name="to-create-the-host-side-adapter"></a><span data-ttu-id="31c99-208">Para crear el adaptador del host</span><span class="sxs-lookup"><span data-stu-id="31c99-208">To create the host-side adapter</span></span>  
  
1.  <span data-ttu-id="31c99-209">Agregue un nuevo proyecto denominado `Calc1HostSideAdapter` a la `CalculatorV1` solución.</span><span class="sxs-lookup"><span data-stu-id="31c99-209">Add a new project named `Calc1HostSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="31c99-210">Basarlo en el **biblioteca de clases** plantilla.</span><span class="sxs-lookup"><span data-stu-id="31c99-210">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="31c99-211">En **el Explorador de soluciones**, agregue referencias a los siguientes ensamblados a los `Calc1HostSideAdapter` proyecto:</span><span class="sxs-lookup"><span data-stu-id="31c99-211">In **Solution Explorer**, add references to the following assemblies to the `Calc1HostSideAdapter` project:</span></span>  
  
     <span data-ttu-id="31c99-212">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="31c99-212">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="31c99-213">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="31c99-213">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="31c99-214">Agregue referencias a los proyectos en los segmentos adyacentes:</span><span class="sxs-lookup"><span data-stu-id="31c99-214">Add project references to the projects for the adjacent segments:</span></span>  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  <span data-ttu-id="31c99-215">Seleccione cada referencia de proyecto y en **propiedades** establecer **Copy Local** a **False**.</span><span class="sxs-lookup"><span data-stu-id="31c99-215">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="31c99-216">En Visual Basic, utilice el **referencias** ficha de **las propiedades del proyecto** establecer **Copy Local** a **False** para las dos referencias de proyecto.</span><span class="sxs-lookup"><span data-stu-id="31c99-216">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="31c99-217">Cambiar el nombre de la clase del proyecto predeterminado `CalculatorContractToViewHostSideAdapter`.</span><span class="sxs-lookup"><span data-stu-id="31c99-217">Rename the project's default class `CalculatorContractToViewHostSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="31c99-218">En el archivo de clase, agregue referencias de espacio de nombres a <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="31c99-218">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="31c99-219">En el archivo de clase, agregue referencias de espacio de nombres para los segmentos adyacentes: `CalcHVAs` y `CalculatorContracts`.</span><span class="sxs-lookup"><span data-stu-id="31c99-219">In the class file, add namespace references for the adjacent segments: `CalcHVAs` and `CalculatorContracts`.</span></span> <span data-ttu-id="31c99-220">(En Visual Basic, estas referencias de espacio de nombres son `Calc1HVA.CalcHVAs` y `Calc1Contract.CalculatorContracts`, a menos que haya desactivado los espacios de nombres predeterminado en los proyectos de Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="31c99-220">(In Visual Basic, these namespace references are `Calc1HVA.CalcHVAs` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="31c99-221">Aplicar el <xref:System.AddIn.Pipeline.HostAdapterAttribute> atributo a la `CalculatorContractToViewHostSideAdapter` (clase), que la identifica como el segmento del adaptador del host.</span><span class="sxs-lookup"><span data-stu-id="31c99-221">Apply the <xref:System.AddIn.Pipeline.HostAdapterAttribute> attribute to the `CalculatorContractToViewHostSideAdapter` class, to identify it as the host-side adapter segment.</span></span>  
  
9. <span data-ttu-id="31c99-222">Realizar el `CalculatorContractToViewHostSideAdapter` clase implementa la interfaz que representa la vista host del complemento: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="31c99-222">Make the `CalculatorContractToViewHostSideAdapter` class implement the interface that represents the host view of the add-in: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).</span></span>  
  
10. <span data-ttu-id="31c99-223">Agregue un constructor público que acepta el tipo de contrato de la canalización, `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="31c99-223">Add a public constructor that accepts the pipeline contract type, `ICalc1Contract`.</span></span> <span data-ttu-id="31c99-224">El constructor debe almacenar en caché la referencia al contrato.</span><span class="sxs-lookup"><span data-stu-id="31c99-224">The constructor must cache the reference to the contract.</span></span> <span data-ttu-id="31c99-225">También debe crear y almacenar en caché un nuevo <xref:System.AddIn.Pipeline.ContractHandle> para el contrato, para administrar la vigencia del complemento.</span><span class="sxs-lookup"><span data-stu-id="31c99-225">It must also create and cache a new <xref:System.AddIn.Pipeline.ContractHandle> for the contract, to manage the lifetime of the add-in.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="31c99-226">El <xref:System.AddIn.Pipeline.ContractHandle> es fundamental para la administración de la duración.</span><span class="sxs-lookup"><span data-stu-id="31c99-226">The <xref:System.AddIn.Pipeline.ContractHandle> is critical to lifetime management.</span></span> <span data-ttu-id="31c99-227">Si no puede mantener una referencia a la <xref:System.AddIn.Pipeline.ContractHandle> objeto recolección lo reclamará y la canalización se cerrará cuando el programa no lo espera.</span><span class="sxs-lookup"><span data-stu-id="31c99-227">If you fail to keep a reference to the <xref:System.AddIn.Pipeline.ContractHandle> object, garbage collection will reclaim it, and the pipeline will shut down when your program does not expect it.</span></span> <span data-ttu-id="31c99-228">Esto puede conducir a errores que son difíciles de diagnosticar, como <xref:System.AppDomainUnloadedException>.</span><span class="sxs-lookup"><span data-stu-id="31c99-228">This can lead to errors that are difficult to diagnose, such as <xref:System.AppDomainUnloadedException>.</span></span> <span data-ttu-id="31c99-229">Cierre es una fase normal en la vida de una canalización, por lo que no hay ninguna manera de que el código de administración de vigencia detectar que esta condición es un error.</span><span class="sxs-lookup"><span data-stu-id="31c99-229">Shutdown is a normal stage in the life of a pipeline, so there is no way for the lifetime management code to detect that this condition is an error.</span></span>  
  
11. <span data-ttu-id="31c99-230">Para implementar los miembros de `ICalculator`, basta con llamar a los miembros correspondientes de la `ICalc1Contract` instancia que se pasa al constructor y devolver los resultados.</span><span class="sxs-lookup"><span data-stu-id="31c99-230">To implement the members of `ICalculator`, simply call the corresponding members of the `ICalc1Contract` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="31c99-231">Esto adapta el contrato (`ICalc1Contract`) a la vista (`ICalculator`).</span><span class="sxs-lookup"><span data-stu-id="31c99-231">This adapts the contract (`ICalc1Contract`) to the view (`ICalculator`).</span></span>  
  
     <span data-ttu-id="31c99-232">El código siguiente muestra el adaptador del host completado.</span><span class="sxs-lookup"><span data-stu-id="31c99-232">The following code shows the completed host-side adapter.</span></span>  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. <span data-ttu-id="31c99-233">Si lo desea, compile la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31c99-233">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host"></a><span data-ttu-id="31c99-234">Crear el Host</span><span class="sxs-lookup"><span data-stu-id="31c99-234">Creating the Host</span></span>  
 <span data-ttu-id="31c99-235">Una aplicación host interactúa con el complemento a través de la vista host del complemento.</span><span class="sxs-lookup"><span data-stu-id="31c99-235">A host application interacts with the add-in through the host view of the add-in.</span></span> <span data-ttu-id="31c99-236">Usa el complemento detección y activación métodos proporcionados por el <xref:System.AddIn.Hosting.AddInStore> y <xref:System.AddIn.Hosting.AddInToken> clases para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="31c99-236">It uses add-in discovery and activation methods provided by the <xref:System.AddIn.Hosting.AddInStore> and <xref:System.AddIn.Hosting.AddInToken> classes to do the following:</span></span>  
  
-   <span data-ttu-id="31c99-237">Actualizar la caché de información de canalización y complemento.</span><span class="sxs-lookup"><span data-stu-id="31c99-237">Update the cache of pipeline and add-in information.</span></span>  
  
-   <span data-ttu-id="31c99-238">Buscar complementos del tipo de vista de host, `ICalculator`, bajo el directorio raíz de la canalización especificada.</span><span class="sxs-lookup"><span data-stu-id="31c99-238">Find add-ins of the host view type, `ICalculator`, under the specified pipeline root directory.</span></span>  
  
-   <span data-ttu-id="31c99-239">Solicitar al usuario que especifique que complemento para usar.</span><span class="sxs-lookup"><span data-stu-id="31c99-239">Prompt the user to specify which add-in to use.</span></span>  
  
-   <span data-ttu-id="31c99-240">Activar el complemento seleccionado en un nuevo dominio de aplicación con un nivel de confianza de seguridad especificado.</span><span class="sxs-lookup"><span data-stu-id="31c99-240">Activate the selected add-in in a new application domain with a specified security trust level.</span></span>  
  
-   <span data-ttu-id="31c99-241">Ejecute personalizado `RunCalculator` método, que llama a métodos del complemento según lo especificado por la vista host del complemento.</span><span class="sxs-lookup"><span data-stu-id="31c99-241">Run the custom `RunCalculator` method, which calls the add-in's methods as specified by the host view of the add-in.</span></span>  
  
#### <a name="to-create-the-host"></a><span data-ttu-id="31c99-242">Para crear el host</span><span class="sxs-lookup"><span data-stu-id="31c99-242">To create the host</span></span>  
  
1.  <span data-ttu-id="31c99-243">Agregue un nuevo proyecto denominado `Calc1Host` a la `CalculatorV1` solución.</span><span class="sxs-lookup"><span data-stu-id="31c99-243">Add a new project named `Calc1Host` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="31c99-244">Basarlo en el **aplicación de consola** plantilla.</span><span class="sxs-lookup"><span data-stu-id="31c99-244">Base it on the **Console Application** template.</span></span>  
  
2.  <span data-ttu-id="31c99-245">En **el Explorador de soluciones**, agregue una referencia al ensamblado System.AddIn.dll para el `Calc1Host` proyecto.</span><span class="sxs-lookup"><span data-stu-id="31c99-245">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the `Calc1Host` project.</span></span>  
  
3.  <span data-ttu-id="31c99-246">Agregar una referencia al proyecto el `Calc1HVA` proyecto.</span><span class="sxs-lookup"><span data-stu-id="31c99-246">Add a project reference to the `Calc1HVA` project.</span></span> <span data-ttu-id="31c99-247">Seleccione la referencia del proyecto y en **propiedades** establecer **Copy Local** a **False**.</span><span class="sxs-lookup"><span data-stu-id="31c99-247">Select the project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="31c99-248">En Visual Basic, utilice el **referencias** ficha de **las propiedades del proyecto** establecer **Copy Local** a **False**.</span><span class="sxs-lookup"><span data-stu-id="31c99-248">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False**.</span></span>  
  
4.  <span data-ttu-id="31c99-249">Cambiar el nombre del archivo de clase (módulo en Visual Basic) `MathHost1`.</span><span class="sxs-lookup"><span data-stu-id="31c99-249">Rename the class file (module in Visual Basic) `MathHost1`.</span></span>  
  
5.  <span data-ttu-id="31c99-250">En Visual Basic, utilice el **aplicación** pestaña de la **las propiedades del proyecto** cuadro de diálogo para establecer **objeto Startup** a **Sub Main**.</span><span class="sxs-lookup"><span data-stu-id="31c99-250">In Visual Basic, use the **Application** tab of the **Project Properties** dialog box to set **Startup object** to **Sub Main**.</span></span>  
  
6.  <span data-ttu-id="31c99-251">En el archivo de clase o módulo, agregue una referencia de espacio de nombres a <xref:System.AddIn.Hosting>.</span><span class="sxs-lookup"><span data-stu-id="31c99-251">In the class or module file, add a namespace reference to <xref:System.AddIn.Hosting>.</span></span>  
  
7.  <span data-ttu-id="31c99-252">En el archivo de clase o módulo, agregue una referencia de espacio de nombres para la vista de host del complemento: `CalcHVAs`.</span><span class="sxs-lookup"><span data-stu-id="31c99-252">In the class or module file, add a namespace reference for the host view of the add-in: `CalcHVAs`.</span></span> <span data-ttu-id="31c99-253">(En Visual Basic, esta referencia de espacio de nombres es `Calc1HVA.CalcHVAs`, a menos que haya desactivado los espacios de nombres predeterminado en los proyectos de Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="31c99-253">(In Visual Basic, this namespace reference is `Calc1HVA.CalcHVAs`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="31c99-254">En **el Explorador de soluciones**, seleccione la solución y desde el **proyecto** menú elija **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="31c99-254">In **Solution Explorer**, select the solution and from the **Project** menu choose **Properties**.</span></span> <span data-ttu-id="31c99-255">En el **páginas de propiedades de la solución** cuadro de diálogo, establezca el **proyecto de inicio único** sea este proyecto de aplicación host.</span><span class="sxs-lookup"><span data-stu-id="31c99-255">In the **Solution Property Pages** dialog box, set the **Single Startup Project** to be this host application project.</span></span>  
  
9. <span data-ttu-id="31c99-256">En el archivo de clase o módulo, use el <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> método para actualizar la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="31c99-256">In the class or module file, use the <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> method to update the cache.</span></span> <span data-ttu-id="31c99-257">Utilice la <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> método para obtener una colección de tokens y utilice el <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> método para activar un complemento.</span><span class="sxs-lookup"><span data-stu-id="31c99-257">Use the <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> method to get a collection of tokens, and use the <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> method to activate an add-in.</span></span>  
  
     <span data-ttu-id="31c99-258">El código siguiente muestra la aplicación host completada.</span><span class="sxs-lookup"><span data-stu-id="31c99-258">The following code shows the completed host application.</span></span>  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="31c99-259">Este código supone que la estructura de carpetas de la canalización se encuentra en la carpeta de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="31c99-259">This code assumes that the pipeline folder structure is located in the application folder.</span></span> <span data-ttu-id="31c99-260">Si se encuentra en otro lugar, cambie la línea de código que establece el `addInRoot` variable, por lo que la variable contiene la ruta de acceso a la estructura de directorios de canalización.</span><span class="sxs-lookup"><span data-stu-id="31c99-260">If you located it elsewhere, change the line of code that sets the `addInRoot` variable, so that the variable contains the path to your pipeline directory structure.</span></span>  
  
     <span data-ttu-id="31c99-261">El código usa un `ChooseCalculator` método para enumerar los tokens y para pedir al usuario elegir un complemento.</span><span class="sxs-lookup"><span data-stu-id="31c99-261">The code uses a `ChooseCalculator` method to list the tokens and to prompt the user to choose an add-in.</span></span> <span data-ttu-id="31c99-262">El `RunCalculator` método pide al usuario para expresiones matemáticas simples, analiza las expresiones utilizando la `Parser` clase y muestra los resultados devuelven por el complemento.</span><span class="sxs-lookup"><span data-stu-id="31c99-262">The `RunCalculator` method prompts the user for simple math expressions, parses the expressions using the `Parser` class, and displays the results returned by the add-in.</span></span>  
  
10. <span data-ttu-id="31c99-263">Si lo desea, compile la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31c99-263">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in"></a><span data-ttu-id="31c99-264">Crear el complemento</span><span class="sxs-lookup"><span data-stu-id="31c99-264">Creating the Add-In</span></span>  
 <span data-ttu-id="31c99-265">Un complemento implementa los métodos especificados por la vista de complemento.</span><span class="sxs-lookup"><span data-stu-id="31c99-265">An add-in implements the methods specified by the add-in view.</span></span> <span data-ttu-id="31c99-266">Este complemento implementa el `Add`, `Subtract`, `Multiply`, y `Divide` operaciones y devuelve los resultados al host.</span><span class="sxs-lookup"><span data-stu-id="31c99-266">This add-in implements the `Add`, `Subtract`, `Multiply`, and `Divide` operations and returns the results to the host.</span></span>  
  
#### <a name="to-create-the-add-in"></a><span data-ttu-id="31c99-267">Para crear el complemento</span><span class="sxs-lookup"><span data-stu-id="31c99-267">To create the add-in</span></span>  
  
1.  <span data-ttu-id="31c99-268">Agregue un nuevo proyecto denominado `AddInCalcV1` a la `CalculatorV1` solución.</span><span class="sxs-lookup"><span data-stu-id="31c99-268">Add a new project named `AddInCalcV1` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="31c99-269">Basarlo en el **biblioteca de clases** plantilla.</span><span class="sxs-lookup"><span data-stu-id="31c99-269">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="31c99-270">En **el Explorador de soluciones**, agregue una referencia al ensamblado System.AddIn.dll al proyecto.</span><span class="sxs-lookup"><span data-stu-id="31c99-270">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the project.</span></span>  
  
3.  <span data-ttu-id="31c99-271">Agregar una referencia al proyecto el `Calc1AddInView` proyecto.</span><span class="sxs-lookup"><span data-stu-id="31c99-271">Add a project reference to the `Calc1AddInView` project.</span></span> <span data-ttu-id="31c99-272">Seleccione la referencia del proyecto y en **propiedades**, establezca **Copy Local** a **False**.</span><span class="sxs-lookup"><span data-stu-id="31c99-272">Select the project reference, and in **Properties**, set **Copy Local** to **False**.</span></span> <span data-ttu-id="31c99-273">En Visual Basic, utilice el **referencias** ficha de **las propiedades del proyecto** establecer **Copy Local** a **False** para la referencia del proyecto.</span><span class="sxs-lookup"><span data-stu-id="31c99-273">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the project reference.</span></span>  
  
4.  <span data-ttu-id="31c99-274">Cambiar el nombre de la clase `AddInCalcV1`.</span><span class="sxs-lookup"><span data-stu-id="31c99-274">Rename the class `AddInCalcV1`.</span></span>  
  
5.  <span data-ttu-id="31c99-275">En el archivo de clase, agregue una referencia de espacio de nombres a <xref:System.AddIn> y el segmento de vista de complemento: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="31c99-275">In the class file, add a namespace reference to <xref:System.AddIn> and the add-in view segment: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).</span></span>  
  
6.  <span data-ttu-id="31c99-276">Aplicar el <xref:System.AddIn.AddInAttribute> atributo a la `AddInCalcV1` (clase), para identificar la clase como un complemento.</span><span class="sxs-lookup"><span data-stu-id="31c99-276">Apply the <xref:System.AddIn.AddInAttribute> attribute to the `AddInCalcV1` class, to identify the class as an add-in.</span></span>  
  
7.  <span data-ttu-id="31c99-277">Realizar el `AddInCalcV1` clase implementa la interfaz que representa la vista de complemento: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="31c99-277">Make the `AddInCalcV1` class implement the interface that represents the add-in view: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).</span></span>  
  
8.  <span data-ttu-id="31c99-278">Implemente los miembros de `ICalculator` devolviendo los resultados de los cálculos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="31c99-278">Implement the members of `ICalculator` by returning the results of the appropriate calculations.</span></span>  
  
     <span data-ttu-id="31c99-279">El código siguiente muestra el complemento completado.</span><span class="sxs-lookup"><span data-stu-id="31c99-279">The following code shows the completed add-in.</span></span>  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. <span data-ttu-id="31c99-280">Si lo desea, compile la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31c99-280">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="deploying-the-pipeline"></a><span data-ttu-id="31c99-281">Implementación de la canalización</span><span class="sxs-lookup"><span data-stu-id="31c99-281">Deploying the Pipeline</span></span>  
 <span data-ttu-id="31c99-282">Ahora está listo para compilar e implementar los segmentos de complemento a la estructura de directorios de canalización requerida.</span><span class="sxs-lookup"><span data-stu-id="31c99-282">You are now ready to build and deploy the add-in segments to the required pipeline directory structure.</span></span>  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a><span data-ttu-id="31c99-283">Para implementar los segmentos en la canalización</span><span class="sxs-lookup"><span data-stu-id="31c99-283">To deploy the segments to the pipeline</span></span>  
  
1.  <span data-ttu-id="31c99-284">En cada proyecto de la solución, utilice el **compilar** ficha de **las propiedades del proyecto** (el **compilar** pestaña en Visual Basic) para establecer el valor de la **ruta de acceso de salida**  (el **ruta de acceso de salida de compilación** en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="31c99-284">For each project in the solution, use the **Build** tab of **Project Properties** (the **Compile** tab in Visual Basic) to set the value of the **Output path** (the **Build output path** in Visual Basic).</span></span> <span data-ttu-id="31c99-285">Si el nombre de la carpeta aplicación `MyApp`, por ejemplo, podrían compilar sus proyectos en las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="31c99-285">If you named your application folder `MyApp`, for example, your projects would build into the following folders:</span></span>  
  
    |<span data-ttu-id="31c99-286">Proyecto</span><span class="sxs-lookup"><span data-stu-id="31c99-286">Project</span></span>|<span data-ttu-id="31c99-287">Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="31c99-287">Path</span></span>|  
    |-------------|----------|  
    |<span data-ttu-id="31c99-288">AddInCalcV1</span><span class="sxs-lookup"><span data-stu-id="31c99-288">AddInCalcV1</span></span>|<span data-ttu-id="31c99-289">MyApp\Pipeline\AddIns\CalcV1</span><span class="sxs-lookup"><span data-stu-id="31c99-289">MyApp\Pipeline\AddIns\CalcV1</span></span>|  
    |<span data-ttu-id="31c99-290">Calc1AddInSideAdapter</span><span class="sxs-lookup"><span data-stu-id="31c99-290">Calc1AddInSideAdapter</span></span>|<span data-ttu-id="31c99-291">MyApp\Pipeline\AddInSideAdapters</span><span class="sxs-lookup"><span data-stu-id="31c99-291">MyApp\Pipeline\AddInSideAdapters</span></span>|  
    |<span data-ttu-id="31c99-292">Calc1AddInView</span><span class="sxs-lookup"><span data-stu-id="31c99-292">Calc1AddInView</span></span>|<span data-ttu-id="31c99-293">MyApp\Pipeline\AddInViews</span><span class="sxs-lookup"><span data-stu-id="31c99-293">MyApp\Pipeline\AddInViews</span></span>|  
    |<span data-ttu-id="31c99-294">Calc1Contract</span><span class="sxs-lookup"><span data-stu-id="31c99-294">Calc1Contract</span></span>|<span data-ttu-id="31c99-295">MyApp\Pipeline\Contracts</span><span class="sxs-lookup"><span data-stu-id="31c99-295">MyApp\Pipeline\Contracts</span></span>|  
    |<span data-ttu-id="31c99-296">Calc1Host</span><span class="sxs-lookup"><span data-stu-id="31c99-296">Calc1Host</span></span>|<span data-ttu-id="31c99-297">MyApp</span><span class="sxs-lookup"><span data-stu-id="31c99-297">MyApp</span></span>|  
    |<span data-ttu-id="31c99-298">Calc1HostSideAdapter</span><span class="sxs-lookup"><span data-stu-id="31c99-298">Calc1HostSideAdapter</span></span>|<span data-ttu-id="31c99-299">MyApp\Pipeline\HostSideAdapters</span><span class="sxs-lookup"><span data-stu-id="31c99-299">MyApp\Pipeline\HostSideAdapters</span></span>|  
    |<span data-ttu-id="31c99-300">Calc1HVA</span><span class="sxs-lookup"><span data-stu-id="31c99-300">Calc1HVA</span></span>|<span data-ttu-id="31c99-301">MyApp</span><span class="sxs-lookup"><span data-stu-id="31c99-301">MyApp</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="31c99-302">Si ha decidido poner la estructura de carpetas de la canalización en una ubicación distinta a la carpeta de aplicación, debe modificar las rutas de acceso que se muestra en la tabla en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="31c99-302">If you decided to put your pipeline folder structure in a location other than your application folder, you must modify the paths shown in the table accordingly.</span></span> <span data-ttu-id="31c99-303">Vea la explicación de los requisitos de directorio de canalización en [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="31c99-303">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
2.  <span data-ttu-id="31c99-304">Compile la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31c99-304">Build the Visual Studio solution.</span></span>  
  
3.  <span data-ttu-id="31c99-305">Compruebe los directorios de la canalización y la aplicación para asegurarse de que los ensamblados se copiaron en los directorios correctos y que ninguna copia adicional de los ensamblados se instala en las carpetas incorrectas.</span><span class="sxs-lookup"><span data-stu-id="31c99-305">Check the application and pipeline directories to ensure that the assemblies were copied to the correct directories and that no extra copies of assemblies were installed in the wrong folders.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31c99-306">Si no cambió **Copy Local** a **False** para el `Calc1AddInView` referencia de proyecto la `AddInCalcV1` proyectos, problemas de cargador contexto impedirá que el complemento que se encuentra.</span><span class="sxs-lookup"><span data-stu-id="31c99-306">If you did not change **Copy Local** to **False** for the `Calc1AddInView` project reference in the `AddInCalcV1` project, loader context problems will prevent the add-in from being located.</span></span>  
  
     <span data-ttu-id="31c99-307">Para obtener información acerca de la implementación a la canalización, consulte [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="31c99-307">For information about deploying to the pipeline, see [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
## <a name="running-the-host-application"></a><span data-ttu-id="31c99-308">Ejecutar la aplicación Host</span><span class="sxs-lookup"><span data-stu-id="31c99-308">Running the Host Application</span></span>  
 <span data-ttu-id="31c99-309">Ahora está listo para ejecutar el host e interactuar con el complemento.</span><span class="sxs-lookup"><span data-stu-id="31c99-309">You are now ready to run the host and interact with the add-in.</span></span>  
  
#### <a name="to-run-the-host-application"></a><span data-ttu-id="31c99-310">Para ejecutar la aplicación host</span><span class="sxs-lookup"><span data-stu-id="31c99-310">To run the host application</span></span>  
  
1.  <span data-ttu-id="31c99-311">En el símbolo del sistema, vaya al directorio de la aplicación y ejecutar la aplicación host, `Calc1Host.exe`.</span><span class="sxs-lookup"><span data-stu-id="31c99-311">At the command prompt, go to the application directory and run the host application, `Calc1Host.exe`.</span></span>  
  
2.  <span data-ttu-id="31c99-312">El host busca todos los complementos disponibles de su tipo y se le pide que seleccione un complemento.</span><span class="sxs-lookup"><span data-stu-id="31c99-312">The host finds all available add-ins of its type and prompts you to select an add-in.</span></span> <span data-ttu-id="31c99-313">Escriba **1** para el complemento solo está disponible.</span><span class="sxs-lookup"><span data-stu-id="31c99-313">Enter **1** for the only available add-in.</span></span>  
  
3.  <span data-ttu-id="31c99-314">Escriba una ecuación para la Calculadora, como **2 + 2**.</span><span class="sxs-lookup"><span data-stu-id="31c99-314">Enter an equation for the calculator, such as **2 + 2**.</span></span> <span data-ttu-id="31c99-315">Debe haber espacios entre los números y el operador.</span><span class="sxs-lookup"><span data-stu-id="31c99-315">There must be spaces between the numbers and the operator.</span></span>  
  
4.  <span data-ttu-id="31c99-316">Tipo **salir** y presione la **ENTRAR** tecla para cerrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="31c99-316">Type **exit** and press the **Enter** key to close the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31c99-317">Vea también</span><span class="sxs-lookup"><span data-stu-id="31c99-317">See Also</span></span>  
- [<span data-ttu-id="31c99-318">Tutorial: Habilita la compatibilidad con versiones anteriores como los cambios de Host</span><span class="sxs-lookup"><span data-stu-id="31c99-318">Walkthrough: Enabling Backward Compatibility as Your Host Changes</span></span>](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
-  [<span data-ttu-id="31c99-319">Tutorial: Pasar colecciones entre Hosts y complementos</span><span class="sxs-lookup"><span data-stu-id="31c99-319">Walkthrough: Passing Collections Between Hosts and Add-Ins</span></span>](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
-  [<span data-ttu-id="31c99-320">Requisitos del desarrollo de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="31c99-320">Pipeline Development Requirements</span></span>](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
-  [<span data-ttu-id="31c99-321">Contratos, vistas y adaptadores</span><span class="sxs-lookup"><span data-stu-id="31c99-321">Contracts, Views, and Adapters</span></span>](https://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c)  
-  [<span data-ttu-id="31c99-322">Desarrollo de canalizaciones</span><span class="sxs-lookup"><span data-stu-id="31c99-322">Pipeline Development</span></span>](../../../docs/framework/add-ins/pipeline-development.md)
