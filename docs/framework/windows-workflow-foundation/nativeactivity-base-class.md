---
description: 'Más información sobre: clase base NativeActivity'
title: Clase base NativeActivity
ms.date: 03/30/2017
ms.assetid: 254a4c50-425b-426d-a32f-0f7234925bac
ms.openlocfilehash: 184001ad9ee83c238265764cda3bc007e4a1fc71
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720142"
---
# <a name="nativeactivity-base-class"></a><span data-ttu-id="ee2e8-103">Clase base NativeActivity</span><span class="sxs-lookup"><span data-stu-id="ee2e8-103">NativeActivity Base Class</span></span>

<span data-ttu-id="ee2e8-104"><xref:System.Activities.NativeActivity> es una clase abstracta con un constructor protegido.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-104"><xref:System.Activities.NativeActivity> is an abstract class with a protected constructor.</span></span> <span data-ttu-id="ee2e8-105">Al igual que ocurre con <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> se usa para escribir el comportamiento imperativo al implementar un método <xref:System.Activities.NativeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-105">Like <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> is used for writing imperative behavior by implementing an <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span> <span data-ttu-id="ee2e8-106">A diferencia de <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> tiene acceso a todas las características expuestas del tiempo de ejecución del flujo de trabajo a través del objeto <xref:System.Activities.NativeActivityContext> pasado al método <xref:System.Activities.NativeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-106">Unlike <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> has access to all of the exposed features of the workflow runtime through the <xref:System.Activities.NativeActivityContext> object passed to the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>

## <a name="using-nativeactivitycontext"></a><span data-ttu-id="ee2e8-107">Usar NativeActivityContext</span><span class="sxs-lookup"><span data-stu-id="ee2e8-107">Using NativeActivityContext</span></span>

 <span data-ttu-id="ee2e8-108">Se puede tener acceso a las características del tiempo de ejecución del flujo de trabajo desde dentro del método <xref:System.Activities.NativeActivity.Execute%2A> usando los miembros del parámetro `context`, del tipo <xref:System.Activities.NativeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-108">Features of the workflow runtime can be accessed from within the <xref:System.Activities.NativeActivity.Execute%2A> method by using members of the `context` parameter, of type <xref:System.Activities.NativeActivityContext>.</span></span> <span data-ttu-id="ee2e8-109">Las características disponibles mediante <xref:System.Activities.NativeActivityContext> incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-109">The features available through <xref:System.Activities.NativeActivityContext> include the following:</span></span>

- <span data-ttu-id="ee2e8-110">Obtener y definir los argumentos y variables.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-110">Getting and setting of arguments and variables.</span></span>

- <span data-ttu-id="ee2e8-111">Programar las actividades secundarias con <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A></span><span class="sxs-lookup"><span data-stu-id="ee2e8-111">Scheduling child activities with <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A></span></span>

- <span data-ttu-id="ee2e8-112">Anular la ejecución de la actividad con <xref:System.Activities.NativeActivityContext.Abort%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-112">Aborting activity execution using <xref:System.Activities.NativeActivityContext.Abort%2A>.</span></span>

- <span data-ttu-id="ee2e8-113">Cancelar la ejecución secundaria con <xref:System.Activities.NativeActivityContext.CancelChild%2A> y <xref:System.Activities.NativeActivityContext.CancelChildren%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-113">Canceling child execution using <xref:System.Activities.NativeActivityContext.CancelChild%2A> and <xref:System.Activities.NativeActivityContext.CancelChildren%2A>.</span></span>

- <span data-ttu-id="ee2e8-114">Obtener acceso a los marcadores de actividad usando dichos métodos como <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A> y <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-114">Access to activity bookmarks using such methods as <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A>, and <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A>.</span></span>

- <span data-ttu-id="ee2e8-115">Características de seguimiento personalizadas con <xref:System.Activities.CodeActivityContext.Track%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-115">Custom tracking features using <xref:System.Activities.CodeActivityContext.Track%2A>.</span></span>

- <span data-ttu-id="ee2e8-116">Acceso a las propiedades de ejecución de la actividad y a las propiedades de los valores con <xref:System.Activities.CodeActivityContext.GetProperty%2A> y <xref:System.Activities.NativeActivityContext.GetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-116">Access to the activity’s execution properties and value properties using <xref:System.Activities.CodeActivityContext.GetProperty%2A> and <xref:System.Activities.NativeActivityContext.GetValue%2A>.</span></span>

- <span data-ttu-id="ee2e8-117">Programar las acciones de la actividad y las funciones mediante <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> y <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-117">Scheduling activity actions and functions using <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> and <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A>.</span></span>

### <a name="to-create-a-custom-activity-that-inherits-from-nativeactivity"></a><span data-ttu-id="ee2e8-118">Para crear una actividad personalizada que herede de NativeActivity</span><span class="sxs-lookup"><span data-stu-id="ee2e8-118">To create a custom activity that inherits from NativeActivity</span></span>

1. <span data-ttu-id="ee2e8-119">OpenVisual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-119">OpenVisual Studio 2010.</span></span>

2. <span data-ttu-id="ee2e8-120">Seleccione **archivo**, **nuevo** y **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-120">Select **File**, **New**, and then **Project**.</span></span> <span data-ttu-id="ee2e8-121">Seleccione **flujo de trabajo 4,0** en **Visual C#** en la ventana **tipos de proyecto** y seleccione el nodo **V2010** .</span><span class="sxs-lookup"><span data-stu-id="ee2e8-121">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="ee2e8-122">Seleccione **biblioteca de actividades** en la ventana **plantillas** .</span><span class="sxs-lookup"><span data-stu-id="ee2e8-122">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="ee2e8-123">Dé al nuevo proyecto el nombre "HelloActivity".</span><span class="sxs-lookup"><span data-stu-id="ee2e8-123">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="ee2e8-124">Haga clic con el botón secundario en Activity1. XAML en el proyecto HelloActivity y seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-124">Right-click Activity1.xaml in the HelloActivity project and select **Delete**.</span></span>

4. <span data-ttu-id="ee2e8-125">Haga clic con el botón derecho en el proyecto HelloActivity, seleccione **Agregar** y, a continuación, **clase**.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-125">Right-click the HelloActivity project and select **Add**, and then **Class**.</span></span> <span data-ttu-id="ee2e8-126">Dé a la nueva clase el nombre "HelloActivity.cs".</span><span class="sxs-lookup"><span data-stu-id="ee2e8-126">Name the new class HelloActivity.cs.</span></span>

5. <span data-ttu-id="ee2e8-127">En el archivo HelloActivity.cs, agregue las siguientes directivas `using`.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-127">In the HelloActivity.cs file, add the following `using` directives.</span></span>

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. <span data-ttu-id="ee2e8-128">Haga que la nueva clase herede de <xref:System.Activities.NativeActivity> al agregar una clase base a la declaración de clase.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-128">Make the new class inherit from <xref:System.Activities.NativeActivity> by adding a base class to the class declaration.</span></span>

    ```csharp
    class HelloActivity : NativeActivity
    ```

7. <span data-ttu-id="ee2e8-129">Agregue la funcionalidad a la clase agregando un método <xref:System.Activities.NativeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-129">Add functionality to the class by adding an <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>

    ```csharp
    protected override void Execute(NativeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. <span data-ttu-id="ee2e8-130">Invalide el método <xref:System.Activities.NativeActivity.CacheMetadata%2A> y llame al método Add adecuado para que el tiempo de ejecución del flujo de trabajo conozca las variables, los argumentos, los elementos secundarios y los delegados personalizados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-130">Override the <xref:System.Activities.NativeActivity.CacheMetadata%2A> method and call the appropriate Add method to let the workflow runtime know about the custom activity’s variables, arguments, children, and delegates.</span></span> <span data-ttu-id="ee2e8-131">Para obtener más información, vea la clase <xref:System.Activities.NativeActivityMetadata>.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-131">For more information see the <xref:System.Activities.NativeActivityMetadata> class.</span></span>

9. <span data-ttu-id="ee2e8-132">Utilice el objeto <xref:System.Activities.NativeActivityContext> para programar un marcador.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-132">Use the <xref:System.Activities.NativeActivityContext> object to schedule a bookmark.</span></span> <span data-ttu-id="ee2e8-133">Vea <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A> para obtener detalles sobre cómo crear, programar y reanudar un marcador.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-133">See <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A> for details on how to create, schedule, and resume a bookmark.</span></span>

    ```csharp
    protected override void Execute(NativeActivityContext context)
        {
            // Create a Bookmark and wait for it to be resumed.
            context.CreateBookmark(BookmarkName.Get(context),
                new BookmarkCallback(OnResumeBookmark));
        }
    ```
