---
title: 'Tutorial: definición de un contrato de servicio de Windows Communication Foundation'
description: Obtenga información sobre cómo definir un contrato de servicios como parte de una serie de artículos que le ayudarán a empezar a crear una aplicación WCF.
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 5cb371da8c7180b8c4cbf5ac11468fbb8e0e13cc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246316"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="1dc87-103">Tutorial: definición de un contrato de servicio de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="1dc87-103">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="1dc87-104">En este tutorial se describe la primera de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1dc87-104">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="1dc87-105">Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="1dc87-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="1dc87-106">Al crear un servicio WCF, la primera tarea es definir un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="1dc87-106">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="1dc87-107">El contrato de servicio especifica qué operaciones admite este.</span><span class="sxs-lookup"><span data-stu-id="1dc87-107">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="1dc87-108">Una operación se puede considerar un método de servicio Web.</span><span class="sxs-lookup"><span data-stu-id="1dc87-108">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="1dc87-109">Cree contratos de servicio mediante la definición de una interfaz de C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1dc87-109">You create service contracts by defining a C# or Visual Basic interface.</span></span> <span data-ttu-id="1dc87-110">Una interfaz tiene las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="1dc87-110">An interface has the following characteristics:</span></span>

- <span data-ttu-id="1dc87-111">Cada método de la interfaz corresponde a una operación de servicio específica.</span><span class="sxs-lookup"><span data-stu-id="1dc87-111">Each method in the interface corresponds to a specific service operation.</span></span>
- <span data-ttu-id="1dc87-112">Para cada interfaz, debe aplicar el <xref:System.ServiceModel.ServiceContractAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="1dc87-112">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="1dc87-113">Para cada operación o método, debe aplicar el <xref:System.ServiceModel.OperationContractAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="1dc87-113">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>

<span data-ttu-id="1dc87-114">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="1dc87-114">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="1dc87-115">Cree un proyecto de **biblioteca de servicios WCF** .</span><span class="sxs-lookup"><span data-stu-id="1dc87-115">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="1dc87-116">Defina una interfaz de contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="1dc87-116">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="1dc87-117">Crear un proyecto de biblioteca de servicios WCF y definir una interfaz de contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="1dc87-117">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="1dc87-118">Abra Visual Studio como administrador.</span><span class="sxs-lookup"><span data-stu-id="1dc87-118">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="1dc87-119">Para ello, seleccione el programa de Visual Studio en el menú **Inicio** y, a continuación, seleccione **más**  >  **Ejecutar como administrador** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="1dc87-119">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="1dc87-120">Cree un proyecto de **biblioteca de servicios WCF** .</span><span class="sxs-lookup"><span data-stu-id="1dc87-120">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="1dc87-121">En el menú **Archivo**, seleccione **Nuevo** > **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="1dc87-121">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="1dc87-122">En el cuadro de diálogo **nuevo proyecto** , en el lado izquierdo, expanda **Visual C#** o **Visual Basic**y, a continuación, seleccione la categoría **WCF** .</span><span class="sxs-lookup"><span data-stu-id="1dc87-122">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="1dc87-123">Visual Studio muestra una lista de plantillas de proyecto en la sección central de la ventana.</span><span class="sxs-lookup"><span data-stu-id="1dc87-123">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="1dc87-124">Seleccione **biblioteca de servicios WCF**.</span><span class="sxs-lookup"><span data-stu-id="1dc87-124">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="1dc87-125">Si no ve la categoría de plantilla de proyecto de **WCF** , es posible que deba instalar el componente de **Windows Communication Foundation** de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1dc87-125">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="1dc87-126">En el cuadro de diálogo **nuevo proyecto** , seleccione el vínculo **abrir instalador de Visual Studio** en el lado izquierdo.</span><span class="sxs-lookup"><span data-stu-id="1dc87-126">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="1dc87-127">Seleccione la pestaña **componentes individuales** y busque y seleccione **Windows Communication Foundation** en la categoría **actividades de desarrollo** .</span><span class="sxs-lookup"><span data-stu-id="1dc87-127">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="1dc87-128">Elija **modificar** para iniciar la instalación del componente.</span><span class="sxs-lookup"><span data-stu-id="1dc87-128">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="1dc87-129">En la sección inferior de la ventana, escriba *GettingStartedLib* para el **nombre** y *gettingstarted* para el **nombre**de la solución.</span><span class="sxs-lookup"><span data-stu-id="1dc87-129">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span>

   4. <span data-ttu-id="1dc87-130">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1dc87-130">Select **OK**.</span></span>

      <span data-ttu-id="1dc87-131">Visual Studio crea el proyecto, que tiene tres archivos: *IService1.CS* (o *IService1. VB* para un proyecto Visual Basic), *Service1.CS* (o *Service1. vb* para un proyecto Visual Basic) y *App.config*. Visual Studio define estos archivos como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="1dc87-131">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span>
      - <span data-ttu-id="1dc87-132">El archivo *IService1* contiene la definición predeterminada del contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="1dc87-132">The *IService1* file contains the default definition of the service contract.</span></span>
      - <span data-ttu-id="1dc87-133">El archivo *Service1* contiene la implementación predeterminada del contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="1dc87-133">The *Service1* file contains the default implementation of the service contract.</span></span>
      - <span data-ttu-id="1dc87-134">El archivo de *App.config* contiene la información de configuración necesaria para cargar el servicio predeterminado con la herramienta host de servicio WCF de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1dc87-134">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="1dc87-135">Para obtener más información acerca de la herramienta host de servicio WCF, vea [host de servicio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span><span class="sxs-lookup"><span data-stu-id="1dc87-135">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="1dc87-136">Si instaló Visual Studio con Visual Basic configuración del entorno del desarrollador, puede que la solución esté oculta.</span><span class="sxs-lookup"><span data-stu-id="1dc87-136">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="1dc87-137">En este caso, seleccione **Opciones** en el menú **herramientas** y, a continuación, seleccione **proyectos y soluciones**  >  **General** en la ventana **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="1dc87-137">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="1dc87-138">Seleccione **Mostrar solución siempre**.</span><span class="sxs-lookup"><span data-stu-id="1dc87-138">Select **Always show solution**.</span></span> <span data-ttu-id="1dc87-139">Además, compruebe que la opción **Guardar nuevos proyectos al crear** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1dc87-139">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="1dc87-140">En **Explorador de soluciones**, abra el archivo **IService1.CS** o **IService1. VB** y reemplace su código por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="1dc87-140">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

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

     <span data-ttu-id="1dc87-141">Este contrato define una calculadora en línea.</span><span class="sxs-lookup"><span data-stu-id="1dc87-141">This contract defines an online calculator.</span></span> <span data-ttu-id="1dc87-142">Observe que la `ICalculator` interfaz está marcada con el <xref:System.ServiceModel.ServiceContractAttribute> atributo (simplificado como `ServiceContract` ).</span><span class="sxs-lookup"><span data-stu-id="1dc87-142">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="1dc87-143">Este atributo define un espacio de nombres para eliminar la ambigüedad del nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="1dc87-143">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="1dc87-144">El código marca cada operación de la calculadora con el <xref:System.ServiceModel.OperationContractAttribute> atributo (simplificado como `OperationContract` ).</span><span class="sxs-lookup"><span data-stu-id="1dc87-144">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1dc87-145">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1dc87-145">Next steps</span></span>

<span data-ttu-id="1dc87-146">En este tutorial, ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="1dc87-146">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="1dc87-147">Cree un proyecto de biblioteca de servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="1dc87-147">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="1dc87-148">Defina una interfaz de contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="1dc87-148">Define a service contract interface.</span></span>

<span data-ttu-id="1dc87-149">Avance al siguiente tutorial para aprender a implementar el contrato de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="1dc87-149">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1dc87-150">Tutorial: implementar un contrato de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="1dc87-150">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
