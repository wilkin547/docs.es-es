---
title: Definición de un contrato de servicio de Windows Communication Foundation
ms.date: 09/14/2018
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 4f85a51c47eb045d1d2f0111cb217199c9acf0d7
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "46489164"
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="52517-102">Definición de un contrato de servicio de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="52517-102">How to: Define a Windows Communication Foundation Service Contract</span></span>

<span data-ttu-id="52517-103">Se trata de la primera de las seis tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="52517-103">This is the first of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="52517-104">Para obtener información general de las seis tareas, vea el tema [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="52517-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>

 <span data-ttu-id="52517-105">Al crear un servicio WCF, la primera tarea es definir un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="52517-105">When creating a WCF service, the first task is to define a service contract.</span></span> <span data-ttu-id="52517-106">El contrato de servicio especifica qué operaciones admite el servicio.</span><span class="sxs-lookup"><span data-stu-id="52517-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="52517-107">Una operación se puede considerar un método de servicio Web.</span><span class="sxs-lookup"><span data-stu-id="52517-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="52517-108">Los contratos se crean mediante la definición de una interfaz de C++, C# o Visual Basic (VB).</span><span class="sxs-lookup"><span data-stu-id="52517-108">Contracts are created by defining a C++, C#, or Visual Basic (VB) interface.</span></span> <span data-ttu-id="52517-109">Cada método de la interfaz se corresponde con una operación de servicio concreta.</span><span class="sxs-lookup"><span data-stu-id="52517-109">Each method in the interface corresponds to a specific service operation.</span></span> <span data-ttu-id="52517-110">Cada interfaz debe tener <xref:System.ServiceModel.ServiceContractAttribute> aplicado y cada operación debe tener el atributo <xref:System.ServiceModel.OperationContractAttribute> aplicado.</span><span class="sxs-lookup"><span data-stu-id="52517-110">Each interface must have the <xref:System.ServiceModel.ServiceContractAttribute> applied to it and each operation must have the <xref:System.ServiceModel.OperationContractAttribute> attribute applied to it.</span></span> <span data-ttu-id="52517-111">Si un método de una interfaz que tiene el atributo <xref:System.ServiceModel.ServiceContractAttribute> no tiene el atributo <xref:System.ServiceModel.OperationContractAttribute>, el servicio no expone ese método.</span><span class="sxs-lookup"><span data-stu-id="52517-111">If a method within an interface that has the <xref:System.ServiceModel.ServiceContractAttribute> attribute does not have the <xref:System.ServiceModel.OperationContractAttribute> attribute, that method is not exposed by the service.</span></span>

 <span data-ttu-id="52517-112">El código utilizado para esta tarea se proporciona en el ejemplo que sigue al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="52517-112">The code used for this task is provided in the example following the procedure.</span></span>

## <a name="define-a-service-contract"></a><span data-ttu-id="52517-113">Definir un contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="52517-113">Define a service contract</span></span>

1. <span data-ttu-id="52517-114">Abra Visual Studio como administrador haciendo clic con el programa en el **iniciar** menú y seleccionando **más** > **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="52517-114">Open Visual Studio as an administrator by right-clicking the program in the **Start** menu and selecting **More** > **Run as administrator**.</span></span>

2. <span data-ttu-id="52517-115">Cree un proyecto de biblioteca de servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="52517-115">Create a WCF Service Library project.</span></span>

   1. <span data-ttu-id="52517-116">En el menú **Archivo**, seleccione **Nuevo** > **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="52517-116">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="52517-117">En el **nuevo proyecto** cuadro de diálogo, en el lado izquierdo, expanda **Visual C#** o **Visual Basic**y, a continuación, seleccione el **WCF** categoría.</span><span class="sxs-lookup"><span data-stu-id="52517-117">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="52517-118">En la sección central del cuadro de diálogo se muestra una lista de plantillas de proyecto.</span><span class="sxs-lookup"><span data-stu-id="52517-118">A list of project templates is displayed in the center section of the dialog.</span></span> <span data-ttu-id="52517-119">Seleccione **biblioteca de servicios WCF**.</span><span class="sxs-lookup"><span data-stu-id="52517-119">Select **WCF Service Library**.</span></span>

   3. <span data-ttu-id="52517-120">Escriba `GettingStartedLib` en el **nombre** textbox y `GettingStarted` en el **nombre de la solución** cuadro de texto en la parte inferior del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="52517-120">Enter `GettingStartedLib` in the **Name** textbox and `GettingStarted` in the **Solution name** textbox at the bottom of the dialog.</span></span>

   > [!NOTE]
   > <span data-ttu-id="52517-121">Si no ve el **WCF** categoría de plantilla de proyecto, es posible que deba instalar el **Windows Communication Foundation** componente de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="52517-121">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="52517-122">En el **nuevo proyecto** diálogo cuadro, haga clic en el vínculo que dice **instalador de Visual Studio abierto**.</span><span class="sxs-lookup"><span data-stu-id="52517-122">In the **New Project** dialog box, click the link that says **Open Visual Studio Installer**.</span></span> <span data-ttu-id="52517-123">Seleccione el **componentes individuales** ficha y, a continuación, busque y seleccione **Windows Communication Foundation** bajo el **las actividades de desarrollo** categoría.</span><span class="sxs-lookup"><span data-stu-id="52517-123">Select the **Individual Components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="52517-124">Elija **modificar** para empezar a instalar el componente.</span><span class="sxs-lookup"><span data-stu-id="52517-124">Choose **Modify** to begin installing the component.</span></span>

   <span data-ttu-id="52517-125">Visual Studio crea el proyecto, que contiene 3 archivos: IService1.cs (o IService1.vb), Service1.cs (o Service1.vb) y App.config. El archivo IService1 contiene un contrato de servicio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="52517-125">Visual Studio creates the project, which contains 3 files: IService1.cs (or IService1.vb), Service1.cs (or Service1.vb), and App.config. The IService1 file contains a default service contract.</span></span> <span data-ttu-id="52517-126">El archivo Service1 contiene una implementación predeterminada del contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="52517-126">The Service1 file contains a default implementation of the service contract.</span></span> <span data-ttu-id="52517-127">El archivo App.config contiene la configuración necesaria para cargar el servicio predeterminado con el host de servicio WCF de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="52517-127">The App.config file contains configuration needed to load the default service with the Visual Studio WCF Service Host.</span></span> <span data-ttu-id="52517-128">Para obtener más información acerca de la herramienta de Host de servicio WCF, vea [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span><span class="sxs-lookup"><span data-stu-id="52517-128">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span></span>

3. <span data-ttu-id="52517-129">Abra el archivo IService1.cs o IService1.vb y elimine el código dentro de la declaración de espacio de nombres, dejando la declaración de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="52517-129">Open the IService1.cs or IService1.vb file and delete the code within the namespace declaration, leaving the namespace declaration.</span></span> <span data-ttu-id="52517-130">Dentro de la declaración de espacio de nombres se define una nueva interfaz denominada `ICalculator` como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="52517-130">Inside the namespace declaration define a new interface called `ICalculator` as shown in the code below.</span></span>

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

     <span data-ttu-id="52517-131">Este contrato define una calculadora en línea.</span><span class="sxs-lookup"><span data-stu-id="52517-131">This contract defines an online calculator.</span></span> <span data-ttu-id="52517-132">Observe que la interfaz `ICalculator` se marca con el atributo <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="52517-132">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="52517-133">Este atributo define un espacio de nombres que se usa para eliminar la ambigüedad del nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="52517-133">This attribute defines a namespace that is used to disambiguate the contract name.</span></span> <span data-ttu-id="52517-134">Cada operación de calculadora se marca con el atributo <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="52517-134">Each calculator operation is marked with the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>

## <a name="next-steps"></a><span data-ttu-id="52517-135">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="52517-135">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="52517-136">Cómo: implementar un contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="52517-136">How to: Implement a service contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)

## <a name="see-also"></a><span data-ttu-id="52517-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="52517-137">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="52517-138">Cómo implementar un contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="52517-138">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="52517-139">Introducción</span><span class="sxs-lookup"><span data-stu-id="52517-139">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="52517-140">Probar internamente</span><span class="sxs-lookup"><span data-stu-id="52517-140">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)