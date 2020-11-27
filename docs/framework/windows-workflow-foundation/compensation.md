---
title: Compensación
ms.date: 03/30/2017
ms.assetid: 722e9766-48d7-456c-9496-d7c5c8f0fa76
ms.openlocfilehash: 60e2789c4bbd29185af50eaf6555307b894d3902
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289196"
---
# <a name="compensation"></a>Compensación

La compensación en Windows Workflow Foundation (WF) es el mecanismo por el que se puede deshacer o compensar el trabajo previamente completado (siguiendo la lógica definida por la aplicación) cuando se produce un error posterior. Esta sección describe cómo usar la compensación en los flujos de trabajo.  
  
## <a name="compensation-vs-transactions"></a>Compensación en comparación con transacciones  

 Las transacciones permiten combinar varias operaciones en una sola unidad de trabajo. El uso de una transacción le da a la aplicación la posibilidad de anular (revertir) todos los cambios ejecutados desde dentro de la transacción si se produce algún error en algún momento del proceso de transacción. Sin embargo, el uso de las transacciones puede que no sea adecuado si el trabajo se está ejecutando mucho tiempo. Por ejemplo, se implementa una aplicación que planea un viaje como un flujo de trabajo. Los pasos del flujo de trabajo pueden consistir en la reserva de un vuelo, la espera de la aprobación del administrador y, a continuación, el pago del vuelo. Este proceso podría tardar muchos días y no es práctico que los pasos de reservar y pagar el vuelo formen parte de la misma transacción. En un escenario como este, se podría usar la compensación para deshacer el paso de la reserva del flujo de trabajo si se produce un error posterior durante el procesamiento.  
  
> [!NOTE]
> Este tema trata la compensación en flujos de trabajo. Para obtener más información sobre las transacciones en flujos de trabajo, vea [transacciones](workflow-transactions.md) y <xref:System.Activities.Statements.TransactionScope> . Para obtener más información acerca de las transacciones, vea <xref:System.Transactions?displayProperty=nameWithType> y <xref:System.Transactions.Transaction?displayProperty=nameWithType> .  
  
## <a name="using-compensableactivity"></a>Usar CompensableActivity  

 <xref:System.Activities.Statements.CompensableActivity> es la actividad de compensación principal en [!INCLUDE[wf1](../../../includes/wf1-md.md)]. Cualquier actividad que realice un trabajo que cabe la posibilidad de que deba compensarse se coloca en la propiedad <xref:System.Activities.Statements.CompensableActivity.Body%2A> de la clase <xref:System.Activities.Statements.CompensableActivity>. En este ejemplo, el paso de la reserva de compra de un vuelo se encuentra en la propiedad <xref:System.Activities.Statements.CompensableActivity.Body%2A> de una clase <xref:System.Activities.Statements.CompensableActivity> y la cancelación de la reserva está en la propiedad <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>. Justo después de <xref:System.Activities.Statements.CompensableActivity> en el flujo de trabajo hay dos actividades que esperan la aprobación del administrador y, a continuación, se completa la compra del vuelo. Si una condición de error provoca la cancelación del flujo de trabajo después de que la clase <xref:System.Activities.Statements.CompensableActivity> se haya completado correctamente, las actividades del controlador <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> se programan y el vuelo se cancela.  
  
 [!code-csharp[CFX_CompensationExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#1)]  
  
 El siguiente ejemplo es el flujo de trabajo en XAML.  
  
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
  
 Cuando se invoca el flujo de trabajo, en la consola se muestra el siguiente resultado.  
  
 **ReserveFlight: Ticket is reserved.**  
**ManagerApproval: aprobación del administrador recibida.** 
 **PurchaseFlight: vale adquirido.** 
 El **flujo de trabajo se completó correctamente con el estado: cerrado.**
> [!NOTE]
> Las actividades de ejemplo de este tema como `ReserveFlight` muestran su nombre y propósito a la consola para ayudar a mostrar el orden en el que se ejecutan las actividades cuando se produce la compensación.  
  
### <a name="default-workflow-compensation"></a>Compensación predeterminada del flujo de trabajo  

 De forma predeterminada, si se cancela el flujo de trabajo, se ejecuta la lógica de compensación para cualquier actividad compensable que se haya completado y que aún no se haya confirmado o compensado.  
  
> [!NOTE]
> Cuando <xref:System.Activities.Statements.CompensableActivity> se *confirma* un, ya no se puede invocar la compensación de la actividad. El proceso de confirmación se describe más adelante en esta sección.  
  
 En este ejemplo, se inicia una excepción después de que se haya reservado el vuelo, aunque antes de que lo apruebe el administrador.  
  
 [!code-csharp[CFX_CompensationExample#2](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#2)]  
  
 Este ejemplo es el flujo de trabajo en XAML.  
  
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
  
 Cuando se invoca el flujo de trabajo, la aplicación host administra la excepción de condiciones de error simulada en <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, el flujo de trabajo se cancela y se invoca la lógica de compensación.  
  
 **ReserveFlight: Ticket is reserved.**  
**SimulatedErrorCondition: iniciando ApplicationException.** 
 **Excepción no controlada del flujo de trabajo:** 
 **System. ApplicationException: condición de error simulada en el flujo de trabajo.** 
 **CancelFlight: vale cancelado.** 
 El **flujo de trabajo se completó correctamente con el estado: cancelado.**

### <a name="cancellation-and-compensableactivity"></a>Cancelación y CompensableActivity  

 Si las actividades de la propiedad <xref:System.Activities.Statements.CompensableActivity.Body%2A> de una clase <xref:System.Activities.Statements.CompensableActivity> no se han completado y la actividad se cancela, se ejecutan las actividades de la propiedad <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>.  
  
> [!NOTE]
> La propiedad <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> solo se invoca si las actividades de la propiedad <xref:System.Activities.Statements.CompensableActivity.Body%2A> de la clase <xref:System.Activities.Statements.CompensableActivity> no se han completado y se cancela la actividad. La propiedad <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> solo se ejecuta si las actividades de la propiedad <xref:System.Activities.Statements.CompensableActivity.Body%2A> de la clase <xref:System.Activities.Statements.CompensableActivity> se han completado correctamente y por lo tanto se invoca la compensación en la actividad.  
  
 La propiedad <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> permite a los autores del flujo de trabajo proporcionar una lógica de cancelación adecuada. En el siguiente ejemplo se produce una excepción durante la ejecución de la clase <xref:System.Activities.Statements.CompensableActivity.Body%2A> y, a continuación, se invoca la propiedad <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>.  
  
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
  
 Este ejemplo es el flujo de trabajo en XAML.  
  
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
  
 Cuando se invoca el flujo de trabajo, la aplicación host administra la excepción de condiciones de error simulada en <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, el flujo de trabajo se cancela y se invoca la lógica de cancelación de la clase <xref:System.Activities.Statements.CompensableActivity>. En este ejemplo, la lógica de la compensación y la lógica de cancelación tienen distintos objetivos. Si <xref:System.Activities.Statements.CompensableActivity.Body%2A> se completó correctamente, significa que la tarjeta de crédito se cargó y el vuelo se reservó, por lo que la compensación debe deshacer ambos pasos. (En este ejemplo, al cancelar el vuelo se cancelan automáticamente los cargos de la tarjeta de crédito). Sin embargo, si <xref:System.Activities.Statements.CompensableActivity> se cancela, esto significa que <xref:System.Activities.Statements.CompensableActivity.Body%2A> no se completó y que la lógica de <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> debe ser capaz de determinar cómo administrar mejor la cancelación. En este ejemplo, <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> cancela el cargo de la tarjeta de crédito, pero como `ReserveFlight` era la última actividad de <xref:System.Activities.Statements.CompensableActivity.Body%2A>, no intenta cancelar el vuelo. Puesto que `ReserveFlight` era la última actividad de <xref:System.Activities.Statements.CompensableActivity.Body%2A>, si se hubiera realizado correctamente <xref:System.Activities.Statements.CompensableActivity.Body%2A> se habría completado y no sería posible la cancelación.  
  
 **ChargeCreditCard: cargar el vuelo a la tarjeta de crédito.**  
**SimulatedErrorCondition: iniciando ApplicationException.** 
 **Excepción no controlada del flujo de trabajo:** 
 **System. ApplicationException: condición de error simulada en el flujo de trabajo.** 
 **CancelCreditCard: cancelar los cargos de la tarjeta de crédito.** 
 El **flujo de trabajo se completó correctamente con el estado: cancelado.**  Para obtener más información sobre la cancelación, vea [cancelación](modeling-cancellation-behavior-in-workflows.md).  
  
### <a name="explicit-compensation-using-the-compensate-activity"></a>Compensación explícita usando la actividad Compensate  

 En la sección anterior, se describió la compensación implícita. La compensación implícita puede ser adecuada para escenarios simples, pero si es necesario un mayor control sobre la programación de la administración de la compensación, se podrá usar la actividad <xref:System.Activities.Statements.Compensate>. Para iniciar el proceso de compensación con la actividad <xref:System.Activities.Statements.Compensate>, se usa la clase <xref:System.Activities.Statements.CompensationToken> de la clase <xref:System.Activities.Statements.CompensableActivity> para la que se desea la compensación. Se puede usar la actividad <xref:System.Activities.Statements.Compensate> para iniciar la compensación en cualquier <xref:System.Activities.Statements.CompensableActivity> completada que no se haya confirmado o compensado. Por ejemplo, se puede usar una actividad <xref:System.Activities.Statements.Compensate> en la sección <xref:System.Activities.Statements.TryCatch.Catches%2A> de una actividad <xref:System.Activities.Statements.TryCatch> o cuando desee después de que <xref:System.Activities.Statements.CompensableActivity> se haya completado. En este ejemplo, la actividad <xref:System.Activities.Statements.Compensate> se usa en la sección <xref:System.Activities.Statements.TryCatch.Catches%2A> de una actividad <xref:System.Activities.Statements.TryCatch> para invertir la acción de <xref:System.Activities.Statements.CompensableActivity>.  
  
 [!code-csharp[CFX_CompensationExample#3](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#3)]  
  
 Este ejemplo es el flujo de trabajo en XAML.  
  
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
  
 Cuando se invoca el flujo de trabajo, en la consola se muestra el siguiente resultado.  
  
 **ReserveFlight: Ticket is reserved.**  
**SimulatedErrorCondition: iniciando ApplicationException.** 
 **CancelFlight: vale cancelado.** 
 El **flujo de trabajo se completó correctamente con el estado: cerrado.**

### <a name="confirming-compensation"></a>Confirmar compensación  

 De forma predeterminada, las actividades pueden compensarse en cualquier momento después de que se hayan completado. Sin embargo, en algunos escenarios es posible que no convenga hacerlo. En el ejemplo anterior la compensación para reservar el vale fue cancelar la reserva. No obstante, una vez que se haya completado el vuelo, la compensación dejará de tener validez. Al confirmar la actividad compensable, se invoca la actividad especificada por la propiedad <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>. Un posible uso de ello es permitir cualquier recurso que sea necesario para realizar la compensación que se va a liberar. Una vez confirmada la actividad compensable, no es posible compensarla y, si se intentara, se iniciaría una excepción <xref:System.InvalidOperationException>. Cuando un flujo de trabajo se completa, todas las actividades compensables no confirmadas y no compensadas que se hayan completado se confirmarán en el orden inverso de la finalización. En este ejemplo, el vuelo se reserva, se compra y se completa y, a continuación, se confirma la actividad compensable. Para confirmar <xref:System.Activities.Statements.CompensableActivity>, use la actividad <xref:System.Activities.Statements.Confirm> y especifique la clase <xref:System.Activities.Statements.CompensationToken> de la clase <xref:System.Activities.Statements.CompensableActivity> para confirmar.  
  
 [!code-csharp[CFX_CompensationExample#4](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#4)]  
  
 Este ejemplo es el flujo de trabajo en XAML.  
  
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
  
Cuando se invoca el flujo de trabajo, en la consola se muestra el siguiente resultado.  
  
**ReserveFlight: Ticket is reserved.**  
**ManagerApproval: aprobación del administrador recibida.** 
 **PurchaseFlight: vale adquirido.** 
 **TakeFlight: se completó el vuelo.** 
 **ConfirmFlight: se ha tomado el vuelo, no se puede realizar ninguna compensación.** 
 El **flujo de trabajo se completó correctamente con el estado: cerrado.**

## <a name="nesting-compensation-activities"></a>Anidar las actividades de compensación  

<xref:System.Activities.Statements.CompensableActivity> se puede colocar en la sección <xref:System.Activities.Statements.CompensableActivity.Body%2A> de otra <xref:System.Activities.Statements.CompensableActivity>. <xref:System.Activities.Statements.CompensableActivity> no se puede colocar en un controlador de otra <xref:System.Activities.Statements.CompensableActivity>. Es responsabilidad de un elemento primario <xref:System.Activities.Statements.CompensableActivity> garantizar que cuando se cancela, confirma o compensa, todas las actividades compensables secundarias que se hayan completado correctamente y que no se hayan confirmado o compensado todavía se deben confirmar o compensar antes de que el elemento primario complete la cancelación, la confirmación o la compensación. Si esto no se modeló explícitamente, la <xref:System.Activities.Statements.CompensableActivity> primaria compensará implícitamente las actividades compensables secundarias si el elemento primario recibió la señal de cancelación o compensación. Si el elemento primario recibió la señal de confirmación, el elemento primario confirmará implícitamente las actividades compensables secundarias. Si la lógica para controlar la cancelación, confirmación o compensación se modela explícitamente en el controlador de la <xref:System.Activities.Statements.CompensableActivity> primaria, cualquier elemento secundario no controlado explícitamente se confirmará implícitamente.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Activities.Statements.CompensableActivity>
- <xref:System.Activities.Statements.Compensate>
- <xref:System.Activities.Statements.Confirm>
- <xref:System.Activities.Statements.CompensationToken>
