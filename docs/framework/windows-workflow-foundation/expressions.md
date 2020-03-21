---
title: Expresiones - WF
ms.date: 03/30/2017
ms.assetid: c42341a9-43a1-462c-bffb-c5de004aa428
ms.openlocfilehash: 93fe449e8fa6c50f715d842c2ef6a9ecbd31aff2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182939"
---
# <a name="expressions"></a>Expresiones

Una expresión de Windows Workflow Foundation (WF) es cualquier actividad que devuelve un resultado. Todas las actividades de expresión derivan indirectamente de <xref:System.Activities.Activity%601>, que contiene una propiedad <xref:System.Activities.OutArgument> denominada <xref:System.Activities.Activity%601.Result%2A> como valor devuelto de la actividad. [!INCLUDE[wf1](../../../includes/wf1-md.md)] incluye una gran variedad de actividades de expresión, desde simples como <xref:System.Activities.Expressions.VariableValue%601> y <xref:System.Activities.Expressions.VariableReference%601>, que proporcionan acceso a la única variable de flujo de trabajo mediante actividades de operador, hasta actividades complejas como <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> y <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>, que proporcionan acceso a todo el lenguaje Visual Basic para generar el resultado. Las actividades de expresión adicionales se pueden crear al derivar de <xref:System.Activities.CodeActivity%601> o <xref:System.Activities.NativeActivity%601>.

## <a name="using-expressions"></a>Usar expresiones
 El diseñador de flujo de trabajo usa <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> y <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> para todas las expresiones en proyectos de Visual Basic, y <xref:Microsoft.CSharp.Activities.CSharpValue%601> y <xref:Microsoft.CSharp.Activities.CSharpReference%601> para expresiones en los proyectos de flujo de trabajo de C#.

> [!NOTE]
> En .NET Framework 4.5 se introdujo la compatibilidad con expresiones de C-C en proyectos de flujo de trabajo. Para obtener más información, vea Expresiones de [C.](csharp-expressions.md)

 Los flujos de trabajo generados por el diseñador se guardan en XAML, donde las expresiones se adjuntan en corchetes, como en el siguiente ejemplo.

```xml
<Sequence xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
  <Sequence.Variables>
    <Variable x:TypeArguments="x:Int32" Default="1" Name="a" />
    <Variable x:TypeArguments="x:Int32" Default="2" Name="b" />
    <Variable x:TypeArguments="x:Int32" Default="3" Name="c" />
    <Variable x:TypeArguments="x:Int32" Default="0" Name="r" />
  </Sequence.Variables>
  <Assign>
    <Assign.To>
      <OutArgument x:TypeArguments="x:Int32">[r]</OutArgument>
    </Assign.To>
    <Assign.Value>
      <InArgument x:TypeArguments="x:Int32">[a + b + c]</InArgument>
    </Assign.Value>
  </Assign>
</Sequence>
```

 Al definir un flujo de trabajo en el código, se puede usar cualquier actividad de expresión. En el ejemplo siguiente se muestra el uso de una composición de actividades de operador para agregar tres números:

```csharp
Variable<int> a = new Variable<int>("a", 1);
Variable<int> b = new Variable<int>("b", 2);
Variable<int> c = new Variable<int>("c", 3);
Variable<int> r = new Variable<int>("r", 0);

Sequence w = new Sequence
{
    Variables = { a, b, c, r },
    Activities =
    {
        new Assign {
            To = new OutArgument<int>(r),
            Value = new InArgument<int> {
                Expression = new Add<int, int, int> {
                    Left = new Add<int, int, int> {
                        Left = new InArgument<int>(a),
                        Right = new InArgument<int>(b)
                    },
                    Right = new InArgument<int>(c)
                }
            }
        }
    }
};
```

 El mismo flujo de trabajo se puede expresar de forma más compacta mediante expresiones lambda de C, como se muestra en el ejemplo siguiente:
  
```csharp
Variable<int> a = new Variable<int>("a", 1);
Variable<int> b = new Variable<int>("b", 2);
Variable<int> c = new Variable<int>("c", 3);
Variable<int> r = new Variable<int>("r", 0);

Sequence w = new Sequence
{
    Variables = { a, b, c, r },
    Activities =
    {
        new Assign {
            To = new OutArgument<int>(r),
            Value = new InArgument<int>((ctx) => a.Get(ctx) + b.Get(ctx) + c.Get(ctx))
        }
    }
};
```

## <a name="extending-available-expressions-with-custom-expression-activities"></a>Extender las expresiones disponibles con actividades de expresión personalizadas

 Las expresiones en [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] son extensibles, lo que permite que se creen actividades de expresión adicionales. En el siguiente ejemplo se muestra una actividad que devuelve una suma de tres valores enteros.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Activities;

namespace ExpressionsDemo
{
    public sealed class AddThreeValues : CodeActivity<int>
    {
        public InArgument<int> Value1 { get; set; }
        public InArgument<int> Value2 { get; set; }
        public InArgument<int> Value3 { get; set; }

        protected override int Execute(CodeActivityContext context)
        {
            return Value1.Get(context) +
                   Value2.Get(context) +
                   Value3.Get(context);
        }
    }
}
```

 Con esta nueva actividad puede reescribir el flujo de trabajo anterior que agregó tres valores como se muestra en el ejemplo siguiente:

```csharp
Variable<int> a = new Variable<int>("a", 1);
Variable<int> b = new Variable<int>("b", 2);
Variable<int> c = new Variable<int>("c", 3);
Variable<int> r = new Variable<int>("r", 0);

Sequence w = new Sequence
{
    Variables = { a, b, c, r },
    Activities =
    {
        new Assign {
            To = new OutArgument<int>(r),
            Value = new InArgument<int> {
                Expression = new AddThreeValues() {
                    Value1 = new InArgument<int>(a),
                    Value2 = new InArgument<int>(b),
                    Value3 = new InArgument<int>(c)
                }
            }
        }
    }
};
```

 Para obtener más información sobre el uso de expresiones en el código, vea Creación de flujos de [trabajo, actividades y expresiones mediante código imperativo](authoring-workflows-activities-and-expressions-using-imperative-code.md).
