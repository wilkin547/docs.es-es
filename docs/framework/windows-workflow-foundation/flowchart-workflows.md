---
title: Flujos de trabajo del diagrama de flujo
description: En este artículo se describe la actividad del diagrama de flujo, que se usa normalmente para implementar flujos de trabajo no secuenciales en Workflow Foundation.
ms.date: 03/30/2017
ms.assetid: b0a3475c-d22f-49eb-8912-973c960aebf5
ms.openlocfilehash: ce0661653a1d50b3f7264246b810faabbd12bf5f
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419920"
---
# <a name="flowchart-workflows"></a><span data-ttu-id="b68d4-103">Flujos de trabajo del diagrama de flujo</span><span class="sxs-lookup"><span data-stu-id="b68d4-103">Flowchart Workflows</span></span>

<span data-ttu-id="b68d4-104">Un diagrama de flujo es un paradigma conocido para diseñar programas.</span><span class="sxs-lookup"><span data-stu-id="b68d4-104">A flowchart is a well-known paradigm for designing programs.</span></span> <span data-ttu-id="b68d4-105">La actividad Flowchart se usa normalmente para implementar flujos de trabajo no secuenciales, aunque se puede usar para flujos de trabajo secuenciales si no se usa ningún nodo `FlowDecision`.</span><span class="sxs-lookup"><span data-stu-id="b68d4-105">The Flowchart activity is typically used to implement non-sequential workflows, but can be used for sequential workflows if no `FlowDecision` nodes are used.</span></span>

## <a name="flowchart-workflow-structure"></a><span data-ttu-id="b68d4-106">Estructura del flujo de trabajo de diagrama</span><span class="sxs-lookup"><span data-stu-id="b68d4-106">Flowchart workflow structure</span></span>

 <span data-ttu-id="b68d4-107">Una actividad de diagrama de flujo es una actividad que contiene una colección de actividades que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="b68d4-107">A Flowchart activity is an activity that contains a collection of activities to be executed.</span></span>  <span data-ttu-id="b68d4-108">Los diagramas de flujo también contienen elementos de control de flujo como <xref:System.Activities.Statements.FlowDecision> y <xref:System.Activities.Statements.FlowSwitch%601> que dirigen la ejecución entre las actividades contenidas según los valores de las variables.</span><span class="sxs-lookup"><span data-stu-id="b68d4-108">Flowcharts also contain flow control elements such as <xref:System.Activities.Statements.FlowDecision> and <xref:System.Activities.Statements.FlowSwitch%601> that direct execution between contained activities based on the values of variables.</span></span>

## <a name="types-of-flow-nodes"></a><span data-ttu-id="b68d4-109">Tipos de nodos de flujo</span><span class="sxs-lookup"><span data-stu-id="b68d4-109">Types of flow nodes</span></span>

 <span data-ttu-id="b68d4-110">Se usan tipos diferentes de elementos en función del tipo de control de flujo necesario cuando el elemento se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="b68d4-110">Different types of elements are used depending on the type of flow control required when the element executes.</span></span> <span data-ttu-id="b68d4-111">Los tipos de elemento del diagrama de flujo incluyen:</span><span class="sxs-lookup"><span data-stu-id="b68d4-111">Types of flowchart elements include:</span></span>

- <span data-ttu-id="b68d4-112">`FlowStep`: modela un paso de ejecución en el diagrama de flujo.</span><span class="sxs-lookup"><span data-stu-id="b68d4-112">`FlowStep` - Models one step of execution in the flowchart.</span></span>

- <span data-ttu-id="b68d4-113">`FlowDecision`: la ejecución de bifurcaciones basada en una condición booleana, similar a <xref:System.Activities.Statements.If>.</span><span class="sxs-lookup"><span data-stu-id="b68d4-113">`FlowDecision` - Branches execution based on a Boolean condition, similar to <xref:System.Activities.Statements.If>.</span></span>

- <span data-ttu-id="b68d4-114">`FlowSwitch`: la ejecución de bifurcaciones basada en un modificador exclusivo, similar a <xref:System.Activities.Statements.Switch%601>.</span><span class="sxs-lookup"><span data-stu-id="b68d4-114">`FlowSwitch` – Branches execution based on an exclusive switch, similar to <xref:System.Activities.Statements.Switch%601>.</span></span>

<span data-ttu-id="b68d4-115">Cada vínculo tiene una propiedad `Action` que define una clase <xref:System.Activities.ActivityAction> que se puede usar para ejecutar actividades secundarias, además de una o más propiedades `Next` que definen qué elemento o elementos ejecutar cuando el elemento actual finalice la ejecución.</span><span class="sxs-lookup"><span data-stu-id="b68d4-115">Each link has an `Action` property that defines a <xref:System.Activities.ActivityAction> that can be used to execute child activities, and one or more `Next` properties that define which element or elements to execute when the current element finishes execution.</span></span>

### <a name="creating-a-basic-activity-sequence-with-a-flowstep-node"></a><span data-ttu-id="b68d4-116">Creación de una secuencia de actividad básica con un nodo FlowStep</span><span class="sxs-lookup"><span data-stu-id="b68d4-116">Creating a basic activity sequence with a FlowStep node</span></span>

<span data-ttu-id="b68d4-117">Para modelar una secuencia básica en la que dos actividades se ejecutan sucesivamente, se usa el elemento `FlowStep`.</span><span class="sxs-lookup"><span data-stu-id="b68d4-117">To model a basic sequence in which two activities execute in turn, the `FlowStep` element is used.</span></span> <span data-ttu-id="b68d4-118">En el siguiente ejemplo, se usan dos elementos `FlowStep` para ejecutar dos actividades en secuencia.</span><span class="sxs-lookup"><span data-stu-id="b68d4-118">In the following example, two `FlowStep` elements are used to execute two activities in sequence.</span></span>

```xml
<Flowchart>
  <FlowStep>
    <Assign DisplayName="Get Name">
      <Assign.To>
        <OutArgument x:TypeArguments="x:String">[result]</OutArgument>
      </Assign.To>
      <Assign.Value>
        <InArgument x:TypeArguments="x:String">["User"]</InArgument>
      </Assign.Value>
    </Assign>
    <FlowStep.Next>
      <FlowStep>
        <WriteLine Text="Hello, " & [result]/>
      </FlowStep>
    </FlowStep.Next>
  </FlowStep>
</Flowchart>
```

### <a name="creating-a-conditional-flowchart-with-a-flowdecision-node"></a><span data-ttu-id="b68d4-119">Crear un diagrama de flujo condicional con un nodo FlowDecision</span><span class="sxs-lookup"><span data-stu-id="b68d4-119">Creating a conditional flowchart with a FlowDecision node</span></span>

<span data-ttu-id="b68d4-120">Para modelar un nodo de flujo condicional en un flujo de trabajo de diagrama de flujo (es decir, para crear un vínculo que funcione como el símbolo de la decisión de un diagrama de flujo tradicional), se usa un nodo <xref:System.Activities.Statements.FlowDecision>.</span><span class="sxs-lookup"><span data-stu-id="b68d4-120">To model a conditional flow node in a flowchart workflow (that is, to create a link that functions as a traditional flowchart's decision symbol), a <xref:System.Activities.Statements.FlowDecision> node is used.</span></span> <span data-ttu-id="b68d4-121">La propiedad <xref:System.Activities.Statements.FlowDecision.Condition%2A> del nodo está establecida en una expresión que define la condición. Las propiedades <xref:System.Activities.Statements.FlowDecision.True%2A> y <xref:System.Activities.Statements.FlowDecision.False%2A> están establecidas en instancias de <xref:System.Activities.Statements.FlowNode> para que se ejecuten si la expresión se evalúa como `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="b68d4-121">The <xref:System.Activities.Statements.FlowDecision.Condition%2A> property of the node is set to an expression that defines the condition, and the <xref:System.Activities.Statements.FlowDecision.True%2A> and <xref:System.Activities.Statements.FlowDecision.False%2A> properties are set to <xref:System.Activities.Statements.FlowNode> instances to be executed if the expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="b68d4-122">En el siguiente ejemplo se muestra cómo definir un flujo de trabajo que usa un nodo <xref:System.Activities.Statements.FlowDecision>.</span><span class="sxs-lookup"><span data-stu-id="b68d4-122">The following example shows how to define a workflow that uses a <xref:System.Activities.Statements.FlowDecision> node.</span></span>

```xml
<Flowchart>
  <FlowStep>
    <Read Result="[s]"/>
    <FlowStep.Next>
      <FlowDecision>
        <IsEmpty Input="[s]" />
        <FlowDecision.True>
          <FlowStep>
            <Write Text="Empty"/>
          </FlowStep>
        </FlowDecision.True>
        <FlowDecision.False>
          <FlowStep>
            <Write Text="Non-Empty"/>
          </FlowStep>
        </FlowDecision.False>
      </FlowDecision>
    </FlowStep.Next>
  </FlowStep>
</Flowchart>
```

### <a name="creating-an-exclusive-switch-with-a-flowswitch-node"></a><span data-ttu-id="b68d4-123">Crear un modificador exclusivo con un nodo FlowSwitch</span><span class="sxs-lookup"><span data-stu-id="b68d4-123">Creating an exclusive switch with a FlowSwitch node</span></span>

<span data-ttu-id="b68d4-124">Para modelar un diagrama de flujo en el que se selecciona una ruta de acceso exclusiva según un valor coincidente, se usa el nodo <xref:System.Activities.Statements.FlowSwitch%601>.</span><span class="sxs-lookup"><span data-stu-id="b68d4-124">To model a flowchart in which one exclusive path is selected based on a matching value, the <xref:System.Activities.Statements.FlowSwitch%601> node is used.</span></span> <span data-ttu-id="b68d4-125">La propiedad <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> se establece en <xref:System.Activities.Activity%601> con un parámetro de tipo de <xref:System.Object> que define el valor con el que se van a hacer coincidir las opciones.</span><span class="sxs-lookup"><span data-stu-id="b68d4-125">The <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> property is set to a <xref:System.Activities.Activity%601> with a type parameter of <xref:System.Object> that defines the value to match choices against.</span></span> <span data-ttu-id="b68d4-126">La propiedad <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> define un diccionario de claves y objetos <xref:System.Activities.Statements.FlowNode> para hacer coincidir con la expresión condicional, y un conjunto de objetos <xref:System.Activities.Statements.FlowNode> que definen cómo debe fluir la ejecución si el caso especificado coincide con la expresión condicional.</span><span class="sxs-lookup"><span data-stu-id="b68d4-126">The <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> property defines a dictionary of keys and <xref:System.Activities.Statements.FlowNode> objects to match against the conditional expression, and a set of <xref:System.Activities.Statements.FlowNode> objects that define how execution should flow if the given case matches the conditional expression.</span></span> <span data-ttu-id="b68d4-127"><xref:System.Activities.Statements.FlowSwitch%601> también define una propiedad <xref:System.Activities.Statements.FlowSwitch%601.Default%2A> que define a su vez la manera en que debe fluir la ejecución si no hay casos que coincidan con la expresión de la condición.</span><span class="sxs-lookup"><span data-stu-id="b68d4-127">The <xref:System.Activities.Statements.FlowSwitch%601> also defines a <xref:System.Activities.Statements.FlowSwitch%601.Default%2A> property that defines how execution should flow if no cases match the condition expression.</span></span> <span data-ttu-id="b68d4-128">En el siguiente ejemplo se muestra cómo definir un flujo de trabajo que usa un elemento <xref:System.Activities.Statements.FlowSwitch%601>.</span><span class="sxs-lookup"><span data-stu-id="b68d4-128">The following example demonstrates how to define a workflow that uses a <xref:System.Activities.Statements.FlowSwitch%601> element.</span></span>

```xml
<Flowchart>
  <FlowSwitch>
    <FlowStep x:Key="Red">
      <WriteRed/>
    </FlowStep>
    <FlowStep x:Key="Blue">
      <WriteBlue/>
    </FlowStep>
    <FlowStep x:Key="Green">
      <WriteGreen/>
    </FlowStep>
  </FlowSwitch>
</Flowchart>
```
