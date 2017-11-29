---
title: "Crear actividades asincrónicas en WF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 497e81ed-5eef-460c-ba55-fae73c05824f
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f2fd247348050b8335f4f6354c88664d497dbbf2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="creating-asynchronous-activities-in-wf"></a>Crear actividades asincrónicas en WF
<xref:System.Activities.AsyncCodeActivity> proporciona a los autores de actividad el uso de una clase base que permite a las actividades derivadas implementar la lógica de ejecución asincrónica. Resulta útil para las actividades personalizadas que deben realizar el trabajo asincrónico sin retener el subproceso de programador de flujo de trabajo y bloquear cualquier actividad que pueda ejecutarse en paralelo. En este tema se proporciona información general de cómo crear actividades asincrónicas personalizadas mediante <xref:System.Activities.AsyncCodeActivity>.  
  
## <a name="using-asynccodeactivity"></a>Usar AsyncCodeActivity  
 <xref:System.Activities?displayProperty=nameWithType> proporciona a los autores de actividad personalizada clases base diferentes para distintos requisitos de creación de actividades. Cada uno posee una semántica particular y proporciona al autor del flujo de trabajo (y al tiempo de ejecución de la actividad) el contrato correspondiente. Una actividad basada en <xref:System.Activities.AsyncCodeActivity> es aquélla que realiza el trabajo de manera asincrónica según el subproceso del programador y cuya lógica de ejecución se expresa en código administrado. Como resultado de la asincronía, <xref:System.Activities.AsyncCodeActivity> puede inducir un punto inactivo durante la ejecución. Debido a la naturaleza volátil del trabajo asincrónico, <xref:System.Activities.AsyncCodeActivity> crea siempre un bloque de no persistencia durante la ejecución de la actividad. Esto evita que el tiempo de ejecución del flujo de trabajo conserve la instancia de flujo de trabajo en medio del trabajo asincrónico y también evita que la instancia de flujo de trabajo se descargue mientras el código asincrónico se está ejecutando.  
  
### <a name="asynccodeactivity-methods"></a>Métodos AsyncCodeActivity  
 Las actividades que derivan de <xref:System.Activities.AsyncCodeActivity> pueden crear la lógica de ejecución asincrónica reemplazando los métodos <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> y <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> con código personalizado. Cuando los llama el tiempo de ejecución, se pasa un <xref:System.Activities.AsyncCodeActivityContext> a estos métodos. <xref:System.Activities.AsyncCodeActivityContext>permite al autor de actividad proporcione al estado compartido a través de <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> /  <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> en el contexto <xref:System.Activities.AsyncCodeActivityContext.UserState%2A> propiedad. En el siguiente ejemplo, una actividad `GenerateRandom` genera un número aleatorio de forma asincrónica.  
  
 [!code-csharp[CFX_ActivityExample#8](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#8)]  
  
 La actividad de ejemplo anterior deriva de <xref:System.Activities.AsyncCodeActivity%601>y tiene un `OutArgument<int>` elevado denominado `Result`. El valor devuelto por el método `GetRandom` se extrae y, a su vez, lo devuelve el reemplazo del <xref:System.Activities.AsyncCodeActivity%601.EndExecute%2A>. Este valor se establece como el valor `Result`. Las actividades asincrónicas que no devuelvan un resultado deberían derivar de <xref:System.Activities.AsyncCodeActivity>. En el siguiente ejemplo, se define una actividad `DisplayRandom` que deriva de <xref:System.Activities.AsyncCodeActivity>. Esta actividad es similar a la actividad `GetRandom`, pero en lugar de devolver un resultado muestra un mensaje en la consola.  
  
 [!code-csharp[CFX_ActivityExample#11](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#11)]  
  
 Tenga en cuenta que dado que no hay ningún valor devuelto, `DisplayRandom` utiliza <xref:System.Action> en lugar de <xref:System.Func%602> para invocar su delegado y el delegado no devuelve ningún valor.  
  
 <xref:System.Activities.AsyncCodeActivity> también proporciona el reemplazo de <xref:System.Activities.AsyncCodeActivity.Cancel%2A>. Aunque <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> y <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> son reemplazos necesarios, <xref:System.Activities.AsyncCodeActivity.Cancel%2A> es opcional y puede reemplazarse de manera que la actividad pueda limpiar el estado asincrónico pendiente cuando se cancele o anule. Si la limpieza es posible y `AsyncCodeActivity.ExecutingActivityInstance.IsCancellationRequested` es `true`, la actividad debería llamar a <xref:System.Activities.AsyncCodeActivityContext.MarkCanceled%2A>. Cualquier excepción que se inicie a partir de este método será grave para la instancia del flujo de trabajo.  
  
 [!code-csharp[CFX_ActivityExample#10](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#10)]  
  
### <a name="invoking-asynchronous-methods-on-a-class"></a>Invocar métodos asincrónicos en una clase  
 Muchas de las clases en [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proporcionan funcionalidad asincrónica que, a su vez, puede invocarse de forma asincrónica mediante una actividad basada en <xref:System.Activities.AsyncCodeActivity>. En el ejemplo siguiente de la [usar AsyncOperationContext en una actividad](../../../docs/framework/windows-workflow-foundation/samples/using-asyncoperationcontext-in-an-activity-sample.md), se crea una actividad que crea un archivo de forma asincrónica mediante el uso de la <xref:System.IO.FileStream> clase.  
  
 [!code-csharp[CFX_ActivityExample#12](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#12)]  
  
### <a name="sharing-state-between-the-beginexecute-and-endexecute-methods"></a>Compartir el estado entre los métodos BeginExecute y EndExecute  
 En el ejemplo anterior, se tuvo acceso en <xref:System.IO.FileStream> al objeto <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> creado en <xref:System.Activities.AsyncCodeActivity.EndExecute%2A>. Esto es posible porque la variable `file` se pasó en la propiedad <xref:System.Activities.AsyncCodeActivityContext.UserState%2A?displayProperty=nameWithType> en <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>. Este es el método correcto para compartir el estado entre <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> y <xref:System.Activities.AsyncCodeActivity.EndExecute%2A>. Es incorrecto usar una variable miembro en la clase derivada (`FileWriter` en este caso) para compartir el estado entre el <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> y <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> porque varias instancias de actividad pueden hacer referencia al objeto de actividad. Si se intenta usar una variable miembro para compartir el estado puede dar lugar a valores de una <xref:System.Activities.ActivityInstance> que sobrescriban o que usen valores de otra <xref:System.Activities.ActivityInstance>.  
  
### <a name="accessing-argument-values"></a>Acceso a valores de argumento  
 El entorno de <xref:System.Activities.AsyncCodeActivity> está compuesto de los argumentos definidos en la actividad. Pueden tener acceso a estos argumentos de la <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> / <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> reemplaza con la <xref:System.Activities.AsyncCodeActivityContext> parámetro. No se puede tener acceso a los argumentos en el delegado, pero los valores de argumento o cualquier otro dato deseado se pueden pasar al delegado con sus parámetros. En el siguiente ejemplo, se define una actividad que genera números aleatorios y que obtiene el enlace superior inclusivo del argumento `Max`. El valor del argumento se pasa al código asincrónico cuando se invoca el delegado.  
  
 [!code-csharp[CFX_ActivityExample#9](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#9)]  
  
### <a name="scheduling-actions-or-child-activities-using-asynccodeactivity"></a>Programar acciones o actividades secundarias mediante AsyncCodeActivity  
 Las actividades personalizadas derivadas de <xref:System.Activities.AsyncCodeActivity> proporcionan un método para realizar el trabajo de forma asincrónica con respecto al subproceso del flujo de trabajo, pero no proporcionan la capacidad de programar actividades secundarias o acciones. Sin embargo, el comportamiento asincrónico se puede incorporar con la programación de actividades secundarias a través de composición. Una actividad asincrónica se puede crear, y después componer con una <xref:System.Activities.Activity> o una actividad derivada de <xref:System.Activities.NativeActivity> para proporcionar comportamiento asincrónico y programación de actividades o acciones secundarias. Por ejemplo, se podría crear una actividad que derive de <xref:System.Activities.Activity> y tenga como su implementación una <xref:System.Activities.Statements.Sequence> que contenga la actividad asincrónica, así como otras actividades que implementen la lógica de la actividad. Para obtener más ejemplos de creación de actividades mediante <xref:System.Activities.Activity> y <xref:System.Activities.NativeActivity>, consulte [Cómo: crear una actividad](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md), [opciones de creación de actividades](../../../docs/framework/windows-workflow-foundation/activity-authoring-options-in-wf.md)y el [compuestos](../../../docs/framework/windows-workflow-foundation/samples/composite.md) ejemplos de actividades.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Action>  
 <xref:System.Func%602>  
 [Usar AsyncOperationContext en una actividad](../../../docs/framework/windows-workflow-foundation/samples/using-asyncoperationcontext-in-an-activity-sample.md)
