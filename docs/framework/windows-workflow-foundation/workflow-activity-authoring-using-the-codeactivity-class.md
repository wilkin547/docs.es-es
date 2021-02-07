---
description: 'Más información sobre: creación de actividades de flujo de trabajo mediante la clase CodeActivity'
title: Crear actividad de flujo de trabajo mediante la clase CodeActivity
ms.date: 03/30/2017
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
ms.openlocfilehash: 393b6c586a88e876484f6888441d5bb82b4c0dad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754919"
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a><span data-ttu-id="49a36-103">Crear actividad de flujo de trabajo mediante la clase CodeActivity</span><span class="sxs-lookup"><span data-stu-id="49a36-103">Workflow Activity Authoring Using the CodeActivity Class</span></span>

<span data-ttu-id="49a36-104">Las actividades creadas al heredar de <xref:System.Activities.CodeActivity> pueden implementar el comportamiento imperativo básico al invalidar el método <xref:System.Activities.CodeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="49a36-104">Activities created by inheriting from <xref:System.Activities.CodeActivity> can implement basic imperative behavior by overriding the <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>

## <a name="using-codeactivitycontext"></a><span data-ttu-id="49a36-105">Usar CodeActivityContext</span><span class="sxs-lookup"><span data-stu-id="49a36-105">Using CodeActivityContext</span></span>

 <span data-ttu-id="49a36-106">Se puede tener acceso a las características del tiempo de ejecución del flujo de trabajo desde dentro del método <xref:System.Activities.CodeActivity.Execute%2A> usando los miembros del parámetro `context`, del tipo <xref:System.Activities.CodeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="49a36-106">Features of the workflow runtime can be accessed from within the <xref:System.Activities.CodeActivity.Execute%2A> method by using members of the `context` parameter, of type <xref:System.Activities.CodeActivityContext>.</span></span> <span data-ttu-id="49a36-107">Las características disponibles mediante <xref:System.Activities.CodeActivityContext> incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="49a36-107">The features available through <xref:System.Activities.CodeActivityContext> include the following:</span></span>

- <span data-ttu-id="49a36-108">Obtener y establecer los valores de variables y argumentos.</span><span class="sxs-lookup"><span data-stu-id="49a36-108">Getting and setting the values of variables and arguments.</span></span>

- <span data-ttu-id="49a36-109">Características de seguimiento personalizadas con <xref:System.Activities.CodeActivityContext.Track%2A>.</span><span class="sxs-lookup"><span data-stu-id="49a36-109">Custom tracking features using <xref:System.Activities.CodeActivityContext.Track%2A>.</span></span>

- <span data-ttu-id="49a36-110">Obtenga acceso a las propiedades de ejecución de la actividad con <xref:System.Activities.CodeActivityContext.GetProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="49a36-110">Access to the activity’s execution properties using <xref:System.Activities.CodeActivityContext.GetProperty%2A>.</span></span>

#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a><span data-ttu-id="49a36-111">Para crear una actividad personalizada que herede de CodeActivity</span><span class="sxs-lookup"><span data-stu-id="49a36-111">To create a custom activity that inherits from CodeActivity</span></span>

1. <span data-ttu-id="49a36-112">Abra Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="49a36-112">Open Visual Studio 2010.</span></span>

2. <span data-ttu-id="49a36-113">Seleccione **archivo**, **nuevo** y **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="49a36-113">Select **File**, **New**, and then **Project**.</span></span> <span data-ttu-id="49a36-114">Seleccione **flujo de trabajo 4,0** en **Visual C#** en la ventana **tipos de proyecto** y seleccione el nodo **V2010** .</span><span class="sxs-lookup"><span data-stu-id="49a36-114">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="49a36-115">Seleccione **biblioteca de actividades** en la ventana **plantillas** .</span><span class="sxs-lookup"><span data-stu-id="49a36-115">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="49a36-116">Dé al nuevo proyecto el nombre "HelloActivity".</span><span class="sxs-lookup"><span data-stu-id="49a36-116">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="49a36-117">Haga clic con el botón secundario en Activity1. XAML en el proyecto HelloActivity y seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="49a36-117">Right-click Activity1.xaml in the HelloActivity project and select **Delete**.</span></span>

4. <span data-ttu-id="49a36-118">Haga clic con el botón derecho en el proyecto HelloActivity, seleccione **Agregar** y, a continuación, **clase**.</span><span class="sxs-lookup"><span data-stu-id="49a36-118">Right-click the HelloActivity project and select **Add** , and then **Class**.</span></span> <span data-ttu-id="49a36-119">Dé a la nueva clase el nombre "HelloActivity.cs".</span><span class="sxs-lookup"><span data-stu-id="49a36-119">Name the new class HelloActivity.cs.</span></span>

5. <span data-ttu-id="49a36-120">En el archivo HelloActivity.cs, agregue las siguientes directivas `using`.</span><span class="sxs-lookup"><span data-stu-id="49a36-120">In the HelloActivity.cs file, add the following `using` directives.</span></span>

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. <span data-ttu-id="49a36-121">Haga que la nueva clase herede de <xref:System.Activities.CodeActivity> al agregar una clase base a la declaración de clase.</span><span class="sxs-lookup"><span data-stu-id="49a36-121">Make the new class inherit from <xref:System.Activities.CodeActivity> by adding a base class to the class declaration.</span></span>

    ```csharp
    class HelloActivity : CodeActivity
    ```

7. <span data-ttu-id="49a36-122">Agregue la funcionalidad a la clase agregando un método <xref:System.Activities.CodeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="49a36-122">Add functionality to the class by adding an <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. <span data-ttu-id="49a36-123">Use <xref:System.Activities.CodeActivityContext> para crear un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="49a36-123">Use the <xref:System.Activities.CodeActivityContext> to create a tracking record.</span></span>

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));
        context.Track(record);
    }
    ```
