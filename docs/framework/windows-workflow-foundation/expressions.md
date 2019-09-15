---
title: 'Expresiones: WF'
ms.date: 03/30/2017
ms.assetid: c42341a9-43a1-462c-bffb-c5de004aa428
ms.openlocfilehash: 1c79d4294ce1e7d6f6fc13e8220f88919c8f6021
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989751"
---
# <a name="expressions"></a><span data-ttu-id="ea7de-102">Expresiones</span><span class="sxs-lookup"><span data-stu-id="ea7de-102">Expressions</span></span>
<span data-ttu-id="ea7de-103">Una expresión Windows Workflow Foundation (WF) es cualquier actividad que devuelve un resultado.</span><span class="sxs-lookup"><span data-stu-id="ea7de-103">A Windows Workflow Foundation (WF) expression is any activity that returns a result.</span></span> <span data-ttu-id="ea7de-104">Todas las actividades de expresión derivan indirectamente de <xref:System.Activities.Activity%601>, que contiene una propiedad <xref:System.Activities.OutArgument> denominada <xref:System.Activities.Activity%601.Result%2A> como valor devuelto de la actividad.</span><span class="sxs-lookup"><span data-stu-id="ea7de-104">All expression activities derive indirectly from <xref:System.Activities.Activity%601>, which contains an <xref:System.Activities.OutArgument> property named <xref:System.Activities.Activity%601.Result%2A> as the activity’s return value.</span></span> [!INCLUDE[wf1](../../../includes/wf1-md.md)] <span data-ttu-id="ea7de-105">incluye una gran variedad de actividades de expresión, desde simples como <xref:System.Activities.Expressions.VariableValue%601> y <xref:System.Activities.Expressions.VariableReference%601>, que proporcionan acceso a la única variable de flujo de trabajo mediante actividades de operador, hasta actividades complejas como <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> y <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>, que proporcionan acceso a todo el lenguaje Visual Basic para generar el resultado.</span><span class="sxs-lookup"><span data-stu-id="ea7de-105">ships with a wide range of expression activities from simple ones like <xref:System.Activities.Expressions.VariableValue%601> and <xref:System.Activities.Expressions.VariableReference%601>, which provide access to single workflow variable through operator activities, to complex activities such as <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> and <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> that offer access to the full breadth of Visual Basic language to produce the result.</span></span> <span data-ttu-id="ea7de-106">Las actividades de expresión adicionales se pueden crear al derivar de <xref:System.Activities.CodeActivity%601> o <xref:System.Activities.NativeActivity%601>.</span><span class="sxs-lookup"><span data-stu-id="ea7de-106">Additional expression activities can be created by deriving from <xref:System.Activities.CodeActivity%601> or <xref:System.Activities.NativeActivity%601>.</span></span>  
  
## <a name="using-expressions"></a><span data-ttu-id="ea7de-107">Usar expresiones</span><span class="sxs-lookup"><span data-stu-id="ea7de-107">Using Expressions</span></span>  
 <span data-ttu-id="ea7de-108">El diseñador de flujo de trabajo usa <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> y <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> para todas las expresiones en proyectos de Visual Basic, y <xref:Microsoft.CSharp.Activities.CSharpValue%601> y <xref:Microsoft.CSharp.Activities.CSharpReference%601> para expresiones en los proyectos de flujo de trabajo de C#.</span><span class="sxs-lookup"><span data-stu-id="ea7de-108">Workflow designer uses <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> and <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> for all expressions in Visual Basic projects, and <xref:Microsoft.CSharp.Activities.CSharpValue%601> and <xref:Microsoft.CSharp.Activities.CSharpReference%601> for expressions in C# workflow projects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea7de-109">La compatibilidad C# con expresiones de proyectos de flujo de trabajo se presentó en .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="ea7de-109">Support for C# expressions in workflow projects was introduced in .NET Framework 4.5.</span></span> <span data-ttu-id="ea7de-110">Para obtener más información, vea [ C# expresiones](csharp-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ea7de-110">For more information, see [C# Expressions](csharp-expressions.md).</span></span>  
  
 <span data-ttu-id="ea7de-111">Los flujos de trabajo generados por el diseñador se guardan en XAML, donde las expresiones se adjuntan en corchetes, como en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ea7de-111">Workflows produced by designer are saved in XAML, where expressions appear enclosed in square brackets, as in the following example.</span></span>  
  
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
  
 <span data-ttu-id="ea7de-112">Al definir un flujo de trabajo en el código, se puede usar cualquier actividad de expresión.</span><span class="sxs-lookup"><span data-stu-id="ea7de-112">When defining a workflow in code, any expression activities can be used.</span></span> <span data-ttu-id="ea7de-113">En el siguiente ejemplo se muestra el uso de una composición de actividades de operador para sumar tres números.</span><span class="sxs-lookup"><span data-stu-id="ea7de-113">The following example shows the usage of a composition of operator activities to add three numbers.</span></span>  
  
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
  
 <span data-ttu-id="ea7de-114">El mismo flujo de trabajo se puede expresar de forma más sólida usando expresiones lambda de C#, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ea7de-114">The same workflow can be expressed more compactly by using C# lambda expressions, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="ea7de-115">El flujo de trabajo también se puede expresar usando actividades de expresión de Visual Basic, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ea7de-115">The workflow can also be expressed by using Visual Basic expression activities, as shown in the following example.</span></span>  
  
```vb  
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
            Value = new InArgument<int>(new VisualBasicValue<int>("a + b + c"))  
        }  
    }  
};  
```  
  
## <a name="extending-available-expressions-with-custom-expression-activities"></a><span data-ttu-id="ea7de-116">Extender las expresiones disponibles con actividades de expresión personalizadas</span><span class="sxs-lookup"><span data-stu-id="ea7de-116">Extending Available Expressions with Custom Expression Activities</span></span>  
 <span data-ttu-id="ea7de-117">Las expresiones en [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] son extensibles, lo que permite que se creen actividades de expresión adicionales.</span><span class="sxs-lookup"><span data-stu-id="ea7de-117">Expressions in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] are extensible allowing for additional expression activities to be created.</span></span> <span data-ttu-id="ea7de-118">En el siguiente ejemplo se muestra una actividad que devuelve una suma de tres valores enteros.</span><span class="sxs-lookup"><span data-stu-id="ea7de-118">The following example shows an activity that returns a sum of three integer values.</span></span>  
  
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
  
 <span data-ttu-id="ea7de-119">Con esta nueva actividad, puede volver a escribir el flujo de trabajo anterior que sumó tres valores, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ea7de-119">With this new activity you can rewrite the previous workflow that added three values as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="ea7de-120">Para obtener más información sobre el uso de expresiones en el código, vea [crear flujos de trabajo, actividades y expresiones mediante código imperativo](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span><span class="sxs-lookup"><span data-stu-id="ea7de-120">For more information about using expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>
