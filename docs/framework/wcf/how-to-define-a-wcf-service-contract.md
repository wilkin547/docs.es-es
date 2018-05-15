---
title: Definición de un contrato de servicio de Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- service contracts [WCF], defining
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 5e8abbf8c5f9b0696d90ccbee94c5d8f4dd8b1ec
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="12e1b-102">Definición de un contrato de servicio de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="12e1b-102">How to: Define a Windows Communication Foundation Service Contract</span></span>
<span data-ttu-id="12e1b-103">Se trata de la primera de las seis tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="12e1b-103">This is the first of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="12e1b-104">Para obtener información general de las seis de las tareas, consulte la [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md) tema.</span><span class="sxs-lookup"><span data-stu-id="12e1b-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="12e1b-105">Al crear un servicio WCF, la primera tarea es definir un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="12e1b-105">When creating a WCF service, the first task is to define a service contract.</span></span> <span data-ttu-id="12e1b-106">El contrato de servicio especifica qué operaciones admite el servicio.</span><span class="sxs-lookup"><span data-stu-id="12e1b-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="12e1b-107">Una operación se puede considerar un método de servicio Web.</span><span class="sxs-lookup"><span data-stu-id="12e1b-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="12e1b-108">Los contratos se crean mediante la definición de una interfaz de C++, C# o Visual Basic (VB).</span><span class="sxs-lookup"><span data-stu-id="12e1b-108">Contracts are created by defining a C++, C#, or Visual Basic (VB) interface.</span></span> <span data-ttu-id="12e1b-109">Cada método de la interfaz se corresponde con una operación de servicio concreta.</span><span class="sxs-lookup"><span data-stu-id="12e1b-109">Each method in the interface corresponds to a specific service operation.</span></span> <span data-ttu-id="12e1b-110">Cada interfaz debe tener <xref:System.ServiceModel.ServiceContractAttribute> aplicado y cada operación debe tener el atributo <xref:System.ServiceModel.OperationContractAttribute> aplicado.</span><span class="sxs-lookup"><span data-stu-id="12e1b-110">Each interface must have the <xref:System.ServiceModel.ServiceContractAttribute> applied to it and each operation must have the <xref:System.ServiceModel.OperationContractAttribute> attribute applied to it.</span></span> <span data-ttu-id="12e1b-111">Si un método de una interfaz que tiene el atributo <xref:System.ServiceModel.ServiceContractAttribute> no tiene el atributo <xref:System.ServiceModel.OperationContractAttribute>, el servicio no expone ese método.</span><span class="sxs-lookup"><span data-stu-id="12e1b-111">If a method within an interface that has the <xref:System.ServiceModel.ServiceContractAttribute> attribute does not have the <xref:System.ServiceModel.OperationContractAttribute> attribute, that method is not exposed by the service.</span></span>  
  
 <span data-ttu-id="12e1b-112">El código utilizado para esta tarea se proporciona en el ejemplo que sigue al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="12e1b-112">The code used for this task is provided in the example following the procedure.</span></span>  
  
### <a name="to-define-a-service-contract"></a><span data-ttu-id="12e1b-113">Para definir un contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="12e1b-113">To define a service contract</span></span>  
  
1.  <span data-ttu-id="12e1b-114">Abra [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] como administrador haciendo clic en el programa en el **iniciar** menú y seleccionando **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="12e1b-114">Open  [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] as an administrator by right-clicking the program in the **Start** menu and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="12e1b-115">Crear un proyecto de biblioteca de servicios WCF, haga clic en el **archivo** menú y seleccionando **New**, **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="12e1b-115">Create a WCF Service Library project by clicking the **File** menu and selecting **New**, **Project**.</span></span> <span data-ttu-id="12e1b-116">En el **nuevo proyecto** cuadro de diálogo, en el lado izquierdo del cuadro de diálogo expandir **Visual C#** para un proyecto de C# o **otros lenguajes** y, a continuación, **Visual Basic** para un proyecto de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="12e1b-116">In the **New Project** dialog, on the left-hand side of the dialog expand **Visual C#** for a C# project or **Other Languages** and then **Visual Basic** for a Visual Basic project.</span></span> <span data-ttu-id="12e1b-117">En el idioma seleccionado, seleccione **WCF** y se mostrará una lista de plantillas de proyecto en la sección central del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="12e1b-117">Under the language selected select **WCF** and a list of project templates will be displayed on the center section of the dialog.</span></span> <span data-ttu-id="12e1b-118">Seleccione **biblioteca de servicios WCF**y el tipo de `GettingStartedLib` en el **nombre** cuadro de texto y `GettingStarted` en el **nombre de la solución** cuadro de texto en la parte inferior del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="12e1b-118">Select **WCF Service Library**, and type `GettingStartedLib` in the **Name** textbox and `GettingStarted` in the **Solution name** textbox at the bottom of the dialog.</span></span>  
  
3.  <span data-ttu-id="12e1b-119">Visual Studio creará el proyecto que contiene 3 archivos: IService1.cs (o IService1.vb), Service1.cs (o Service1.vb) y App.config.  El archivo IService1 contiene un contrato de servicio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="12e1b-119">Visual Studio will create the project which contains 3 files: IService1.cs (or IService1.vb), Service1.cs (or Service1.vb), and App.config.  The IService1 file contains a default service contract.</span></span>  <span data-ttu-id="12e1b-120">El archivo Service1 contiene una implementación predeterminada del contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="12e1b-120">The Service1 file contains a default implementation of the service contract.</span></span> <span data-ttu-id="12e1b-121">El archivo App.config contiene la configuración necesaria para cargar el servicio predeterminado con el host de servicio WCF de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="12e1b-121">The App.config file contains configuration needed to load the default service with the Visual Studio WCF Service Host.</span></span> <span data-ttu-id="12e1b-122">Para obtener más información acerca de la herramienta de Host de servicio WCF, vea [Host de servicio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span><span class="sxs-lookup"><span data-stu-id="12e1b-122">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span></span>  
  
4.  <span data-ttu-id="12e1b-123">Abra el archivo IService1.cs o IService1.vb y elimine el código dentro de la declaración de espacio de nombres que sale de la declaración de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="12e1b-123">Open the IService1.cs or IService1.vb file and delete the code within the namespace declaration leaving the namespace declaration.</span></span> <span data-ttu-id="12e1b-124">Dentro de la declaración de espacio de nombres se define una nueva interfaz denominada `ICalculator` como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="12e1b-124">Inside the namespace declaration define a new interface called `ICalculator` as shown in the code below.</span></span>  
  
    ```  
    // IService.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Runtime.Serialization;  
    using System.ServiceModel;  
    using System.Text;  
  
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
  
    ```  
    ‘IService.vb  
    Imports System  
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
  
     <span data-ttu-id="12e1b-125">Este contrato define una calculadora en línea.</span><span class="sxs-lookup"><span data-stu-id="12e1b-125">This contract defines an online calculator.</span></span> <span data-ttu-id="12e1b-126">Observe que la interfaz `ICalculator` se marca con el atributo <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="12e1b-126">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="12e1b-127">Este atributo define un espacio de nombres que se usa para eliminar la ambigüedad del nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="12e1b-127">This attribute defines a namespace that is used to disambiguate the contract name.</span></span> <span data-ttu-id="12e1b-128">Cada operación de calculadora se marca con el atributo <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="12e1b-128">Each calculator operation is marked with the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="12e1b-129">Al usar los atributos para anotar una interfaz, miembro o clase, puede quitar la parte "Attribute" del nombre de atributo.</span><span class="sxs-lookup"><span data-stu-id="12e1b-129">When using attributes to annotate an interface, member, or class, you can drop the "Attribute" part from the attribute name.</span></span> <span data-ttu-id="12e1b-130">Por tanto, la clase <xref:System.ServiceModel.ServiceContractAttribute> se convierte en `[ServiceContract]` en C# o `<ServiceContract>` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="12e1b-130">So <xref:System.ServiceModel.ServiceContractAttribute> becomes `[ServiceContract]` in C#, or `<ServiceContract>` in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12e1b-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="12e1b-131">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [<span data-ttu-id="12e1b-132">Cómo implementar un contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="12e1b-132">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 [<span data-ttu-id="12e1b-133">Introducción</span><span class="sxs-lookup"><span data-stu-id="12e1b-133">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="12e1b-134">Probar internamente</span><span class="sxs-lookup"><span data-stu-id="12e1b-134">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
