---
title: Creación de tipos mixin mediante métodos de interfaz predeterminados
description: Con el uso de los miembros de interfaz predeterminados, puede extender las interfaces con implementaciones predeterminadas opcionales para los implementadores.
ms.technology: csharp-advanced-concepts
ms.date: 10/04/2019
ms.openlocfilehash: fb876731f1cf16840b583ea23b1dd09d8ff74bfe
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102103717"
---
# <a name="tutorial-mix-functionality-in-when-creating-classes-using-interfaces-with-default-interface-methods"></a>Tutorial: Funcionalidad de combinación al crear clases mediante interfaces con métodos de interfaz predeterminados

A partir de C# 8.0 en .NET Core 3.0, puede definir una implementación cuando declare un miembro de una interfaz. Esta característica proporciona nuevas funcionalidades en las que puede definir implementaciones predeterminadas para las características declaradas en las interfaces. Las clases pueden elegir cuándo invalidar la funcionalidad, cuándo usar la funcionalidad predeterminada y cuándo no se debe declarar la compatibilidad con características discretas.

En este tutorial aprenderá lo siguiente:

> [!div class="checklist"]
>
> * Creación de interfaces con implementaciones que describen características discretas.
> * Creación de clases que usan las implementaciones predeterminadas.
> * Creación de clases que invaliden algunas o todas las implementaciones predeterminadas.

## <a name="prerequisites"></a>Requisitos previos

Deberá configurar la máquina para ejecutar .NET Core, incluido el compilador de C# 8.0. El compilador de C# 8.0 está disponible a partir de la [versión 16.3 de Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o del [SDK de .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet) o versiones posteriores.

## <a name="limitations-of-extension-methods"></a>Limitaciones de los métodos de extensión

Una manera de implementar el comportamiento que aparece como parte de una interfaz es definir [métodos de extensión](../programming-guide/classes-and-structs/extension-methods.md) que proporcionan el comportamiento predeterminado. Las interfaces declaran un conjunto mínimo de miembros mientras proporcionan un área expuesta más grande para cualquier clase que implemente esa interfaz. Por ejemplo, los métodos de extensión de <xref:System.Linq.Enumerable> proporcionan la implementación para que cualquier secuencia sea el origen de una consulta LINQ.

Los métodos de extensión se resuelven en tiempo de compilación, mediante el tipo declarado de la variable. Las clases que implementan la interfaz pueden proporcionar una mejor implementación para cualquier método de extensión. Las declaraciones de variables deben coincidir con el tipo de implementación para que el compilador pueda elegir esa implementación. Cuando el tipo en tiempo de compilación coincide con la interfaz, las llamadas al método se resuelven en el método de extensión. Otro problema con los métodos de extensión es que se puede tener acceso a esos métodos siempre que se pueda tener acceso a la clase que contiene los métodos de extensión. Las clases no pueden declarar si deben o no deben proporcionar características declaradas en los métodos de extensión.

A partir de C# 8.0, puede declarar las implementaciones predeterminadas como métodos de interfaz. Después, cada clase usa automáticamente la implementación predeterminada. Cualquier clase que pueda proporcionar una mejor implementación puede invalidar la definición del método de interfaz con un algoritmo mejor. En un sentido, esta técnica suena de forma similar a como se podían usar los [métodos de extensión](../programming-guide/classes-and-structs/extension-methods.md).

En este artículo, aprenderá cómo las implementaciones de interfaces predeterminadas habilitan nuevos escenarios.

## <a name="design-the-application"></a>Diseño de la aplicación

Considere una aplicación de automatización de dispositivos del hogar. Probablemente tenga muchos tipos diferentes de luces e indicadores que podrían usarse en toda la casa. Cada luz debe admitir las API para encenderla y apagarla, y para notificar el estado actual. Algunas luces e indicadores pueden admitir otras características, como:

- Encender la luz y apagarla después de un tiempo.
- Hacer parpadear la luz durante un período.

Algunas de estas funcionalidades extendidas se pueden emular en los dispositivos que admiten el conjunto mínimo. Lo que indica que se proporciona una implementación predeterminada. En el caso de los dispositivos que tienen más funcionalidades integradas, el software del dispositivo usaría las funcionalidades nativas. Para otras luces, podrían optar por implementar la interfaz y usar la implementación predeterminada.

Los miembros de interfaz predeterminados son una solución mejor para este escenario que los métodos de extensión. Los autores de clases pueden controlar qué interfaces deciden implementar. Las interfaces que elijan están disponibles como métodos. Además, dado que los métodos de interfaz predeterminados son virtuales de forma predeterminada, el envío del método siempre elige la implementación en la clase.

Vamos a crear el código para mostrar estas diferencias.

## <a name="create-interfaces"></a>Creación de interfaces

Empiece por crear la interfaz que define el comportamiento de todas las luces:

[!code-csharp[Declare base interface](./snippets/mixins-with-default-interface-methods/UnusedExampleCode.cs?name=SnippetILightInterfaceV1)]

Un accesorio básico de luces de techo puede implementar esta interfaz, tal como se muestra en el código siguiente:

[!code-csharp[First overhead light](./snippets/mixins-with-default-interface-methods/UnusedExampleCode.cs?name=SnippetOverheadLightV1)]

En este tutorial, el código no dispone de dispositivos IoT, pero emula esas actividades escribiendo mensajes en la consola. Puede explorar el código sin automatizar los dispositivos de hogar.

A continuación, vamos a definir la interfaz para una luz que se pueda apagar automáticamente después de un tiempo de espera:

[!code-csharp[pure Timer interface](./snippets/mixins-with-default-interface-methods/UnusedExampleCode.cs?name=SnippetPureTimerInterface)]

Podría agregar una implementación básica a la luz de techo, pero una solución mejor es modificar esta definición de interfaz para proporcionar una implementación predeterminada `virtual`:

[!code-csharp[Timer interface](./snippets/mixins-with-default-interface-methods/ITimerLight.cs?name=SnippetTimerLightFinal)]

Al agregar ese cambio, la clase `OverheadLight` puede implementar la función de temporizador mediante la declaración de la compatibilidad con la interfaz:

```csharp
public class OverheadLight : ITimerLight { }
```

Un tipo de luz diferente puede admitir un protocolo más sofisticado. Puede proporcionar su propia implementación de `TurnOnFor`, como se muestra en el código siguiente:

[!code-csharp[Override the timer function](./snippets/mixins-with-default-interface-methods/HalogenLight.cs?name=SnippetHalogenLight)]

A diferencia de los métodos de clase virtual de invalidación, la declaración de `TurnOnFor` en la clase `HalogenLight` no utiliza la palabra clave `override`.

## <a name="mix-and-match-capabilities"></a>Funcionalidades de combinación

Las ventajas de los métodos de interfaz predeterminados resultan más claras a medida que se introducen funcionalidades más avanzadas. El uso de interfaces permite combinar las funcionalidades. También permite que cada autor de clase elija entre la implementación predeterminada y una implementación personalizada. Vamos a agregar una interfaz con una implementación predeterminada para una luz parpadeante:

[!code-csharp[Define the blinking light interface](./snippets/mixins-with-default-interface-methods/IBlinkingLight.cs?name=SnippetBlinkingLight)]

La implementación predeterminada permite que cualquier luz parpadee. La luz de techo puede agregar las funcionalidades de temporizador y de parpadeo mediante la implementación predeterminada:

[!code-csharp[Use the default blink function](./snippets/mixins-with-default-interface-methods/OverheadLight.cs?name=SnippetOverheadLight)]

Un nuevo tipo de luz, la clase `LEDLight`, admite la función de temporizador y la función de parpadeo directamente. Este estilo de luz implementa las interfaces `ITimerLight` y `IBlinkingLight`, e invalida el método `Blink`:

[!code-csharp[Override the blink function](./snippets/mixins-with-default-interface-methods/LEDLight.cs?name=SnippetLEDLight)]

La clase `ExtraFancyLight` podría admitir funciones de parpadeo y de temporizador directamente:

[!code-csharp[Override the blink and timer function](./snippets/mixins-with-default-interface-methods/ExtraFancyLight.cs?name=SnippetExtraFancyLight)]

La clase `HalogenLight` que ha creado anteriormente no admite el parpadeo. Por lo tanto, no agregue la interfaz `IBlinkingLight` a la lista de interfaces compatibles.

## <a name="detect-the-light-types-using-pattern-matching"></a>Detección de tipos de luz mediante la coincidencia de patrones

A continuación, vamos a escribir código de prueba. Puede usar la característica de C# de [coincidencia de patrones](../pattern-matching.md) para determinar las funcionalidades de una luz mediante el examen de las interfaces que admite.  El método siguiente ejercita las funcionalidades admitidas por cada luz:

[!code-csharp[Test a light's capabilities](./snippets/mixins-with-default-interface-methods/Program.cs?name=SnippetTestLightFunctions)]

El código siguiente en el método `Main` crea cada tipo de luz secuencialmente y lo prueba:

[!code-csharp[Test a light's capabilities](./snippets/mixins-with-default-interface-methods/Program.cs?name=SnippetMainMethod)]

## <a name="how-the-compiler-determines-best-implementation"></a>Cómo determina el compilador la mejor implementación

En este escenario se muestra una interfaz base sin ninguna implementación. Agregar un método a la interfaz `ILight` presenta nuevas complejidades. Las reglas del lenguaje que rigen los métodos de interfaz predeterminados minimizan el efecto en las clases concretas que implementan varias interfaces derivadas. Vamos a mejorar la interfaz original con un nuevo método para mostrar cómo cambia su uso. Cada luz del indicador puede informar de su estado de energía como un valor enumerado:

[!code-csharp[Enumeration for power status](./snippets/mixins-with-default-interface-methods/ILight.cs?name=SnippetPowerStatus)]

La implementación predeterminada presupone la ausencia de alimentación:

[!code-csharp[Report a default power status](./snippets/mixins-with-default-interface-methods/ILight.cs?name=SnippetILightInterface)]

Estos cambios se compilan correctamente, aunque la clase `ExtraFancyLight` declara la compatibilidad con la interfaz de `ILight` y las interfaces derivadas `ITimerLight` y `IBlinkingLight`. Solo hay una implementación "más cercana" declarada en la interfaz `ILight`. Cualquier clase que declare una invalidación se convertirá en la implementación "más cercana". Ha visto ejemplos en las clases anteriores que reemplazaron los miembros de otras interfaces derivadas.

Evite reemplazar el mismo método en varias interfaces derivadas. Al hacerlo, se crea una llamada de método ambiguo siempre que una clase implementa ambas interfaces derivadas. El compilador no puede elegir un solo método mejor para que emita un error. Por ejemplo, si tanto `IBlinkingLight` como `ITimerLight` implementaron una invalidación de `PowerStatus`, `OverheadLight` tendría que proporcionar una invalidación más específica. De lo contrario, el compilador no puede elegir entre las implementaciones en las dos interfaces derivadas. Normalmente, puede evitar esta situación al mantener las definiciones de interfaz pequeñas y centradas en una característica. En este escenario, cada funcionalidad de una luz es su propia interfaz; solo las clases heredan varias interfaces.

En este ejemplo se muestra un escenario en el que puede definir características discretas que se pueden combinar en clases. Declare cualquier conjunto de funcionalidades admitidas declarando qué interfaces admite una clase. El uso de métodos de interfaz predeterminados virtuales permite a las clases usar o definir una implementación diferente para cualquiera de los métodos de interfaz o para todos. Esta funcionalidad del lenguaje proporciona nuevas formas de modelar los sistemas reales que se están compilando. Los métodos de interfaz predeterminados proporcionan una forma más clara de expresar clases relacionadas que pueden combinar con diferentes características mediante implementaciones virtuales de esas funcionalidades.
