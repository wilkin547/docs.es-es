---
title: 'Tutorial: Definir un contrato de servicio de Windows Communication Foundation'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: f93ef787c74a4581d45c24c5a704cc5fb044bd46
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409970"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="9cf0e-102">Tutorial: Definir un contrato de servicio de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="9cf0e-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="9cf0e-103">Este tutorial describen las primeras cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9cf0e-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="9cf0e-104">Para obtener información general de los tutoriales, consulte [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="9cf0e-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="9cf0e-105">Cuando se crea un servicio WCF, la primera tarea es definir un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="9cf0e-106">El contrato de servicio especifica qué operaciones admite el servicio.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="9cf0e-107">Una operación se puede considerar un método de servicio Web.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="9cf0e-108">Crear contratos de servicio mediante la definición de un objeto Visual C# o la interfaz de Visual Basic (VB).</span><span class="sxs-lookup"><span data-stu-id="9cf0e-108">You create service contracts by defining a Visual C# or Visual Basic (VB) interface.</span></span> <span data-ttu-id="9cf0e-109">Una interfaz tiene las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="9cf0e-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="9cf0e-110">Cada método de la interfaz se corresponde con una operación de servicio concreta.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-110">Each method in the interface corresponds to a specific service operation.</span></span> 
- <span data-ttu-id="9cf0e-111">Para cada interfaz, se debe aplicar el <xref:System.ServiceModel.ServiceContractAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="9cf0e-112">Para cada operación o método, se debe aplicar el <xref:System.ServiceModel.OperationContractAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span> 

<span data-ttu-id="9cf0e-113">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="9cf0e-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="9cf0e-114">Crear un **biblioteca de servicios WCF** proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="9cf0e-115">Defina una interfaz de contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-115">Define a service contract interface.</span></span>


## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="9cf0e-116">Crear un proyecto de biblioteca de servicios WCF y definir una interfaz de contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="9cf0e-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="9cf0e-117">Abra Visual Studio como administrador.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="9cf0e-118">Para ello, seleccione el programa de Visual Studio en el **iniciar** menú y, a continuación, seleccione **más** > **ejecutar como administrador** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="9cf0e-119">Crear un **biblioteca de servicios WCF** proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="9cf0e-120">En el menú **Archivo**, seleccione **Nuevo** > **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="9cf0e-121">En el **nuevo proyecto** cuadro de diálogo, en el lado izquierdo, expanda **Visual C#** o **Visual Basic**y, a continuación, seleccione el **WCF** categoría.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="9cf0e-122">Visual Studio muestra una lista de plantillas de proyecto en la sección central de la ventana.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="9cf0e-123">Seleccione **biblioteca de servicios WCF**.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="9cf0e-124">Si no ve el **WCF** categoría de plantilla de proyecto, es posible que deba instalar el **Windows Communication Foundation** componente de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="9cf0e-125">En el **nuevo proyecto** cuadro de diálogo, seleccione el **abrir Visual Studio Installer** vínculo en el lado izquierdo.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="9cf0e-126">Seleccione el **componentes individuales** ficha y, a continuación, busque y seleccione **Windows Communication Foundation** bajo el **las actividades de desarrollo** categoría.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="9cf0e-127">Elija **modificar** para empezar a instalar el componente.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="9cf0e-128">En la sección inferior de la ventana, escriba *GettingStartedLib* para el **nombre** y *GettingStarted* para el **nombre de la solución**.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span> 

   4. <span data-ttu-id="9cf0e-129">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-129">Select **OK**.</span></span>

      <span data-ttu-id="9cf0e-130">Visual Studio crea el proyecto, que tiene tres archivos: *IService1.cs* (o *IService1.vb* para un proyecto de Visual Basic), *Service1.cs* (o *Service1.vb* para un proyecto de Visual Basic), y  *App.config*. Visual Studio define estos archivos como sigue:</span><span class="sxs-lookup"><span data-stu-id="9cf0e-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span> 
      - <span data-ttu-id="9cf0e-131">El *IService1* archivo contiene la definición predeterminada del contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-131">The *IService1* file contains the default definition of the service contract.</span></span> 
      - <span data-ttu-id="9cf0e-132">El *Service1* archivo contiene la implementación predeterminada del contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-132">The *Service1* file contains the default implementation of the service contract.</span></span> 
      - <span data-ttu-id="9cf0e-133">El *App.config* archivo contiene la información de configuración necesaria para cargar el servicio de forma predeterminada con la herramienta de Host de servicio WCF de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="9cf0e-134">Para obtener más información acerca de la herramienta de Host de servicio WCF, vea [Host de servicio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9cf0e-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="9cf0e-135">Si ha instalado Visual Studio con la configuración del entorno de desarrollo de Visual Basic, la solución podría estar oculto.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="9cf0e-136">Si esto es así, seleccione **opciones** desde el **herramientas** menú, a continuación, seleccione **proyectos y soluciones** > **General** en el **opciones** ventana.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="9cf0e-137">Seleccione **Mostrar solución siempre**.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-137">Select **Always show solution**.</span></span> <span data-ttu-id="9cf0e-138">Además, compruebe que **guardar nuevos proyectos al crearlos** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-138">Also, verify that **Save new projects when created** is selected.</span></span>


3. <span data-ttu-id="9cf0e-139">Desde **el Explorador de soluciones**, abra el **IService1.cs** o **IService1.vb** y reemplace su código con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9cf0e-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

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

     <span data-ttu-id="9cf0e-140">Este contrato define una calculadora en línea.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-140">This contract defines an online calculator.</span></span> <span data-ttu-id="9cf0e-141">Tenga en cuenta la `ICalculator` interfaz se marca con el <xref:System.ServiceModel.ServiceContractAttribute> atributo (simplificada como `ServiceContract`).</span><span class="sxs-lookup"><span data-stu-id="9cf0e-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="9cf0e-142">Este atributo define un espacio de nombres para eliminar la ambigüedad entre el nombre de contrato.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="9cf0e-143">El código marca cada operación de calculadora con los <xref:System.ServiceModel.OperationContractAttribute> atributo (simplificada como `OperationContract`).</span><span class="sxs-lookup"><span data-stu-id="9cf0e-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9cf0e-144">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9cf0e-144">Next steps</span></span>

<span data-ttu-id="9cf0e-145">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="9cf0e-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="9cf0e-146">Cree un proyecto de biblioteca de servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="9cf0e-147">Defina una interfaz de contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-147">Define a service contract interface.</span></span>

<span data-ttu-id="9cf0e-148">Avance al siguiente tutorial para aprender a implementar el contrato de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="9cf0e-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9cf0e-149">Tutorial: Implementar un contrato de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="9cf0e-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
