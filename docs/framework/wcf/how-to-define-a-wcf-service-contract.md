---
title: 'Tutorial: definición de un contrato de servicio de Windows Communication Foundation'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 49526808a65b68c6df734bd7f3e76eff1e4a6bc5
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338295"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="77c10-102">Tutorial: definición de un contrato de servicio de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="77c10-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="77c10-103">En este tutorial se describe la primera de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="77c10-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="77c10-104">Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="77c10-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="77c10-105">Al crear un servicio WCF, la primera tarea es definir un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="77c10-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="77c10-106">El contrato de servicio especifica qué operaciones admite el servicio.</span><span class="sxs-lookup"><span data-stu-id="77c10-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="77c10-107">Una operación se puede considerar un método de servicio Web.</span><span class="sxs-lookup"><span data-stu-id="77c10-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="77c10-108">Los contratos de servicio se crean mediante C# la definición de una interfaz o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="77c10-108">You create service contracts by defining a C# or Visual Basic interface.</span></span> <span data-ttu-id="77c10-109">Una interfaz tiene las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="77c10-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="77c10-110">Cada método de la interfaz se corresponde con una operación de servicio concreta.</span><span class="sxs-lookup"><span data-stu-id="77c10-110">Each method in the interface corresponds to a specific service operation.</span></span> 
- <span data-ttu-id="77c10-111">Para cada interfaz, debe aplicar el atributo <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="77c10-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="77c10-112">Para cada operación o método, debe aplicar el atributo <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="77c10-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span> 

<span data-ttu-id="77c10-113">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="77c10-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="77c10-114">Cree un proyecto de **biblioteca de servicios WCF** .</span><span class="sxs-lookup"><span data-stu-id="77c10-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="77c10-115">Defina una interfaz de contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="77c10-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="77c10-116">Crear un proyecto de biblioteca de servicios WCF y definir una interfaz de contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="77c10-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="77c10-117">Abra Visual Studio como administrador.</span><span class="sxs-lookup"><span data-stu-id="77c10-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="77c10-118">Para ello, seleccione el programa de Visual Studio en el menú **Inicio** y, a continuación, seleccione **más** > **Ejecutar como administrador** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="77c10-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="77c10-119">Cree un proyecto de **biblioteca de servicios WCF** .</span><span class="sxs-lookup"><span data-stu-id="77c10-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="77c10-120">En el menú **Archivo**, seleccione **Nuevo** > **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="77c10-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="77c10-121">En el cuadro de diálogo **nuevo proyecto** , en el lado izquierdo, expanda  **C# visual** o **Visual Basic**y, a continuación, seleccione la categoría **WCF** .</span><span class="sxs-lookup"><span data-stu-id="77c10-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="77c10-122">Visual Studio muestra una lista de plantillas de proyecto en la sección central de la ventana.</span><span class="sxs-lookup"><span data-stu-id="77c10-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="77c10-123">Seleccione **biblioteca de servicios WCF**.</span><span class="sxs-lookup"><span data-stu-id="77c10-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="77c10-124">Si no ve la categoría de plantilla de proyecto de **WCF** , es posible que deba instalar el componente de **Windows Communication Foundation** de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="77c10-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="77c10-125">En el cuadro de diálogo **nuevo proyecto** , seleccione el vínculo **abrir instalador de Visual Studio** en el lado izquierdo.</span><span class="sxs-lookup"><span data-stu-id="77c10-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="77c10-126">Seleccione la pestaña **componentes individuales** y busque y seleccione **Windows Communication Foundation** en la categoría **actividades de desarrollo** .</span><span class="sxs-lookup"><span data-stu-id="77c10-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="77c10-127">Elija **modificar** para iniciar la instalación del componente.</span><span class="sxs-lookup"><span data-stu-id="77c10-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="77c10-128">En la sección inferior de la ventana, escriba *GettingStartedLib* para el **nombre** y *gettingstarted* para el **nombre**de la solución.</span><span class="sxs-lookup"><span data-stu-id="77c10-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span> 

   4. <span data-ttu-id="77c10-129">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="77c10-129">Select **OK**.</span></span>

      <span data-ttu-id="77c10-130">Visual Studio crea el proyecto, que tiene tres archivos: *IService1.CS* (o *IService1. VB* para un proyecto Visual Basic), *Service1.CS* (o *Service1. VB* para un proyecto Visual Basic) y *app. config*. Visual Studio define estos archivos como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="77c10-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span> 
      - <span data-ttu-id="77c10-131">El archivo *IService1* contiene la definición predeterminada del contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="77c10-131">The *IService1* file contains the default definition of the service contract.</span></span> 
      - <span data-ttu-id="77c10-132">El archivo *Service1* contiene la implementación predeterminada del contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="77c10-132">The *Service1* file contains the default implementation of the service contract.</span></span> 
      - <span data-ttu-id="77c10-133">El archivo *app. config* contiene la información de configuración necesaria para cargar el servicio predeterminado con la herramienta host de servicio WCF de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="77c10-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="77c10-134">Para obtener más información acerca de la herramienta host de servicio WCF, vea [host de servicio WCF (WcfSvcHost. exe)](wcf-service-host-wcfsvchost-exe.md).</span><span class="sxs-lookup"><span data-stu-id="77c10-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="77c10-135">Si instaló Visual Studio con Visual Basic configuración del entorno del desarrollador, puede que la solución esté oculta.</span><span class="sxs-lookup"><span data-stu-id="77c10-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="77c10-136">En este caso, seleccione **Opciones** en el menú **herramientas** y, a continuación, seleccione **proyectos y soluciones** > **General** en la ventana **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="77c10-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="77c10-137">Seleccione **Mostrar solución siempre**.</span><span class="sxs-lookup"><span data-stu-id="77c10-137">Select **Always show solution**.</span></span> <span data-ttu-id="77c10-138">Además, compruebe que la opción **Guardar nuevos proyectos al crear** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="77c10-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="77c10-139">En **Explorador de soluciones**, abra el archivo **IService1.CS** o **IService1. VB** y reemplace su código por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="77c10-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

    ```csharp
    using System;
    using System.ServiceModel;

    namespace GettingStartedLib
    {
            [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
            public interface ICalculator
            {
                [OperationContract]
                double Add(double n1, double n2);
                [OperationContract]
                double Subtract(double n1, double n2);
                [OperationContract]
                double Multiply(double n1, double n2);
                [OperationContract]
                double Divide(double n1, double n2);
            }
    }
    ```

    ```vb
    Imports System.ServiceModel

    Namespace GettingStartedLib

        <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
        Public Interface ICalculator

            <OperationContract()> _
            Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
        End Interface
    End Namespace
    ```

     <span data-ttu-id="77c10-140">Este contrato define una calculadora en línea.</span><span class="sxs-lookup"><span data-stu-id="77c10-140">This contract defines an online calculator.</span></span> <span data-ttu-id="77c10-141">Observe que la interfaz `ICalculator` está marcada con el atributo <xref:System.ServiceModel.ServiceContractAttribute> (simplificado como `ServiceContract`).</span><span class="sxs-lookup"><span data-stu-id="77c10-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="77c10-142">Este atributo define un espacio de nombres para eliminar la ambigüedad del nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="77c10-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="77c10-143">El código marca cada operación de la calculadora con el <xref:System.ServiceModel.OperationContractAttribute> atributo (simplificado como `OperationContract`).</span><span class="sxs-lookup"><span data-stu-id="77c10-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="77c10-144">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="77c10-144">Next steps</span></span>

<span data-ttu-id="77c10-145">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="77c10-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="77c10-146">Cree un proyecto de biblioteca de servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="77c10-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="77c10-147">Defina una interfaz de contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="77c10-147">Define a service contract interface.</span></span>

<span data-ttu-id="77c10-148">Avance al siguiente tutorial para aprender a implementar el contrato de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="77c10-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="77c10-149">Tutorial: implementar un contrato de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="77c10-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
