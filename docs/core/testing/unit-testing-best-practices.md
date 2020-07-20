---
title: Procedimientos recomendados para escribir pruebas unitarias
description: Obtenga información sobre los procedimientos recomendados para escribir pruebas unitarias que mejoren la calidad y la resistencia del código para proyectos de NET Core y .NET Standard.
author: jpreese
ms.author: wiwagn
ms.date: 07/28/2018
ms.openlocfilehash: ffeaa1e11512cab64695c120f844594b8c5014a8
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281113"
---
# <a name="unit-testing-best-practices-with-net-core-and-net-standard"></a>Procedimientos recomendados de pruebas unitarias con .NET Core y .NET Standard

La escritura de pruebas unitarias reporta muchos beneficios; las pruebas ayudan con la regresión, proporcionan documentación y facilitan un buen diseño. Pero también son difíciles de leer y, si son frágiles, pueden causar estragos en el código base. En este artículo se describen algunos procedimientos recomendados sobre el diseño de pruebas unitarias para proyectos de .NET Core y .NET Standard.

En esta guía, aprenderá algunos procedimientos recomendados para escribir pruebas unitarias resistentes y fáciles de entender.

De [John Reese](https://reese.dev), con agradecimientos especiales a [Roy Osherove](https://osherove.com/)

## <a name="why-unit-test"></a>El porqué de las pruebas unitarias

### <a name="less-time-performing-functional-tests"></a>Menos tiempo para realizar pruebas funcionales

Las pruebas funcionales son costosas. Normalmente implican la apertura de la aplicación y la realización de una serie de pasos que usted (u otro usuario) debe seguir para validar el comportamiento esperado. Es posible que estos pasos no sean siempre conocidos para el evaluador, lo que significa tener que recurrir a alguien con más conocimientos en el tema para llevar a cabo la prueba. Las pruebas en sí mismas podrían llevar segundos en el caso de cambios triviales, o minutos en el de cambios más importantes. Por último, este proceso debe repetirse para cada cambio que se realice en el sistema.

Por otra parte, las pruebas unitarias duran milisegundos, se pueden ejecutar con solo presionar un botón y no exigen necesariamente ningún conocimiento del sistema en general. El que la prueba se supere o no depende del ejecutor de pruebas, no del usuario.

### <a name="protection-against-regression"></a>Protección frente a regresión

Los defectos de regresión son aquellos que se presentan cuando se realiza un cambio en la aplicación. Es habitual que los evaluadores no solo prueben una nueva característica, sino también las ya existentes con el fin de comprobar que siguen funcionando según lo previsto.

Con las pruebas unitarias, es posible volver a ejecutar el conjunto completo de pruebas después de cada compilación o incluso después de cambiar una línea de código. Eso da confianza en que el nuevo código no interrumpa la funcionalidad existente.

### <a name="executable-documentation"></a>Documentación ejecutable

Es posible que no siempre sea evidente lo que hace un método determinado o cómo se comporta ante una acción concreta. Es posible que se pregunte: ¿cómo se comporta este método si se le pasa una cadena en blanco? ¿Null?

Si tiene un conjunto de pruebas unitarias con un nombre adecuado, cada prueba debe ser capaz de explicar con claridad el resultado esperado de una acción determinada. Además, debe ser capaz de comprobar que funciona.

### <a name="less-coupled-code"></a>Menos código acoplado

Cuando el código está estrechamente acoplado, puede resultar difícil realizar pruebas unitarias. Sin crear pruebas unitarias para el código que se está escribiendo, el acoplamiento puede ser menos evidente.

Al escribir pruebas para el código, este se desacopla naturalmente, ya que, de otra forma, sería más difícil de probar.

## <a name="characteristics-of-a-good-unit-test"></a>Características de una buena prueba unitaria

- **Rápida**. No es infrecuente que los proyectos maduros tengan miles de pruebas unitarias. Las pruebas unitarias deberían tardar muy poco tiempo en ejecutarse. Milisegundos.
- **Aislada**. Las pruebas unitarias son independientes, se pueden ejecutar de forma aislada y no tienen ninguna dependencia en ningún factor externo, como sistemas de archivos o bases de datos.
- **Reiterativa**. La ejecución de una prueba unitaria debe ser coherente con sus resultados, es decir, devolver siempre el mismo resultado si no cambia nada entre ejecuciones.
- **Autocomprobada**. La prueba debe ser capaz de detectar automáticamente si el resultado ha sido correcto o incorrecto sin necesidad de intervención humana.
- **Oportuna**. Una prueba unitaria no debe tardar un tiempo desproporcionado en escribirse en comparación con el código que se va a probar. Si observa que la prueba del código tarda mucho en comparación con su escritura, considere un diseño más fácil de probar.

## <a name="code-coverage"></a>Cobertura de código

Un alto porcentaje de cobertura de código suele ir asociado a una mayor calidad del código. Pero la medida en sí *no puede* determinar la calidad del código. La configuración de un objetivo de porcentaje de cobertura de código excesivamente ambicioso puede ser contraproducente. Imagine un proyecto complejo con miles de ramas condicionales e imagine que establece un objetivo de cobertura de código del 95 %. Actualmente, el proyecto mantiene una cobertura de código del 90 %. La cantidad de tiempo que lleva cubrir todos los casos del 5 % restante puede ser un esfuerzo enorme y la propuesta de valor disminuye rápidamente.

Un alto porcentaje de cobertura de código no es un indicador de éxito, ni implica una alta calidad del código. Simplemente representa la cantidad de código cubierta por las pruebas unitarias. Para obtener más información, vea [Cobertura de código de pruebas unitarias](unit-testing-code-coverage.md).

## <a name="lets-speak-the-same-language"></a>Vamos a hablar el mismo idioma

Desafortunadamente, el término *ficticio* se emplea de forma incorrecta al referirse a las pruebas. Los puntos siguientes definen los tipos más comunes de *emulaciones* al escribir pruebas unitarias:

*Emulación*: una emulación es un término genérico que se puede usar para describir un stub o un objeto ficticio. Si es un stub o un objeto ficticio depende del contexto en el que se use. Es decir, una emulación puede ser un stub o un objeto ficticio.

*Objeto ficticio*: un objeto ficticio es una emulación del sistema que decide si una prueba unitaria se ha superado o no. Un objeto ficticio comienza como una emulación hasta que se declara una instrucción Assert en ella.

*Stub*: un stub es un reemplazo controlable para una dependencia existente (o colaborador) en el sistema. Con un stub, puede probar el código sin tratar directamente con la dependencia. De forma predeterminada, una emulación empieza como un stub.

Tenga en cuenta el fragmento de código siguiente:

```csharp
var mockOrder = new MockOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

Es un ejemplo de stub al que se hace referencia como un objeto ficticio. En este caso, es un stub. Simplemente está pasando el pedido para poder crear una instancia de `Purchase` (el sistema sometido a prueba). El nombre `MockOrder` también es confuso porque, una vez más, el pedido no es un objeto ficticio.

Un mejor enfoque sería

```csharp
var stubOrder = new FakeOrder();
var purchase = new Purchase(stubOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

Al cambiar el nombre de la clase `FakeOrder`, la ha convertido en mucho más genérica, con lo que puede usarse como objeto ficticio o stub. Lo que sea mejor para el caso de prueba. En el ejemplo anterior, `FakeOrder` se usa como un stub. No usa `FakeOrder` de ninguna forma durante la aserción. `FakeOrder` se ha pasado a la clase `Purchase` para satisfacer los requisitos del constructor.

Para usarlo como un objeto ficticio, podría hacer algo parecido a esto:

```csharp
var mockOrder = new FakeOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(mockOrder.Validated);
```

En este caso, va a registrar una propiedad en la emulación (la declara en ella), por lo que en el fragmento de código anterior, `mockOrder` es un objeto simulado.

> [!IMPORTANT]
> Es importante tener clara esta terminología. Si se denomina a los stubs "objetos ficticios", los demás desarrolladores van a realizar suposiciones falsas sobre su intención.

Lo principal que debe recordar sobre los objetos ficticios frente a los stubs es que los objetos ficticios son como los stubs, pero se declara en el objeto ficticio, y no en un stub.

## <a name="best-practices"></a>Procedimientos recomendados

### <a name="naming-your-tests"></a>Asignar nombre a las pruebas

El nombre de la prueba debe constar de tres partes:

- Nombre del método que se va a probar.
- Escenario en el que se está probando.
- Comportamiento esperado al invocar al escenario.

#### <a name="why"></a>¿Por qué?

- Los estándares de nomenclatura son importantes porque expresan de forma explícita la intención de la prueba.

Las pruebas van más allá de garantizar que el código funciona, también proporcionan documentación. Con solo mirar el conjunto de pruebas unitarias, debe ser capaz de deducir el comportamiento del código sin ni siquiera mirar el propio código. Además, cuando no se superan las pruebas, puede ver exactamente qué escenarios no cumplen las expectativas.

#### <a name="bad"></a>Malo:

[!code-csharp[BeforeNaming](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeNaming)]

#### <a name="better"></a>Mejor:

[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="arranging-your-tests"></a>Organizar las pruebas

**Organizar, actuar, declarar** es un patrón común al realizar pruebas unitarias. Como el propio nombre implica, consta de tres acciones principales:

- *Organizar* los objetos, crearlos y configurarlos según sea necesario.
- *Actuar* en un objeto.
- *Declarar* que algo es como se espera.

#### <a name="why"></a>¿Por qué?

- Separa claramente lo que se está probando de los pasos *organizar* y *declarar*.
- Menos posibilidad de mezclar aserciones con el código para "actuar".

La legibilidad es uno de los aspectos más importantes a la hora de escribir una prueba. Al separar cada una de estas acciones dentro de la prueba, se resaltan claramente las dependencias necesarias para llamar al código, la forma de llamarlo y lo que se intenta declarar. Aunque es posible combinar algunos pasos y reducir el tamaño de la prueba, el objetivo principal es que sea lo más legible posible.

#### <a name="bad"></a>Malo:

[!code-csharp[BeforeArranging](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeArranging)]

#### <a name="better"></a>Mejor:

[!code-csharp[AfterArranging](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterArranging)]

### <a name="write-minimally-passing-tests"></a>Escribir pruebas correctas lo más sencillas posible

La entrada que se use en una prueba unitaria debe ser lo más sencilla posible para comprobar el comportamiento que se está probando.

#### <a name="why"></a>¿Por qué?

- Las pruebas se hacen más resistentes a los cambios futuros en el código base.
- Más cercano al comportamiento de prueba que a la implementación.

Las pruebas que incluyen más información de la necesaria para superarse tienen una mayor posibilidad de incorporar errores en la prueba y pueden hacer confusa su intención. Al escribir pruebas, queremos centrarnos en el comportamiento. El establecimiento de propiedades adicionales en los modelos o el empleo de valores distintos de cero cuando no es necesario solo resta de lo que se quiere probar.

#### <a name="bad"></a>Malo:

[!code-csharp[BeforeMinimallyPassing](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeMinimallyPassing)]

#### <a name="better"></a>Mejor:

[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="avoid-magic-strings"></a>Evitar cadenas mágicas

La asignación de nombres a las variables de las pruebas unitarias es tan importante, si no más, que la asignación de nombres a las variables del código de producción. Las pruebas unitarias no deben contener cadenas mágicas.

#### <a name="why"></a>¿Por qué?

- Evita la necesidad de que el lector de la prueba inspeccione el código de producción con el fin de averiguar lo que hace que el valor sea especial.
- Muestra explícitamente lo que se intenta *probar*, en lugar de lo que se intenta *lograr*.

Las cadenas mágicas pueden provocar confusión al lector de las pruebas. Si una cadena tiene un aspecto fuera de lo normal, puede preguntarse por qué se ha elegido un determinado valor para un parámetro o valor devuelto. Esto puede dar lugar a un vistazo más detallado a los detalles de implementación, en lugar de centrarse en la prueba.

> [!TIP]
> Al escribir pruebas, su objetivo debe ser expresar tanta intención como sea posible. En el caso de las cadenas mágicas, un buen enfoque es asignar estos valores a constantes.

#### <a name="bad"></a>Malo:

[!code-csharp[BeforeMagicString](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeMagicString)]

#### <a name="better"></a>Mejor:

[!code-csharp[AfterMagicString](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterMagicString)]

### <a name="avoid-logic-in-tests"></a>Evitar la lógica en las pruebas

Al escribir las pruebas unitarias, evite la concatenación de cadenas manual y las condiciones lógicas como `if`, `while`, `for`, `switch`, etc.

#### <a name="why"></a>¿Por qué?

- Menos posibilidad de incorporar un error a las pruebas.
- El foco está en el resultado final, en lugar de en los detalles de implementación.

Al incorporar lógica al conjunto de pruebas, aumenta considerablemente la posibilidad de agregar un error. El último lugar en el que se quiere encontrar un error es el conjunto de pruebas. Debe tener mucha confianza en que las pruebas funcionan, de lo contrario, no confiará en ellas. Las pruebas en las que no se confía, no proporcionan ningún valor. Cuando se produce un error en una prueba, quiere saber que algo va mal realmente con el código y que no se puede omitir.

> [!TIP]
> Si la lógica en la prueba parece inevitable, considere la posibilidad de dividirla en dos o más pruebas diferentes.

#### <a name="bad"></a>Malo:

[!code-csharp[LogicInTests](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#LogicInTests)]

#### <a name="better"></a>Mejor:

[!code-csharp[AfterTestLogic](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterTestLogic)]

### <a name="prefer-helper-methods-to-setup-and-teardown"></a>Se prefieren métodos auxiliares a la instalación y el desmontaje

Si necesita un objeto o un estado similares para las pruebas, se prefiere un método auxiliar al aprovechamiento de los atributos de instalación y desmontaje, si existen.

#### <a name="why"></a>¿Por qué?

- Menos confusión al leer las pruebas, puesto que todo el código es visible desde dentro de cada prueba.
- Menor posibilidad de configurar demasiado o muy poco para la prueba.
- Menor posibilidad de compartir el estado entre las pruebas, lo que crea dependencias no deseadas entre ellas.

En los marcos de trabajo de pruebas unitarias, se llama a `Setup` antes de cada prueba unitaria del conjunto de pruebas. Aunque algunos puedan verlo como una herramienta útil, por lo general termina por dar lugar a pruebas recargadas y difíciles de leer. Cada prueba normalmente tendrá requisitos diferentes para funcionar y ejecutarse. Por desgracia, `Setup` obliga a usar los mismos requisitos para cada prueba.

> [!NOTE]
> xUnit ha quitado la instalación y el desmontaje a partir de la versión 2.x

#### <a name="bad"></a>Malo:

[!code-csharp[BeforeSetup](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeSetup)]

```csharp
// more tests...
```

[!code-csharp[BeforeHelperMethod](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeHelperMethod)]

#### <a name="better"></a>Mejor:

[!code-csharp[AfterHelperMethod](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterHelperMethod)]

```csharp
// more tests...
```

[!code-csharp[AfterSetup](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterSetup)]

### <a name="avoid-multiple-asserts"></a>Evitar varias aserciones

Al escribir las pruebas, intente incluir solo una aserción por prueba. Los enfoques comunes para usar solo una aserción incluyen:

- Crear una prueba independiente para cada aserción.
- Usar pruebas con parámetros.

#### <a name="why"></a>¿Por qué?

- Si se produce un error en una aserción, no se evalúan las aserciones posteriores.
- Garantiza que no se estén declarando varios casos en las pruebas.
- Proporciona la imagen completa de por qué se producen errores en las pruebas.

Al incorporar varias aserciones en un caso de prueba, no se garantiza que se ejecuten todas. En la mayoría de los marcos de trabajo de pruebas unitarias, una vez que se produce un error en una aserción de una prueba unitaria, las pruebas siguientes se consideran erróneas automáticamente. Esto puede ser confuso, ya que funciones que realmente están funcionando se muestran como erróneas.

> [!NOTE]
> Una excepción común a esta regla es cuando se declara en un objeto. En este caso, suele ser aceptable que haya varias aserciones en cada propiedad para asegurarse de que el objeto está en el estado que se espera que esté.

#### <a name="bad"></a>Malo:

[!code-csharp[BeforeMultipleAsserts](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeMultipleAsserts)]

#### <a name="better"></a>Mejor:

[!code-csharp[AfterMultipleAsserts](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterMultipleAsserts)]

### <a name="validate-private-methods-by-unit-testing-public-methods"></a>Validar métodos privados mediante la prueba unitaria de métodos públicos

En la mayoría de los casos, no debería haber necesidad de probar un método privado. Los métodos privados son un detalle de implementación. Se puede considerar de esta forma: los métodos privados nunca existen de forma aislada. En algún momento, va a haber un método público que llame al método privado como parte de su implementación. Lo que debería importarle es el resultado final del método público que llama al privado.

Considere el caso siguiente

```csharp
public string ParseLogLine(string input)
{
    var sanitizedInput = TrimInput(input);
    return sanitizedInput;
}

private string TrimInput(string input)
{
    return input.Trim();
}
```

Su primera reacción puede ser empezar a escribir una prueba para `TrimInput` porque quiere asegurarse de que el método funciona según lo previsto. Pero es muy posible que `ParseLogLine` manipule a `sanitizedInput` de una forma totalmente imprevista, con lo que una prueba en `TrimInput` sería inútil.

La prueba real debe realizarse en el método público `ParseLogLine`, porque eso es lo debe importarle en última instancia.

```csharp
public void ParseLogLine_StartsAndEndsWithSpace_ReturnsTrimmedResult()
{
    var parser = new Parser();

    var result = parser.ParseLogLine(" a ");

    Assert.Equals("a", result);
}
```

Con este punto de vista, si ve un método privado, busque el método público y escriba las pruebas en ese método. Simplemente porque un método privado devuelva el resultado esperado, no significa que el sistema que finalmente llama al método privado use el resultado correctamente.

### <a name="stub-static-references"></a>Referencias estáticas de stub

Uno de los principios de una prueba unitaria es que debe tener control total del sistema sometido a prueba. Esto puede ser problemático cuando el código de producción incluye llamadas a referencias estáticas (por ejemplo, `DateTime.Now`). Considere el código siguiente

```csharp
public int GetDiscountedPrice(int price)
{
    if (DateTime.Now.DayOfWeek == DayOfWeek.Tuesday)
    {
        return price / 2;
    }
    else
    {
        return price;
    }
}
```

¿Cómo se podrían realizar pruebas unitarias de este código? Puede probar un enfoque como

```csharp
public void GetDiscountedPrice_NotTuesday_ReturnsFullPrice()
{
    var priceCalculator = new PriceCalculator();

    var actual = priceCalculator.GetDiscountedPrice(2);

    Assert.Equals(2, actual)
}

public void GetDiscountedPrice_OnTuesday_ReturnsHalfPrice()
{
    var priceCalculator = new PriceCalculator();

    var actual = priceCalculator.GetDiscountedPrice(2);

    Assert.Equals(1, actual);
}
```

Lamentablemente, pronto comprobará que hay un par de problemas con las pruebas.

- Si el conjunto de pruebas se ejecuta un martes, se superará la segunda prueba, pero se producirá un error en la primera.
- Si el conjunto de pruebas se ejecuta otro día, se superará la primera prueba, pero se producirá un error en la segunda.

Para solucionar estos problemas, debe incorporar un *arreglo* en el código de producción. Un enfoque consiste en encapsular el código que necesita controlar en una interfaz y hacer que el código de producción dependa de esa interfaz.

```csharp
public interface IDateTimeProvider
{
    DayOfWeek DayOfWeek();
}

public int GetDiscountedPrice(int price, IDateTimeProvider dateTimeProvider)
{
    if (dateTimeProvider.DayOfWeek() == DayOfWeek.Tuesday)
    {
        return price / 2;
    }
    else
    {
        return price;
    }
}
```

El conjunto de pruebas ahora se convierte

```csharp
public void GetDiscountedPrice_NotTuesday_ReturnsFullPrice()
{
    var priceCalculator = new PriceCalculator();
    var dateTimeProviderStub = new Mock<IDateTimeProvider>();
    dateTimeProviderStub.Setup(dtp => dtp.DayOfWeek()).Returns(DayOfWeek.Monday);

    var actual = priceCalculator.GetDiscountedPrice(2, dateTimeProviderStub);

    Assert.Equals(2, actual);
}

public void GetDiscountedPrice_OnTuesday_ReturnsHalfPrice()
{
    var priceCalculator = new PriceCalculator();
    var dateTimeProviderStub = new Mock<IDateTimeProvider>();
    dateTimeProviderStub.Setup(dtp => dtp.DayOfWeek()).Returns(DayOfWeek.Tuesday);

    var actual = priceCalculator.GetDiscountedPrice(2, dateTimeProviderStub);

    Assert.Equals(1, actual);
}
```

Ahora el conjunto de pruebas tiene control total sobre `DateTime.Now` y puede convertir en stub cualquier valor al llamar al método.
