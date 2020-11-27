---
title: Usar delegados de actividad
ms.date: 03/30/2017
ms.assetid: e33cf876-8979-440b-9b23-4a12d1139960
ms.openlocfilehash: 66a03187336475ed377fda032506cfa66d3daf58
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293304"
---
# <a name="using-activity-delegates"></a>Usar delegados de actividad

Los delegados de actividad permiten a los autores de actividad exponer devoluciones de llamada con firmas específicas, para las que los usuarios de la actividad pueden proporcionar controladores basados en actividades. Hay dos tipos de delegados de actividad disponibles: <xref:System.Activities.ActivityAction%601> se usa para definir delegados de actividad que no tienen un valor devuelto y <xref:System.Activities.ActivityFunc%601> se utiliza para definir delegados de actividad que tienen un valor devuelto.

Los delegados de actividad son útiles en situaciones en que se debe restringir una actividad secundaria para que tenga una firma determinada. Por ejemplo, una actividad <xref:System.Activities.Statements.While> puede contener cualquier tipo de actividad secundaria sin restricciones, aunque el cuerpo de una actividad <xref:System.Activities.Statements.ForEach%601> es <xref:System.Activities.ActivityAction%601> y la actividad secundaria que <xref:System.Activities.Statements.ForEach%601> ejecuta finalmente debe tener <xref:System.Activities.InArgument%601>, que es el mismo tipo de miembros de la colección que <xref:System.Activities.Statements.ForEach%601> enumera.

## <a name="using-activityaction"></a>Utilizar ActivityAction

Varias actividades de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] utilizan acciones de actividad, como <xref:System.Activities.Statements.Catch> y <xref:System.Activities.Statements.ForEach%601>. En cada caso, la acción de actividad representa una ubicación donde el autor del flujo de trabajo especifica una actividad para proporcionar el comportamiento deseado cuando se crea un flujo de trabajo mediante una de estas actividades. En el siguiente ejemplo, se utiliza una actividad <xref:System.Activities.Statements.ForEach%601> para mostrar texto en la ventana de la consola. El cuerpo de <xref:System.Activities.Statements.ForEach%601> se especifica utilizando un objeto <xref:System.Activities.ActivityAction%601> que coincide con el tipo del objeto <xref:System.Activities.Statements.ForEach%601> que es cadena. La actividad <xref:System.Activities.Statements.WriteLine> especificada en <xref:System.Activities.ActivityDelegate.Handler%2A> tiene su argumento <xref:System.Activities.Statements.WriteLine.Text%2A> enlazado a los valores de cadena en la colección que la actividad <xref:System.Activities.Statements.ForEach%601> recorre en iteración.

[!code-csharp[CFX_ActivityExample#6](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#6)]

ActionArgument se utiliza para pasar los elementos individuales de la colección a WriteLine. Cuando se invoca el flujo de trabajo, en la consola se muestra el siguiente resultado.

```console
HelloWorld.
```

Los ejemplos de este tema usan la sintaxis de inicialización del objeto. Esta sintaxis puede ser una forma útil de crear definiciones de flujo de trabajo en el código porque proporciona una vista jerárquica de las actividades en el flujo de trabajo y muestra la relación entre las actividades. No hay ningún requisito para usar la sintaxis de inicialización de objeto al crear los flujos de trabajo mediante programación. El ejemplo siguiente es equivalente en su funcionamiento al ejemplo anterior.

[!code-csharp[CFX_ActivityExample#7](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#7)]

Para obtener más información sobre los inicializadores de objeto, vea [Cómo: inicializar objetos sin llamar a un constructor (Guía de programación de C#)](../../csharp/programming-guide/classes-and-structs/how-to-initialize-objects-by-using-an-object-initializer.md) y [Cómo: declarar un objeto usando un inicializador de objeto (Visual Basic)](../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md).

En el siguiente ejemplo, se utiliza una actividad <xref:System.Activities.Statements.TryCatch> en un flujo de trabajo. El flujo de trabajo produce una excepción <xref:System.ApplicationException>, que es controlada por una actividad <xref:System.Activities.Statements.Catch%601>. El controlador de la <xref:System.Activities.Statements.Catch%601> acción de actividad de la actividad es una <xref:System.Activities.Statements.WriteLine> actividad, y el detalle de la excepción se transmite a través de `ex` <xref:System.Activities.DelegateInArgument%601> .

[!code-csharp[CFX_WorkflowApplicationExample#33](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#33)]

Cuando cree una actividad personalizada que defina un objeto <xref:System.Activities.ActivityAction%601>, use <xref:System.Activities.Statements.InvokeAction%601> para modelar la invocación de ese objeto <xref:System.Activities.ActivityAction%601>. En este ejemplo, se define una actividad `WriteLineWithNotification` personalizada. Esta actividad está compuesta de una clase <xref:System.Activities.Statements.Sequence> que contiene una actividad <xref:System.Activities.Statements.WriteLine> seguida de <xref:System.Activities.Statements.InvokeAction%601> que invoca una clase <xref:System.Activities.ActivityAction%601> que toma un argumento de tipo cadena.

[!code-csharp[CFX_ActivityExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#1)]

Cuando se crea un flujo de trabajo con la actividad `WriteLineWithNotification`, el autor del flujo de trabajo especifica la lógica personalizada deseada en la propiedad <xref:System.Activities.ActivityDelegate.Handler%2A> de la acción de la actividad. En este ejemplo, se crea un flujo de trabajo que utiliza la actividad `WriteLineWithNotification` y se usa una actividad <xref:System.Activities.Statements.WriteLine> como <xref:System.Activities.ActivityDelegate.Handler%2A>.

[!code-csharp[CFX_ActivityExample#2](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#2)]

Hay varias versiones genéricas de <xref:System.Activities.Statements.InvokeAction%601> y <xref:System.Activities.ActivityAction%601> proporcionadas para pasar uno o varios argumentos.

## <a name="using-activityfunc"></a>Usar ActivityFunc

<xref:System.Activities.ActivityAction%601> es útil cuando no existe ningún valor de resultado procedente de la actividad y <xref:System.Activities.ActivityFunc%601> se utiliza cuando se devuelve un valor de resultado. Cuando cree una actividad personalizada que defina un objeto <xref:System.Activities.ActivityFunc%601>, use <xref:System.Activities.Expressions.InvokeFunc%601> para modelar la invocación de ese objeto <xref:System.Activities.ActivityFunc%601>. En el ejemplo siguiente, se define una actividad `WriteFillerText` . Para proporcionar el texto de relleno, se especifica una clase <xref:System.Activities.Expressions.InvokeFunc%601> que toma un argumento entero y genera una cadena como resultado. Una vez recuperado el texto de relleno, se muestra en la consola utilizando una actividad <xref:System.Activities.Statements.WriteLine>.

[!code-csharp[CFX_ActivityExample#3](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#3)]

Para proporcionar el texto, se debe usar una actividad que tome un argumento `int` y tenga como resultado una cadena. En este ejemplo se muestra una actividad `TextGenerator` que cumple estos requisitos.

[!code-csharp[CFX_ActivityExample#4](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#4)]

Para usar la actividad `TextGenerator` con la actividad `WriteFillerText`, especifíquela como <xref:System.Activities.ActivityDelegate.Handler%2A>.

[!code-csharp[CFX_ActivityExample#5](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#5)]
