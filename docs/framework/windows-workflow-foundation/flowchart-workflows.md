---
title: Flujos de trabajo del diagrama de flujo
ms.date: 03/30/2017
ms.assetid: b0a3475c-d22f-49eb-8912-973c960aebf5
ms.openlocfilehash: b84b0de34f8869d9775fe0694e74c340cc16a6b3
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249069"
---
# <a name="flowchart-workflows"></a>Flujos de trabajo del diagrama de flujo

Un diagrama de flujo es un paradigma conocido para diseñar programas. La actividad Flowchart se usa normalmente para implementar flujos de trabajo no secuenciales, aunque se puede usar para flujos de trabajo secuenciales si no se usa ningún nodo `FlowDecision`.

## <a name="flowchart-workflow-structure"></a>Estructura del flujo de trabajo del diagrama de flujo

 Una actividad de diagrama de flujo es una actividad que contiene una colección de actividades que se ejecutarán.  Los diagramas de flujo también contienen elementos de control de flujo como <xref:System.Activities.Statements.FlowDecision> y <xref:System.Activities.Statements.FlowSwitch%601> que dirigen la ejecución entre las actividades contenidas según los valores de las variables.

## <a name="types-of-flow-nodes"></a>Tipos de nodos de flujo

 Se usan tipos diferentes de elementos en función del tipo de control de flujo necesario cuando el elemento se ejecuta. Los tipos de elemento del diagrama de flujo incluyen:

- `FlowStep`: modela un paso de ejecución en el diagrama de flujo.

- `FlowDecision`: la ejecución de bifurcaciones basada en una condición booleana, similar a <xref:System.Activities.Statements.If>.

- `FlowSwitch`: la ejecución de bifurcaciones basada en un modificador exclusivo, similar a <xref:System.Activities.Statements.Switch%601>.

Cada vínculo tiene una propiedad `Action` que define una clase <xref:System.Activities.ActivityAction> que se puede usar para ejecutar actividades secundarias, además de una o más propiedades `Next` que definen qué elemento o elementos ejecutar cuando el elemento actual finalice la ejecución.

### <a name="creating-a-basic-activity-sequence-with-a-flowstep-node"></a>Creación de una secuencia de actividad básica con un nodo FlowStep

Para modelar una secuencia básica en la que dos actividades se ejecutan sucesivamente, se usa el elemento `FlowStep`. En el siguiente ejemplo, se usan dos elementos `FlowStep` para ejecutar dos actividades en secuencia.

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

### <a name="creating-a-conditional-flowchart-with-a-flowdecision-node"></a>Creación de un diagrama de flujo condicional con un nodo FlowDecision

Para modelar un nodo de flujo condicional en un flujo de trabajo de diagrama de flujo (es decir, para crear un vínculo que funcione como el símbolo de la decisión de un diagrama de flujo tradicional), se usa un nodo <xref:System.Activities.Statements.FlowDecision>. La propiedad <xref:System.Activities.Statements.FlowDecision.Condition%2A> del nodo está establecida en una expresión que define la condición. Las propiedades <xref:System.Activities.Statements.FlowDecision.True%2A> y <xref:System.Activities.Statements.FlowDecision.False%2A> están establecidas en instancias de <xref:System.Activities.Statements.FlowNode> para que se ejecuten si la expresión se evalúa como `true` o `false`. En el siguiente ejemplo se muestra cómo definir un flujo de trabajo que usa un nodo <xref:System.Activities.Statements.FlowDecision>.

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

### <a name="creating-an-exclusive-switch-with-a-flowswitch-node"></a>Creación de un conmutador exclusivo con un nodo FlowSwitch

Para modelar un diagrama de flujo en el que se selecciona una ruta de acceso exclusiva según un valor coincidente, se usa el nodo <xref:System.Activities.Statements.FlowSwitch%601>. La propiedad <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> se establece en <xref:System.Activities.Activity%601> con un parámetro de tipo de <xref:System.Object> que define el valor con el que se van a hacer coincidir las opciones. La propiedad <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> define un diccionario de claves y objetos <xref:System.Activities.Statements.FlowNode> para hacer coincidir con la expresión condicional, y un conjunto de objetos <xref:System.Activities.Statements.FlowNode> que definen cómo debe fluir la ejecución si el caso especificado coincide con la expresión condicional. <xref:System.Activities.Statements.FlowSwitch%601> también define una propiedad <xref:System.Activities.Statements.FlowSwitch%601.Default%2A> que define a su vez la manera en que debe fluir la ejecución si no hay casos que coincidan con la expresión de la condición. En el siguiente ejemplo se muestra cómo definir un flujo de trabajo que usa un elemento <xref:System.Activities.Statements.FlowSwitch%601>.

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
