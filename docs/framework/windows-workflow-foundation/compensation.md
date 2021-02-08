---
description: 'Más información acerca de: compensación'
title: Compensación
ms.date: 03/30/2017
ms.assetid: 722e9766-48d7-456c-9496-d7c5c8f0fa76
ms.openlocfilehash: d2c57a248939d0485075a5cbf57d91789f58d01a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792796"
---
# <a name="compensation"></a><span data-ttu-id="081f5-103">Compensación</span><span class="sxs-lookup"><span data-stu-id="081f5-103">Compensation</span></span>

<span data-ttu-id="081f5-104">La compensación en Windows Workflow Foundation (WF) es el mecanismo por el que se puede deshacer o compensar el trabajo previamente completado (siguiendo la lógica definida por la aplicación) cuando se produce un error posterior.</span><span class="sxs-lookup"><span data-stu-id="081f5-104">Compensation in Windows Workflow Foundation (WF) is the mechanism by which previously completed work can be undone or compensated (following the logic defined by the application) when a subsequent failure occurs.</span></span> <span data-ttu-id="081f5-105">Esta sección describe cómo usar la compensación en los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="081f5-105">This section describes how to use compensation in workflows.</span></span>  
  
## <a name="compensation-vs-transactions"></a><span data-ttu-id="081f5-106">Compensación en comparación con transacciones</span><span class="sxs-lookup"><span data-stu-id="081f5-106">Compensation vs. Transactions</span></span>  

 <span data-ttu-id="081f5-107">Las transacciones permiten combinar varias operaciones en una sola unidad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="081f5-107">A transaction allows you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="081f5-108">El uso de una transacción le da a la aplicación la posibilidad de anular (revertir) todos los cambios ejecutados desde dentro de la transacción si se produce algún error en algún momento del proceso de transacción.</span><span class="sxs-lookup"><span data-stu-id="081f5-108">Using a transaction gives your application the ability to abort (roll back) all changes executed from within the transaction if any errors occur during any part of the transaction process.</span></span> <span data-ttu-id="081f5-109">Sin embargo, el uso de las transacciones puede que no sea adecuado si el trabajo se está ejecutando mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="081f5-109">However, using transactions may not be appropriate if the work is long running.</span></span> <span data-ttu-id="081f5-110">Por ejemplo, se implementa una aplicación que planea un viaje como un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="081f5-110">For example, a travel planning application is implemented as a workflow.</span></span> <span data-ttu-id="081f5-111">Los pasos del flujo de trabajo pueden consistir en la reserva de un vuelo, la espera de la aprobación del administrador y, a continuación, el pago del vuelo.</span><span class="sxs-lookup"><span data-stu-id="081f5-111">The steps of the workflow may consist of booking a flight, waiting for manager approval, and then paying for the flight.</span></span> <span data-ttu-id="081f5-112">Este proceso podría tardar muchos días y no es práctico que los pasos de reservar y pagar el vuelo formen parte de la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="081f5-112">This process could take many days and it is not practical for the steps of booking and paying for the flight to participate in the same transaction.</span></span> <span data-ttu-id="081f5-113">En un escenario como este, se podría usar la compensación para deshacer el paso de la reserva del flujo de trabajo si se produce un error posterior durante el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="081f5-113">In a scenario such as this, compensation could be used to undo the booking step of the workflow if there is a failure later in the processing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="081f5-114">Este tema trata la compensación en flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="081f5-114">This topic covers compensation in workflows.</span></span> <span data-ttu-id="081f5-115">Para obtener más información sobre las transacciones en flujos de trabajo, vea [transacciones](workflow-transactions.md) y <xref:System.Activities.Statements.TransactionScope> .</span><span class="sxs-lookup"><span data-stu-id="081f5-115">For more information about transactions in workflows, see [Transactions](workflow-transactions.md) and <xref:System.Activities.Statements.TransactionScope>.</span></span> <span data-ttu-id="081f5-116">Para obtener más información acerca de las transacciones, vea <xref:System.Transactions?displayProperty=nameWithType> y <xref:System.Transactions.Transaction?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="081f5-116">For more information about transactions, see <xref:System.Transactions?displayProperty=nameWithType> and <xref:System.Transactions.Transaction?displayProperty=nameWithType>.</span></span>  
  
## <a name="using-compensableactivity"></a><span data-ttu-id="081f5-117">Usar CompensableActivity</span><span class="sxs-lookup"><span data-stu-id="081f5-117">Using CompensableActivity</span></span>  

 <span data-ttu-id="081f5-118"><xref:System.Activities.Statements.CompensableActivity> es la actividad de compensación principal en [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="081f5-118"><xref:System.Activities.Statements.CompensableActivity> is the core compensation activity in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="081f5-119">Cualquier actividad que realice un trabajo que cabe la posibilidad de que deba compensarse se coloca en la propiedad <xref:System.Activities.Statements.CompensableActivity.Body%2A> de la clase <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="081f5-119">Any activities that perform work that may need to be compensated are placed into the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of a <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="081f5-120">En este ejemplo, el paso de la reserva de compra de un vuelo se encuentra en la propiedad <xref:System.Activities.Statements.CompensableActivity.Body%2A> de una clase <xref:System.Activities.Statements.CompensableActivity> y la cancelación de la reserva está en la propiedad <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="081f5-120">In this example, the reservation step of purchasing a flight is placed into the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of a <xref:System.Activities.Statements.CompensableActivity> and the cancellation of the reservation is placed into the <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>.</span></span> <span data-ttu-id="081f5-121">Justo después de <xref:System.Activities.Statements.CompensableActivity> en el flujo de trabajo hay dos actividades que esperan la aprobación del administrador y, a continuación, se completa la compra del vuelo.</span><span class="sxs-lookup"><span data-stu-id="081f5-121">Immediately following the <xref:System.Activities.Statements.CompensableActivity> in the workflow are two activities that wait for manager approval and then complete the purchasing step of the flight.</span></span> <span data-ttu-id="081f5-122">Si una condición de error provoca la cancelación del flujo de trabajo después de que la clase <xref:System.Activities.Statements.CompensableActivity> se haya completado correctamente, las actividades del controlador <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> se programan y el vuelo se cancela.</span><span class="sxs-lookup"><span data-stu-id="081f5-122">If an error condition causes the workflow to be canceled after the <xref:System.Activities.Statements.CompensableActivity> has successfully completed, then the activities in the <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> handler are scheduled and the flight is canceled.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#1)]  
  
 <span data-ttu-id="081f5-123">El siguiente ejemplo es el flujo de trabajo en XAML.</span><span class="sxs-lookup"><span data-stu-id="081f5-123">The following example is the workflow in XAML.</span></span>  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 <span data-ttu-id="081f5-124">Cuando se invoca el flujo de trabajo, en la consola se muestra el siguiente resultado.</span><span class="sxs-lookup"><span data-stu-id="081f5-124">When the workflow is invoked, the following output is displayed to the console.</span></span>  
  
 <span data-ttu-id="081f5-125">**ReserveFlight: Ticket is reserved.**</span><span class="sxs-lookup"><span data-stu-id="081f5-125">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="081f5-126">**ManagerApproval: aprobación del administrador recibida.** 
 **PurchaseFlight: vale adquirido.** 
 El **flujo de trabajo se completó correctamente con el estado: cerrado.**</span><span class="sxs-lookup"><span data-stu-id="081f5-126">**ManagerApproval: Manager approval received.**
**PurchaseFlight: Ticket is purchased.**
**Workflow completed successfully with status: Closed.**</span></span>
> [!NOTE]
> <span data-ttu-id="081f5-127">Las actividades de ejemplo de este tema como `ReserveFlight` muestran su nombre y propósito a la consola para ayudar a mostrar el orden en el que se ejecutan las actividades cuando se produce la compensación.</span><span class="sxs-lookup"><span data-stu-id="081f5-127">The sample activities in this topic such as `ReserveFlight` display their name and purpose to the console to help illustrate the order in which the activities are executed when compensation occurs.</span></span>  
  
### <a name="default-workflow-compensation"></a><span data-ttu-id="081f5-128">Compensación predeterminada del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="081f5-128">Default Workflow Compensation</span></span>  

 <span data-ttu-id="081f5-129">De forma predeterminada, si se cancela el flujo de trabajo, se ejecuta la lógica de compensación para cualquier actividad compensable que se haya completado y que aún no se haya confirmado o compensado.</span><span class="sxs-lookup"><span data-stu-id="081f5-129">By default, if the workflow is canceled, the compensation logic is run for any compensable activity that has successfully completely and has not already been confirmed or compensated.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="081f5-130">Cuando <xref:System.Activities.Statements.CompensableActivity> se *confirma* un, ya no se puede invocar la compensación de la actividad.</span><span class="sxs-lookup"><span data-stu-id="081f5-130">When a <xref:System.Activities.Statements.CompensableActivity> is *confirmed*, compensation for the activity can no longer be invoked.</span></span> <span data-ttu-id="081f5-131">El proceso de confirmación se describe más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="081f5-131">The confirmation process is described later in this section.</span></span>  
  
 <span data-ttu-id="081f5-132">En este ejemplo, se inicia una excepción después de que se haya reservado el vuelo, aunque antes de que lo apruebe el administrador.</span><span class="sxs-lookup"><span data-stu-id="081f5-132">In this example, an exception is thrown after the flight is reserved but before the manager approval step.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#2](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#2)]  
  
 <span data-ttu-id="081f5-133">Este ejemplo es el flujo de trabajo en XAML.</span><span class="sxs-lookup"><span data-stu-id="081f5-133">This example is the workflow in XAML.</span></span>  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:SimulatedErrorCondition />  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 [!code-csharp[CFX_CompensationExample#100](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#100)]  
  
 <span data-ttu-id="081f5-134">Cuando se invoca el flujo de trabajo, la aplicación host administra la excepción de condiciones de error simulada en <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, el flujo de trabajo se cancela y se invoca la lógica de compensación.</span><span class="sxs-lookup"><span data-stu-id="081f5-134">When the workflow is invoked, the simulated error condition exception is handled by the host application in <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, the workflow is canceled, and the compensation logic is invoked.</span></span>  
  
 <span data-ttu-id="081f5-135">**ReserveFlight: Ticket is reserved.**</span><span class="sxs-lookup"><span data-stu-id="081f5-135">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="081f5-136">**SimulatedErrorCondition: iniciando ApplicationException.** 
 **Excepción no controlada del flujo de trabajo:** 
 **System. ApplicationException: condición de error simulada en el flujo de trabajo.** 
 **CancelFlight: vale cancelado.** 
 El **flujo de trabajo se completó correctamente con el estado: cancelado.**</span><span class="sxs-lookup"><span data-stu-id="081f5-136">**SimulatedErrorCondition: Throwing an ApplicationException.**
**Workflow Unhandled Exception:**
**System.ApplicationException: Simulated error condition in the workflow.**
**CancelFlight: Ticket is canceled.**
**Workflow completed successfully with status: Canceled.**</span></span>

### <a name="cancellation-and-compensableactivity"></a><span data-ttu-id="081f5-137">Cancelación y CompensableActivity</span><span class="sxs-lookup"><span data-stu-id="081f5-137">Cancellation and CompensableActivity</span></span>  

 <span data-ttu-id="081f5-138">Si las actividades de la propiedad <xref:System.Activities.Statements.CompensableActivity.Body%2A> de una clase <xref:System.Activities.Statements.CompensableActivity> no se han completado y la actividad se cancela, se ejecutan las actividades de la propiedad <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="081f5-138">If the activities in the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of a <xref:System.Activities.Statements.CompensableActivity> have not completed and the activity is canceled, the activities in the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> are executed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="081f5-139">La propiedad <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> solo se invoca si las actividades de la propiedad <xref:System.Activities.Statements.CompensableActivity.Body%2A> de la clase <xref:System.Activities.Statements.CompensableActivity> no se han completado y se cancela la actividad.</span><span class="sxs-lookup"><span data-stu-id="081f5-139">The <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> is only invoked if the activities in the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of the <xref:System.Activities.Statements.CompensableActivity> have not completed and the activity is canceled.</span></span> <span data-ttu-id="081f5-140">La propiedad <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> solo se ejecuta si las actividades de la propiedad <xref:System.Activities.Statements.CompensableActivity.Body%2A> de la clase <xref:System.Activities.Statements.CompensableActivity> se han completado correctamente y por lo tanto se invoca la compensación en la actividad.</span><span class="sxs-lookup"><span data-stu-id="081f5-140">The <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> is only executed if the activities in the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of the <xref:System.Activities.Statements.CompensableActivity> have successfully completed and compensation is subsequently invoked on the activity.</span></span>  
  
 <span data-ttu-id="081f5-141">La propiedad <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> permite a los autores del flujo de trabajo proporcionar una lógica de cancelación adecuada.</span><span class="sxs-lookup"><span data-stu-id="081f5-141">The <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> gives workflow authors the opportunity to provide any appropriate cancellation logic.</span></span> <span data-ttu-id="081f5-142">En el siguiente ejemplo se produce una excepción durante la ejecución de la clase <xref:System.Activities.Statements.CompensableActivity.Body%2A> y, a continuación, se invoca la propiedad <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="081f5-142">In the following example, an exception is thrown during the execution of the <xref:System.Activities.Statements.CompensableActivity.Body%2A>, and then the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> is invoked.</span></span>  
  
```csharp  
Activity wf = new Sequence()  
{  
    Activities =  
    {  
        new CompensableActivity  
        {  
            Body = new Sequence  
            {  
                Activities =
                {  
                    new ChargeCreditCard(),  
                    new SimulatedErrorCondition(),  
                    new ReserveFlight()  
                }  
            },  
            CompensationHandler = new CancelFlight(),  
            CancellationHandler = new CancelCreditCard()  
        },  
        new ManagerApproval(),  
        new PurchaseFlight()  
    }  
};  
```  
  
 <span data-ttu-id="081f5-143">Este ejemplo es el flujo de trabajo en XAML.</span><span class="sxs-lookup"><span data-stu-id="081f5-143">This example is the workflow in XAML</span></span>  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <Sequence>  
      <c:ChargeCreditCard />  
      <c:SimulatedErrorCondition />  
      <c:ReserveFlight />  
    </Sequence>  
    <CompensableActivity.CancellationHandler>  
      <c:CancelCreditCard />  
    </CompensableActivity.CancellationHandler>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 <span data-ttu-id="081f5-144">Cuando se invoca el flujo de trabajo, la aplicación host administra la excepción de condiciones de error simulada en <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, el flujo de trabajo se cancela y se invoca la lógica de cancelación de la clase <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="081f5-144">When the workflow is invoked, the simulated error condition exception is handled by the host application in <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, the workflow is canceled, and the cancellation logic of the <xref:System.Activities.Statements.CompensableActivity> is invoked.</span></span> <span data-ttu-id="081f5-145">En este ejemplo, la lógica de la compensación y la lógica de cancelación tienen distintos objetivos.</span><span class="sxs-lookup"><span data-stu-id="081f5-145">In this example, the compensation logic and the cancellation logic have different goals.</span></span> <span data-ttu-id="081f5-146">Si <xref:System.Activities.Statements.CompensableActivity.Body%2A> se completó correctamente, significa que la tarjeta de crédito se cargó y el vuelo se reservó, por lo que la compensación debe deshacer ambos pasos.</span><span class="sxs-lookup"><span data-stu-id="081f5-146">If the <xref:System.Activities.Statements.CompensableActivity.Body%2A> completed successfully, then this means the credit card was charged and the flight booked, so the compensation should undo both steps.</span></span> <span data-ttu-id="081f5-147">(En este ejemplo, al cancelar el vuelo se cancelan automáticamente los cargos de la tarjeta de crédito). Sin embargo, si <xref:System.Activities.Statements.CompensableActivity> se cancela, esto significa que <xref:System.Activities.Statements.CompensableActivity.Body%2A> no se completó y que la lógica de <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> debe ser capaz de determinar cómo administrar mejor la cancelación.</span><span class="sxs-lookup"><span data-stu-id="081f5-147">(In this example, canceling the flight automatically cancels the credit card charges.) However, if the <xref:System.Activities.Statements.CompensableActivity> is canceled, this means the <xref:System.Activities.Statements.CompensableActivity.Body%2A> did not complete and so the logic of the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> needs to be able to determine how to best handle the cancellation.</span></span> <span data-ttu-id="081f5-148">En este ejemplo, <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> cancela el cargo de la tarjeta de crédito, pero como `ReserveFlight` era la última actividad de <xref:System.Activities.Statements.CompensableActivity.Body%2A>, no intenta cancelar el vuelo.</span><span class="sxs-lookup"><span data-stu-id="081f5-148">In this example, the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> cancels the credit card charge, but since `ReserveFlight` was the last activity in the <xref:System.Activities.Statements.CompensableActivity.Body%2A>, it does not attempt to cancel the flight.</span></span> <span data-ttu-id="081f5-149">Puesto que `ReserveFlight` era la última actividad de <xref:System.Activities.Statements.CompensableActivity.Body%2A>, si se hubiera realizado correctamente <xref:System.Activities.Statements.CompensableActivity.Body%2A> se habría completado y no sería posible la cancelación.</span><span class="sxs-lookup"><span data-stu-id="081f5-149">Since `ReserveFlight` was the last activity in the <xref:System.Activities.Statements.CompensableActivity.Body%2A>, if it had successfully completed then the <xref:System.Activities.Statements.CompensableActivity.Body%2A> would have completed and no cancellation would be possible.</span></span>  
  
 <span data-ttu-id="081f5-150">**ChargeCreditCard: cargar el vuelo a la tarjeta de crédito.**</span><span class="sxs-lookup"><span data-stu-id="081f5-150">**ChargeCreditCard: Charge credit card for flight.**</span></span>  
<span data-ttu-id="081f5-151">**SimulatedErrorCondition: iniciando ApplicationException.** 
 **Excepción no controlada del flujo de trabajo:** 
 **System. ApplicationException: condición de error simulada en el flujo de trabajo.** 
 **CancelCreditCard: cancelar los cargos de la tarjeta de crédito.** 
 El **flujo de trabajo se completó correctamente con el estado: cancelado.**</span><span class="sxs-lookup"><span data-stu-id="081f5-151">**SimulatedErrorCondition: Throwing an ApplicationException.**
**Workflow Unhandled Exception:**
**System.ApplicationException: Simulated error condition in the workflow.**
**CancelCreditCard: Cancel credit card charges.**
**Workflow completed successfully with status: Canceled.**</span></span>  <span data-ttu-id="081f5-152">Para obtener más información sobre la cancelación, vea [cancelación](modeling-cancellation-behavior-in-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="081f5-152">For more information about cancellation, see [Cancellation](modeling-cancellation-behavior-in-workflows.md).</span></span>  
  
### <a name="explicit-compensation-using-the-compensate-activity"></a><span data-ttu-id="081f5-153">Compensación explícita usando la actividad Compensate</span><span class="sxs-lookup"><span data-stu-id="081f5-153">Explicit Compensation Using the Compensate Activity</span></span>  

 <span data-ttu-id="081f5-154">En la sección anterior, se describió la compensación implícita.</span><span class="sxs-lookup"><span data-stu-id="081f5-154">In the previous section, implicit compensation was covered.</span></span> <span data-ttu-id="081f5-155">La compensación implícita puede ser adecuada para escenarios simples, pero si es necesario un mayor control sobre la programación de la administración de la compensación, se podrá usar la actividad <xref:System.Activities.Statements.Compensate>.</span><span class="sxs-lookup"><span data-stu-id="081f5-155">Implicit compensation can be appropriate for simple scenarios, but if more explicit control is required over the scheduling of compensation handling then the <xref:System.Activities.Statements.Compensate> activity can be used.</span></span> <span data-ttu-id="081f5-156">Para iniciar el proceso de compensación con la actividad <xref:System.Activities.Statements.Compensate>, se usa la clase <xref:System.Activities.Statements.CompensationToken> de la clase <xref:System.Activities.Statements.CompensableActivity> para la que se desea la compensación.</span><span class="sxs-lookup"><span data-stu-id="081f5-156">To initiate the compensation process with the <xref:System.Activities.Statements.Compensate> activity, the <xref:System.Activities.Statements.CompensationToken> of the <xref:System.Activities.Statements.CompensableActivity> for which compensation is desired is used.</span></span> <span data-ttu-id="081f5-157">Se puede usar la actividad <xref:System.Activities.Statements.Compensate> para iniciar la compensación en cualquier <xref:System.Activities.Statements.CompensableActivity> completada que no se haya confirmado o compensado.</span><span class="sxs-lookup"><span data-stu-id="081f5-157">The <xref:System.Activities.Statements.Compensate> activity can be used to initiate compensation on any completed <xref:System.Activities.Statements.CompensableActivity> that has not been confirmed or compensated.</span></span> <span data-ttu-id="081f5-158">Por ejemplo, se puede usar una actividad <xref:System.Activities.Statements.Compensate> en la sección <xref:System.Activities.Statements.TryCatch.Catches%2A> de una actividad <xref:System.Activities.Statements.TryCatch> o cuando desee después de que <xref:System.Activities.Statements.CompensableActivity> se haya completado.</span><span class="sxs-lookup"><span data-stu-id="081f5-158">For example, a <xref:System.Activities.Statements.Compensate> activity could be used in the <xref:System.Activities.Statements.TryCatch.Catches%2A> section of a <xref:System.Activities.Statements.TryCatch> activity, or any time after the <xref:System.Activities.Statements.CompensableActivity> has completed.</span></span> <span data-ttu-id="081f5-159">En este ejemplo, la actividad <xref:System.Activities.Statements.Compensate> se usa en la sección <xref:System.Activities.Statements.TryCatch.Catches%2A> de una actividad <xref:System.Activities.Statements.TryCatch> para invertir la acción de <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="081f5-159">In this example, the <xref:System.Activities.Statements.Compensate> activity is used in the <xref:System.Activities.Statements.TryCatch.Catches%2A> section of a <xref:System.Activities.Statements.TryCatch> activity to reverse the action of the <xref:System.Activities.Statements.CompensableActivity>.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#3](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#3)]  
  
 <span data-ttu-id="081f5-160">Este ejemplo es el flujo de trabajo en XAML.</span><span class="sxs-lookup"><span data-stu-id="081f5-160">This example is the workflow in XAML.</span></span>  
  
```xaml  
<TryCatch  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:s="clr-namespace:System;assembly=mscorlib"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <TryCatch.Variables>  
    <Variable  
       x:TypeArguments="CompensationToken"  
       x:Name="__ReferenceID0"  
       Name="token1" />  
  </TryCatch.Variables>  
  <TryCatch.Try>  
    <Sequence>  
      <CompensableActivity>  
        <CompensableActivity.Result>  
          <OutArgument  
             x:TypeArguments="CompensationToken">  
            <VariableReference  
               x:TypeArguments="CompensationToken"  
               Variable="{x:Reference __ReferenceID0}">  
              <VariableReference.Result>  
                <OutArgument  
                   x:TypeArguments="Location(CompensationToken)" />  
              </VariableReference.Result>  
            </VariableReference>  
          </OutArgument>  
        </CompensableActivity.Result>  
        <CompensableActivity.CompensationHandler>  
          <c:CancelFlight />  
        </CompensableActivity.CompensationHandler>  
        <CompensableActivity.ConfirmationHandler>  
          <c:ConfirmFlight />  
        </CompensableActivity.ConfirmationHandler>  
        <c:ReserveFlight />  
      </CompensableActivity>  
      <c:SimulatedErrorCondition />  
      <c:ManagerApproval />  
      <c:PurchaseFlight />  
    </Sequence>  
  </TryCatch.Try>  
  <TryCatch.Catches>  
    <Catch  
       x:TypeArguments="s:ApplicationException">  
      <ActivityAction  
         x:TypeArguments="s:ApplicationException">  
        <Compensate>  
          <Compensate.Target>  
            <InArgument  
               x:TypeArguments="CompensationToken">  
              <VariableValue  
                 x:TypeArguments="CompensationToken"  
                 Variable="{x:Reference __ReferenceID0}">  
                <VariableValue.Result>  
                  <OutArgument  
                     x:TypeArguments="CompensationToken" />  
                </VariableValue.Result>  
              </VariableValue>  
            </InArgument>  
          </Compensate.Target>  
        </Compensate>  
      </ActivityAction>  
    </Catch>  
  </TryCatch.Catches>  
</TryCatch>  
```  
  
 <span data-ttu-id="081f5-161">Cuando se invoca el flujo de trabajo, en la consola se muestra el siguiente resultado.</span><span class="sxs-lookup"><span data-stu-id="081f5-161">When the workflow is invoked, the following output is displayed to the console.</span></span>  
  
 <span data-ttu-id="081f5-162">**ReserveFlight: Ticket is reserved.**</span><span class="sxs-lookup"><span data-stu-id="081f5-162">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="081f5-163">**SimulatedErrorCondition: iniciando ApplicationException.** 
 **CancelFlight: vale cancelado.** 
 El **flujo de trabajo se completó correctamente con el estado: cerrado.**</span><span class="sxs-lookup"><span data-stu-id="081f5-163">**SimulatedErrorCondition: Throwing an ApplicationException.**
**CancelFlight: Ticket is canceled.**
**Workflow completed successfully with status: Closed.**</span></span>

### <a name="confirming-compensation"></a><span data-ttu-id="081f5-164">Confirmar compensación</span><span class="sxs-lookup"><span data-stu-id="081f5-164">Confirming Compensation</span></span>  

 <span data-ttu-id="081f5-165">De forma predeterminada, las actividades pueden compensarse en cualquier momento después de que se hayan completado.</span><span class="sxs-lookup"><span data-stu-id="081f5-165">By default, compensable activities can be compensated any time after they have completed.</span></span> <span data-ttu-id="081f5-166">Sin embargo, en algunos escenarios es posible que no convenga hacerlo.</span><span class="sxs-lookup"><span data-stu-id="081f5-166">In some scenarios this may not be appropriate.</span></span> <span data-ttu-id="081f5-167">En el ejemplo anterior la compensación para reservar el vale fue cancelar la reserva.</span><span class="sxs-lookup"><span data-stu-id="081f5-167">In the previous example the compensation to reserving the ticket was to cancel the reservation.</span></span> <span data-ttu-id="081f5-168">No obstante, una vez que se haya completado el vuelo, la compensación dejará de tener validez.</span><span class="sxs-lookup"><span data-stu-id="081f5-168">However, after the flight has been completed this compensation step is no longer valid.</span></span> <span data-ttu-id="081f5-169">Al confirmar la actividad compensable, se invoca la actividad especificada por la propiedad <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="081f5-169">Confirming the compensable activity invokes the activity specified by the <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>.</span></span> <span data-ttu-id="081f5-170">Un posible uso de ello es permitir cualquier recurso que sea necesario para realizar la compensación que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="081f5-170">One possible use for this is to allow any resources that are necessary to perform the compensation to be released.</span></span> <span data-ttu-id="081f5-171">Una vez confirmada la actividad compensable, no es posible compensarla y, si se intentara, se iniciaría una excepción <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="081f5-171">After a compensable activity is confirmed it is not possible for it to be compensated, and if this is attempted an <xref:System.InvalidOperationException> exception is thrown.</span></span> <span data-ttu-id="081f5-172">Cuando un flujo de trabajo se completa, todas las actividades compensables no confirmadas y no compensadas que se hayan completado se confirmarán en el orden inverso de la finalización.</span><span class="sxs-lookup"><span data-stu-id="081f5-172">When a workflow completes successfully, all non-confirmed and non-compensated compensable activities that completed successfully are confirmed in reverse order of completion.</span></span> <span data-ttu-id="081f5-173">En este ejemplo, el vuelo se reserva, se compra y se completa y, a continuación, se confirma la actividad compensable.</span><span class="sxs-lookup"><span data-stu-id="081f5-173">In this example the flight is reserved, purchased, and completed, and then the compensable activity is confirmed.</span></span> <span data-ttu-id="081f5-174">Para confirmar <xref:System.Activities.Statements.CompensableActivity>, use la actividad <xref:System.Activities.Statements.Confirm> y especifique la clase <xref:System.Activities.Statements.CompensationToken> de la clase <xref:System.Activities.Statements.CompensableActivity> para confirmar.</span><span class="sxs-lookup"><span data-stu-id="081f5-174">To confirm a <xref:System.Activities.Statements.CompensableActivity>, use the <xref:System.Activities.Statements.Confirm> activity and specify the <xref:System.Activities.Statements.CompensationToken> of the <xref:System.Activities.Statements.CompensableActivity> to confirm.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#4](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#4)]  
  
 <span data-ttu-id="081f5-175">Este ejemplo es el flujo de trabajo en XAML.</span><span class="sxs-lookup"><span data-stu-id="081f5-175">This example is the workflow in XAML.</span></span>  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <Sequence.Variables>  
    <x:Reference>__ReferenceID0</x:Reference>  
  </Sequence.Variables>  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken">  
        <VariableReference  
           x:TypeArguments="CompensationToken">  
          <VariableReference.Result>  
            <OutArgument  
               x:TypeArguments="Location(CompensationToken)" />  
          </VariableReference.Result>  
          <VariableReference.Variable>  
            <Variable  
               x:TypeArguments="CompensationToken"  
               x:Name="__ReferenceID0"  
               Name="token1" />  
          </VariableReference.Variable>  
        </VariableReference>  
      </OutArgument>  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <CompensableActivity.ConfirmationHandler>  
      <c:ConfirmFlight />  
    </CompensableActivity.ConfirmationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
  <c:TakeFlight />  
  <Confirm>  
    <Confirm.Target>  
      <InArgument  
         x:TypeArguments="CompensationToken">  
        <VariableValue  
           x:TypeArguments="CompensationToken"  
           Variable="{x:Reference __ReferenceID0}">  
          <VariableValue.Result>  
            <OutArgument  
               x:TypeArguments="CompensationToken" />  
          </VariableValue.Result>  
        </VariableValue>  
      </InArgument>  
    </Confirm.Target>  
  </Confirm>  
</Sequence>  
```  
  
<span data-ttu-id="081f5-176">Cuando se invoca el flujo de trabajo, en la consola se muestra el siguiente resultado.</span><span class="sxs-lookup"><span data-stu-id="081f5-176">When the workflow is invoked, the following output is displayed to the console.</span></span>  
  
<span data-ttu-id="081f5-177">**ReserveFlight: Ticket is reserved.**</span><span class="sxs-lookup"><span data-stu-id="081f5-177">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="081f5-178">**ManagerApproval: aprobación del administrador recibida.** 
 **PurchaseFlight: vale adquirido.** 
 **TakeFlight: se completó el vuelo.** 
 **ConfirmFlight: se ha tomado el vuelo, no se puede realizar ninguna compensación.** 
 El **flujo de trabajo se completó correctamente con el estado: cerrado.**</span><span class="sxs-lookup"><span data-stu-id="081f5-178">**ManagerApproval: Manager approval received.**
**PurchaseFlight: Ticket is purchased.**
**TakeFlight: Flight is completed.**
**ConfirmFlight: Flight has been taken, no compensation possible.**
**Workflow completed successfully with status: Closed.**</span></span>

## <a name="nesting-compensation-activities"></a><span data-ttu-id="081f5-179">Anidar las actividades de compensación</span><span class="sxs-lookup"><span data-stu-id="081f5-179">Nesting Compensation Activities</span></span>  

<span data-ttu-id="081f5-180"><xref:System.Activities.Statements.CompensableActivity> se puede colocar en la sección <xref:System.Activities.Statements.CompensableActivity.Body%2A> de otra <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="081f5-180">A <xref:System.Activities.Statements.CompensableActivity> can be placed into the <xref:System.Activities.Statements.CompensableActivity.Body%2A> section of another <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="081f5-181"><xref:System.Activities.Statements.CompensableActivity> no se puede colocar en un controlador de otra <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="081f5-181">A <xref:System.Activities.Statements.CompensableActivity> may not be placed into a handler of another <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="081f5-182">Es responsabilidad de un elemento primario <xref:System.Activities.Statements.CompensableActivity> garantizar que cuando se cancela, confirma o compensa, todas las actividades compensables secundarias que se hayan completado correctamente y que no se hayan confirmado o compensado todavía se deben confirmar o compensar antes de que el elemento primario complete la cancelación, la confirmación o la compensación.</span><span class="sxs-lookup"><span data-stu-id="081f5-182">It is the responsibility of a parent <xref:System.Activities.Statements.CompensableActivity> to ensure that when it is canceled, confirmed, or compensated, all child compensable activities that have completed successfully and have not already been confirmed or compensated must be confirmed or compensated before the parent completes cancellation, confirmation, or compensation.</span></span> <span data-ttu-id="081f5-183">Si esto no se modeló explícitamente, la <xref:System.Activities.Statements.CompensableActivity> primaria compensará implícitamente las actividades compensables secundarias si el elemento primario recibió la señal de cancelación o compensación.</span><span class="sxs-lookup"><span data-stu-id="081f5-183">If this is not modeled explicitly the parent <xref:System.Activities.Statements.CompensableActivity> will implicitly compensate child compensable activities if the parent received the cancel or compensate signal.</span></span> <span data-ttu-id="081f5-184">Si el elemento primario recibió la señal de confirmación, el elemento primario confirmará implícitamente las actividades compensables secundarias.</span><span class="sxs-lookup"><span data-stu-id="081f5-184">If the parent received the confirm signal the parent will implicitly confirm child compensable activities.</span></span> <span data-ttu-id="081f5-185">Si la lógica para controlar la cancelación, confirmación o compensación se modela explícitamente en el controlador de la <xref:System.Activities.Statements.CompensableActivity> primaria, cualquier elemento secundario no controlado explícitamente se confirmará implícitamente.</span><span class="sxs-lookup"><span data-stu-id="081f5-185">If the logic to handle cancellation, confirmation, or compensation is explicitly modeled in the handler of the parent <xref:System.Activities.Statements.CompensableActivity>, any child not explicitly handled will be implicitly confirmed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="081f5-186">Vea también</span><span class="sxs-lookup"><span data-stu-id="081f5-186">See also</span></span>

- <xref:System.Activities.Statements.CompensableActivity>
- <xref:System.Activities.Statements.Compensate>
- <xref:System.Activities.Statements.Confirm>
- <xref:System.Activities.Statements.CompensationToken>
