---
title: Contratos de código
description: Explore los contratos de código, que proporcionan una manera de especificar condiciones previas, condiciones posteriores y objetos invariables en el código de .NET.
ms.date: 09/05/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Code contracts
ms.assetid: 84526045-496f-489d-8517-a258cf76f040
ms.openlocfilehash: 60f794373af75bd3f745c224e0a8c7a84192e4c4
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904148"
---
# <a name="code-contracts"></a>Contratos de código

Los contratos de código proporcionan una manera de especificar condiciones previas, condiciones posteriores e invariantes de objeto en el código. Las condiciones previas son requisitos que deben cumplirse al escribir un método o propiedad. Las condiciones posteriores describen las expectativas en el momento en que se cierra el código del método o propiedad. Las invariantes de objeto describen el estado esperado de una clase que está en buen estado.

Los contratos de código incluyen clases para marcar el código, un analizador estático para el análisis de tiempo de compilación y un analizador en tiempo de ejecución. Las clases para contratos de código pueden encontrarse en el espacio de nombres <xref:System.Diagnostics.Contracts>.

Algunas de las ventajas ofrecidas por los contratos de código son:

- Pruebas mejoradas: los contratos de código proporcionan comprobación estática del contrato, comprobación en runtime y generación de documentación.

- Herramientas de prueba automáticas: puede usar los contratos de código para generar pruebas unitarias más significativas eliminando los argumentos de prueba poco importantes que no satisfacen las condiciones previas.

- Comprobación estática: el comprobador estático puede decidir si hay alguna infracción del contrato sin ejecutar el programa. Se comprueban los contratos implícitos, como desreferencias null y límites de matriz, y los contratos explícitos.

- Documentación de referencia: el generador de documentación aumenta los archivos de documentación XML existentes con información de contrato. También hay hojas de estilo que se pueden usar con [Sandcastle](https://github.com/EWSoftware/SHFB) para que las páginas de documentación generadas tengan secciones de contrato.

Todos los lenguajes de .NET Framework pueden beneficiarse de inmediato de los contratos; no es necesario escribir un analizador o compilador especial. Un complemento de Visual Studio le permite especificar el nivel de análisis de contrato de código que se realiza. Los analizadores pueden confirmar si los contratos están correctamente formados (comprobación de tipos y resolución de nombres) y pueden generar un formulario compilado de los contratos en formato de Lenguaje Intermedio de Microsoft (MSIL). La creación de contratos en Visual Studio le permite aprovechar el IntelliSense estándar proporcionado por la herramienta.

La mayoría de los métodos de la clase de contrato se compila condicionalmente; es decir, el compilador emite llamadas a estos métodos solo cuando se define un símbolo especial, CONTRACTS_FULL, mediante la directiva `#define`. CONTRACTS_FULL le permite escribir contratos en su código sin usar directivas `#ifdef`; puede generar diferentes compilaciones, algunas con contratos y otras sin ellos.

Para obtener herramientas e instrucciones detalladas sobre el uso de contratos de código, vea [code Contracts](https://marketplace.visualstudio.com/items?itemName=RiSEResearchinSoftwareEngineering.CodeContractsforNET) en el sitio de Visual Studio Marketplace.

## <a name="preconditions"></a>Preconditions

El método <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType> permite expresar condiciones previas. Las condiciones previas especifican el estado cuando se invoca un método. Generalmente se usan para especificar valores de parámetro válidos. Todos los miembros que se mencionan en las condiciones previas deben ser al menos tan accesibles como el propio método; de lo contrario, es posible que la condición previa no sea entendida por todos los llamadores de un método. La condición no debe tener efectos secundarios. El analizador de runtime determina el comportamiento en tiempo de ejecución de las condiciones previas con errores.

Por ejemplo, la condición previa siguiente expresa que el parámetro `x` debe ser distinto de null.

```csharp
Contract.Requires(x != null);
```

Si el código debe producir una excepción determinada en caso de error de la condición previa, puede usar la sobrecarga genérica de <xref:System.Diagnostics.Contracts.Contract.Requires%2A> del modo siguiente.

```csharp
Contract.Requires<ArgumentNullException>(x != null, "x");
```

### <a name="legacy-requires-statements"></a>La herencia requiere instrucciones

La mayor parte del código contiene alguna validación de parámetros en forma de código `if`-`then`-`throw`. Las herramientas de contrato reconocen estas instrucciones como condiciones previas en los casos siguientes:

- Las instrucciones aparecen antes que cualquier otra instrucción en un método.

- El conjunto completo de tales instrucciones va seguido de una llamada de método <xref:System.Diagnostics.Contracts.Contract> explícita, como una llamada al método <xref:System.Diagnostics.Contracts.Contract.Requires%2A>, <xref:System.Diagnostics.Contracts.Contract.Ensures%2A>, <xref:System.Diagnostics.Contracts.Contract.EnsuresOnThrow%2A> o <xref:System.Diagnostics.Contracts.Contract.EndContractBlock%2A>.

Cuando las instrucciones `if`-`then`-`throw` aparecen en este formato, las herramientas las reconocen como instrucciones `requires` heredadas. Si ningún otro contrato sigue la secuencia `if`-`then`-`throw`, finalice el código con el método <xref:System.Diagnostics.Contracts.Contract.EndContractBlock%2A?displayProperty=nameWithType>.

```csharp
if (x == null) throw new ...
Contract.EndContractBlock(); // All previous "if" checks are preconditions
```

Tenga en cuenta que la condición en la prueba anterior es una condición previa negada (La condición previa real sería `x != null` ). Una condición previa negada está muy restringida: debe escribirse como se muestra en el ejemplo anterior. es decir, no debe contener `else` cláusulas y el cuerpo de la `then` cláusula debe ser una sola `throw` instrucción. La prueba `if` está sujeta a reglas de pureza y de visibilidad (vea las [instrucciones de uso](#usage_guidelines)), pero la expresión `throw` solo está sujeta a reglas de pureza. Sin embargo, el tipo de la excepción generada debe ser tan visible como el método en el que se produce el contrato.

## <a name="postconditions"></a>Condiciones posteriores

Las condiciones posteriores son contratos para el estado de un método cuando finaliza. La condición posterior se comprueba justo antes de salir de un método. El analizador de runtime determina el comportamiento en tiempo de ejecución de las condiciones posteriores con errores.

A diferencia de las condiciones previas, las condiciones posteriores pueden hacer referencia a miembros con menos visibilidad. Es posible que algún cliente no sea capaz de entender o usar parte de la información expresada por una condición posterior mediante el estado privado, pero esto no afecta a la capacidad del cliente para usar el método correctamente.

### <a name="standard-postconditions"></a>Condiciones posteriores estándar

El método <xref:System.Diagnostics.Contracts.Contract.Ensures%2A> permite expresar condiciones posteriores estándar. Las condiciones posteriores expresan una condición que debe ser `true` tras la finalización normal del método.

```csharp
Contract.Ensures(this.F > 0);
```

### <a name="exceptional-postconditions"></a>Condiciones posteriores excepcionales

Las condiciones posteriores excepcionales son condiciones posteriores que deberían ser `true` cuando un método genera una determinada excepción. Estas condiciones posteriores se pueden especificar mediante el método <xref:System.Diagnostics.Contracts.Contract.EnsuresOnThrow%2A?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente.

```csharp
Contract.EnsuresOnThrow<T>(this.F > 0);
```

El argumento es la condición que debe ser `true` cada vez que se genera una excepción que es un subtipo de `T`.

Hay algunos tipos de excepciones que son difíciles de usar en una condición posterior excepcional. Por ejemplo, para usar el tipo <xref:System.Exception> para `T` es necesario que el método garantice la condición con independencia del tipo de excepción que se genera, incluso si es un desbordamiento de pila u otra excepción imposible de controlar. Las condiciones posteriores excepcionales deben usarse solo para excepciones concretas que puedan producirse cuando se llama a un miembro, por ejemplo, cuando se produce un <xref:System.InvalidTimeZoneException> para una llamada al método <xref:System.TimeZoneInfo>.

### <a name="special-postconditions"></a>Condiciones posteriores especiales

Los métodos siguientes pueden usarse únicamente dentro de condiciones posteriores:

- La referencia a valores devueltos del método en condiciones posteriores se realiza mediante la expresión `Contract.Result<T>()`, donde `T` se sustituye por el tipo de valor devuelto del método. Cuando el compilador no puede inferir el tipo, debe proporcionarse explícitamente. Por ejemplo, el compilador de C# no puede inferir tipos para los métodos que no toman ningún argumento, por lo que requiere la siguiente condición posterior: `Contract.Ensures(0 <Contract.Result<int>())`. Los métodos con un tipo de valor devuelto de `void` no puede hacer referencia a `Contract.Result<T>()` en sus condiciones posteriores.

- Un valor preindicado en una condición posterior hace referencia al valor de una expresión en el inicio de un método o propiedad. Se usa la expresión `Contract.OldValue<T>(e)`, donde `T` es el tipo de `e`. Puede omitir el argumento de tipo genérico siempre que el compilador pueda deducir su tipo. (Por ejemplo, el compilador de C# siempre infiere el tipo porque toma un argumento). Existen varias restricciones sobre lo que puede ocurrir en `e` y los contextos en los que puede aparecer una expresión antigua. Una expresión antigua no puede contener otra expresión antigua. Lo más importante es que una expresión antigua debe hacer referencia a un valor que existía en el estado de condición previa del método. En otras palabras, debe ser una expresión que pueda evaluarse siempre que la condición previa del método sea `true`. A continuación se muestran varias instancias de esa regla.

  - El valor debe existir en el estado de condición previa del método. Para hacer referencia a un campo en un objeto, las condiciones previas deben garantizar que el objeto siempre es distinto de NULL.

  - No es posible hacer referencia al valor devuelto del método en una expresión antigua:

      ```csharp
      Contract.OldValue(Contract.Result<int>() + x) // ERROR
      ```

  - No es posible hacer referencia a parámetros `out` en una expresión antigua.

  - Una expresión antigua no puede depender de la variable dependiente de un cuantificador si el intervalo del cuantificador depende del valor devuelto del método:

      ```csharp
      Contract.ForAll(0, Contract.Result<int>(), i => Contract.OldValue(xs[i]) > 3); // ERROR
      ```

  - Una expresión antigua no puede hacer referencia al parámetro del delegado anónimo en una llamada <xref:System.Diagnostics.Contracts.Contract.ForAll%2A> o <xref:System.Diagnostics.Contracts.Contract.Exists%2A> a menos que se use como indizador o argumento para una llamada al método:

      ```csharp
      Contract.ForAll(0, xs.Length, i => Contract.OldValue(xs[i]) > 3); // OK
      Contract.ForAll(0, xs.Length, i => Contract.OldValue(i) > 3); // ERROR
      ```

  - Una expresión antigua no se puede realizar en el cuerpo de un delegado anónimo si el valor de la expresión antigua depende de cualquiera de los parámetros del delegado anónimo, a menos que el delegado anónimo sea un argumento para el método <xref:System.Diagnostics.Contracts.Contract.ForAll%2A> o <xref:System.Diagnostics.Contracts.Contract.Exists%2A>:

      ```csharp
      Method(... (T t) => Contract.OldValue(... t ...) ...); // ERROR
      ```

  - Los parámetros `Out` presentan un problema porque los contratos aparecen antes del cuerpo del método y la mayoría de los compiladores no permite referencias a parámetros `out` en condiciones posteriores. Para resolver este problema, la clase <xref:System.Diagnostics.Contracts.Contract> proporciona el método <xref:System.Diagnostics.Contracts.Contract.ValueAtReturn%2A>, lo que permite una condición posterior basada en un parámetro `out`.

      ```csharp
      public void OutParam(out int x)
      {
          Contract.Ensures(Contract.ValueAtReturn(out x) == 3);
          x = 3;
      }
      ```

      Al igual que con el método <xref:System.Diagnostics.Contracts.Contract.OldValue%2A>, puede omitir el parámetro de tipo genérico siempre que el compilador pueda deducir su tipo. El sistema de reescritura del contrato reemplaza la llamada de método por el valor del parámetro `out`. El método <xref:System.Diagnostics.Contracts.Contract.ValueAtReturn%2A> solo aparece en las condiciones posteriores. El argumento para el método debe ser un parámetro `out` o un campo de un parámetro `out` de estructura. Este último también es útil cuando se hace referencia a los campos de la condición posterior de un constructor de estructura.

      > [!NOTE]
      > Actualmente, las herramientas de análisis de contrato de código no comprueban si los parámetros `out` se inicializan correctamente y desechan su mención en la condición posterior. Por lo tanto, en el ejemplo anterior, si la línea después del contrato hubiera usado el valor de `x` en lugar de asignarle un entero, un compilador no emitiría el error correcto. Pero en una compilación donde el símbolo de preprocesador CONTRACTS_FULL (por ejemplo, una compilación de versión) no está definido, el compilador emite un error.

## <a name="invariants"></a>Invariables

Las invariantes de objetos son condiciones que deben cumplirse para cada instancia de una clase siempre que ese objeto sea visible para un cliente. Expresan las condiciones en las que el objeto se considera correcto.

Los métodos invariantes se identifican por estar marcados con el atributo <xref:System.Diagnostics.Contracts.ContractInvariantMethodAttribute>. Los métodos invariantes no deben contener ningún código salvo una secuencia de llamadas al método <xref:System.Diagnostics.Contracts.Contract.Invariant%2A>, cada uno de los cuales especifica una invariante individual, como se muestra en el ejemplo siguiente.

```csharp
[ContractInvariantMethod]
protected void ObjectInvariant ()
{
    Contract.Invariant(this.y >= 0);
    Contract.Invariant(this.x > this.y);
    ...
}
```

Las invariantes se definen condicionalmente mediante el símbolo de preprocesador CONTRACTS_FULL. Durante la comprobación en tiempo de ejecución, las invariantes se comprueban al final de cada método público. Si una invariante menciona un método público en la misma clase, se deshabilita la comprobación de invariante que normalmente se produciría normalmente al final de ese método público. En su lugar, la comprobación se produce solo al final de la llamada de método más externo a esa clase. Esto también ocurre si la clase se vuelve a escribir debido a una llamada a un método en otra clase. No se comprueban las invariables para un finalizador de objeto y una <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementación de.

<a name="usage_guidelines"></a>

## <a name="usage-guidelines"></a>Instrucciones de uso

### <a name="contract-ordering"></a>Clasificación de contratos

En la tabla siguiente se muestra el orden de los elementos que debe usarse al escribir contratos de método.

|`If-then-throw statements`|Condiciones previas públicas compatibles con versiones anteriores.|
|-|-|
|<xref:System.Diagnostics.Contracts.Contract.Requires%2A>|Todas las condiciones previas públicas.|
|<xref:System.Diagnostics.Contracts.Contract.Ensures%2A>|Todas las condiciones posteriores públicas (normales).|
|<xref:System.Diagnostics.Contracts.Contract.EnsuresOnThrow%2A>|Todas las condiciones posteriores públicas excepcionales.|
|<xref:System.Diagnostics.Contracts.Contract.Ensures%2A>|Todas las condiciones posteriores privadas/internas (normales).|
|<xref:System.Diagnostics.Contracts.Contract.EnsuresOnThrow%2A>|Todas las condiciones posteriores privadas/internas excepcionales.|
|<xref:System.Diagnostics.Contracts.Contract.EndContractBlock%2A>|Si usa condiciones previas de estilo `if`-`then`-`throw` sin ningún otro contrato, coloque una llamada a <xref:System.Diagnostics.Contracts.Contract.EndContractBlock%2A> para indicar que todas las comprobaciones if anteriores son requisitos previos.|

<a name="purity"></a>

### <a name="purity"></a>Pureza

Todos los métodos que se llaman dentro de un contrato deben ser puros, es decir, no deben actualizar ningún estado preexistente. Un método puro puede modificar objetos que se han creado después de la entrada en el método puro.

Las herramientas de contratos de código asumen que los siguientes elementos de código son puros:

- Métodos marcados con <xref:System.Diagnostics.Contracts.PureAttribute>.

- Tipos marcados con <xref:System.Diagnostics.Contracts.PureAttribute> (el atributo se aplica a todos los métodos del tipo).

- Descriptores de acceso get de propiedad.

- Operadores (métodos estáticos cuyo nombre empieza por "op" y que tienen uno o dos parámetros y un tipo de valor devuelto distinto de void).

- Cualquier método cuyo nombre completo empieza por "System.Diagnostics.Contracts.Contract", "System.String", "System.IO.Path" o "System.Type".

- Cualquier delegado invocado, siempre que el propio tipo delegado se atribuya con <xref:System.Diagnostics.Contracts.PureAttribute>. Los tipos de delegado <xref:System.Predicate%601?displayProperty=nameWithType> y <xref:System.Comparison%601?displayProperty=nameWithType> se consideran puros.

<a name="visibility"></a>

### <a name="visibility"></a>Visibilidad

Todos los miembros mencionados en un contrato deben ser al menos tan visibles como el método en que aparecen. Por ejemplo, un campo privado no se puede mencionar en una condición previa para un método público; los clientes no pueden validar el contrato antes de llamar al método. Sin embargo, si el campo está marcado con <xref:System.Diagnostics.Contracts.ContractPublicPropertyNameAttribute>, está exento de estas reglas.

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se muestra el uso de contratos de código.

[!code-csharp[ContractExample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/contractexample/cs/program.cs#1)]
[!code-vb[ContractExample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/contractexample/vb/program.vb#1)]
