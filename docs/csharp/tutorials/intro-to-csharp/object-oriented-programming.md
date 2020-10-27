---
title: Programación orientada a objetos (C#)
description: C# proporciona compatibilidad completa para la programación orientada a objetos incluida la abstracción, la encapsulación, la herencia y el polimorfismo.
ms.date: 09/30/2020
ms.openlocfilehash: 353edf8fc68f495f3d875fa678aaaf91f1fd6406
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471600"
---
# <a name="object-oriented-programming-c"></a>Programación orientada a objetos (C#)

C# es un lenguaje orientado a objetos. Cuatro de las técnicas clave que se usan en la programación orientada a objetos son:

- La *abstracción* significa ocultar los detalles innecesarios de los consumidores de tipos.
- La *encapsulación* significa que un grupo de propiedades, métodos y otros miembros relacionados se tratan como una sola unidad u objeto.
- La *herencia* describe la posibilidad de crear nuevas clases basadas en una clase existente.
- El *polimorfismo* significa que puede tener múltiples clases que se pueden usar de manera intercambiable, aunque cada clase implementa las mismas propiedades o los mismos métodos de maneras diferentes.

En el tutorial anterior, [Introducción a las clases](introduction-to-classes.md) se trató la *abstracción* y la *encapsulación* . La clase `BankAccount` proporcionó una abstracción para el concepto de una cuenta bancaria. Puede modificar su implementación sin que afecte para nada al código que usó la clase `BankAccount`. Las clases `BankAccount` y `Transaction` proporcionan encapsulación de los componentes necesarios para describir esos conceptos en el código.

En este tutorial, ampliará la aplicación para hacer uso de la *herencia* y el *polimorfismo* para agregar nuevas características. También agregará características a la clase `BankAccount`, aprovechando las técnicas de *abstracción* y *encapsulación* que aprendió en el tutorial anterior.

## <a name="create-different-types-of-accounts"></a>Creación de diferentes tipos de cuentas

Después de compilar este programa, recibirá solicitudes para agregarle características. Funciona bien en situaciones en las que solo hay un tipo de cuenta bancaria. Con el tiempo, las necesidades cambian y se solicitan tipos de cuenta relacionados:

- Una cuenta que devenga intereses que genera beneficios al final de cada mes.
- Una línea de crédito que puede tener un saldo negativo, pero cuando sea así, se producirá un cargo por intereses cada mes.
- Una cuenta de tarjeta de regalo de prepago que comienza con un único depósito y solo se puede liquidar. Se puede recargar una vez al principio de cada mes.

Todas estas cuentas diferentes son similares a la clase `BankAccount` definida en el tutorial anterior. Podría copiar ese código, cambiar el nombre de las clases y realizar modificaciones. Esa técnica funcionaría a corto plazo, pero a la larga supondría más trabajo. Cualquier cambio se copiará en todas las clases afectadas.

En su lugar, puede crear nuevos tipos de cuenta bancaria que hereden métodos y datos de la clase `BankAccount` creada en el tutorial anterior. Estas clases nuevas pueden extender la clase `BankAccount` con el comportamiento específico necesario para cada tipo:

```csharp
public class InterestEarningAccount : BankAccount
{
}

public class LineOfCreditAccount : BankAccount
{
}

public class GiftCardAccount : BankAccount
{
}
```

Cada una de estas clases *hereda* el comportamiento compartido de su *clase base* compartida, la clase `BankAccount`. Escriba las implementaciones para la funcionalidad nueva y diferente en cada una de las *clases derivadas* .  Estas clases derivadas ya tienen todo el comportamiento definido en la clase `BankAccount`.

Es recomendable crear cada clase nueva en un archivo de código fuente diferente. En [Visual Studio](https://visualstudio.com), puede hacer clic con el botón derecho en el proyecto y seleccionar *Agregar clase* para agregar una clase nueva en un archivo nuevo. En [Visual Studio Code](https://code.visualstudio.com), seleccione *Archivo* y luego *Nuevo* para crear un nuevo archivo de código fuente. En cualquier herramienta, ponga un nombre al archivo que coincida con la clase: *InterestEarningAccount.cs* , *LineOfCreditAccount.cs* y *GiftCardAccount.cs* .

Cuando cree las clases como se muestra en el ejemplo anterior, observará que ninguna de las clases derivadas se compila. La inicialización de un objeto es responsabilidad de un constructor. Un constructor de clase derivada debe inicializar la clase derivada y proporcionar instrucciones sobre cómo inicializar el objeto de la clase base incluido en la clase derivada. Normalmente, se produce una inicialización correcta sin ningún código adicional. La clase `BankAccount` declara un constructor público con la siguiente firma:

```csharp
public BankAccount(string name, decimal initialBalance)
```

El compilador no genera un constructor predeterminado al definir un constructor. Esto significa que cada clase derivada debe llamar explícitamente a este constructor. Se declara un constructor que puede pasar argumentos al constructor de la clase base.  En el código siguiente se muestra el constructor de `InterestEarningAccount`:

:::code language="csharp" source="./snippets/object-oriented-programming/InterestEarningAccount.cs" ID="DerivedConstructor":::

Los parámetros de este nuevo constructor coinciden con el tipo de parámetro y los nombres del constructor de clase base. Utilice la sintaxis de `: base()` para indicar una llamada a un constructor de clase base. Algunas clases definen varios constructores, y esta sintaxis le permite elegir el constructor de clase base al que llama. Una vez que haya actualizado los constructores, puede desarrollar el código para cada una de las clases derivadas. Los requisitos para las clases nuevas se pueden indicar de la siguiente manera:

- Una cuenta que devenga intereses:
  - obtendrá un crédito del 2 % del saldo a final de mes.
- Una línea de crédito:
  - puede tener un saldo negativo, pero no mayor en valor absoluto que el límite de crédito.
  - Generará un cargo por intereses cada mes en el que el saldo final del mes no sea 0.
  - Generará un cargo por cada retirada que supere el límite de crédito.
- Una cuenta de tarjeta regalo:
  - Se puede recargar con una cantidad especificada una vez al mes, el último día del mes.

Puede ver que los tres tipos de cuenta tienen una acción que tiene lugar al final de cada mes. Sin embargo, cada tipo de cuenta realiza diferentes tareas. Utiliza el *polimorfismo* para implementar este código. Cree un método `virtual` único en la clase `BankAccount`:

:::code language="csharp" source="./snippets/object-oriented-programming/BankAccount.cs" ID="DeclareMonthEndTransactions":::

El código anterior muestra cómo se usa la palabra clave `virtual` para declarar un método en la clase base para el que una clase derivada puede proporcionar una implementación diferente. Un método `virtual` es un método en el que cualquier clase derivada puede optar por volver a implementar. Las clases derivadas usan la palabra clave `override` para definir la nueva implementación. Normalmente, se hace referencia a este proceso como "reemplazar la implementación de la clase base". La palabra clave `virtual` especifica que las clases derivadas pueden invalidar el comportamiento. También puede declarar métodos `abstract` en los que las clases derivadas deben reemplazar el comportamiento. La clase base no proporciona una implementación para un método `abstract`. A continuación, debe definir la implementación de dos de las nuevas clases que ha creado. Empiece por `InterestEarningAccount`:

:::code language="csharp" source="./snippets/object-oriented-programming/InterestEarningAccount.cs" ID="ApplyMonthendInterest":::

Agregue el código siguiente a `LineOfCreditAccount`. El código niega el saldo para calcular un cargo de interés positivo que se retira de la cuenta:

:::code language="csharp" source="./snippets/object-oriented-programming/LineOfCreditAccount.cs" ID="ApplyMonthendInterest":::

La clase `GiftCardAccount` necesita dos cambios para implementar su funcionalidad de fin de mes. En primer lugar, modifique el constructor para incluir una cantidad opcional para agregar cada mes:

:::code language="csharp" source="./snippets/object-oriented-programming/GiftCardAccount.cs" ID="GiftCardAccountConstruction":::

El constructor proporciona un valor predeterminado para el valor `monthlyDeposit`, por lo que los llamadores pueden omitir `0` para ningún ingreso mensual. A continuación, invalide el método `PerformMonthEndTransactions` para agregar el depósito mensual, si se estableció en un valor distinto de cero en el constructor:

:::code language="csharp" source="./snippets/object-oriented-programming/GiftCardAccount.cs" ID="AddMonthlyDeposit":::

La invalidación aplica el conjunto de depósitos mensual en el constructor. Agregue el código siguiente al método `Main` para probar estos cambios en `GiftCardAccount` y en `InterestEarningAccount`:

:::code language="csharp" source="./snippets/object-oriented-programming/Program.cs" ID="FirstTests":::

Verifique los resultados. Ahora, agregue un conjunto similar de código de prueba para `LineOfCreditAccount`:

:::code language="csharp" source="./snippets/object-oriented-programming/Program.cs" ID="TestLineOfCredit":::

Al agregar el código anterior y ejecutar el programa, verá algo parecido al siguiente error:

```console
Unhandled exception. System.ArgumentOutOfRangeException: Amount of deposit must be positive (Parameter 'amount')
   at OOProgramming.BankAccount.MakeDeposit(Decimal amount, DateTime date, String note) in BankAccount.cs:line 42
   at OOProgramming.BankAccount..ctor(String name, Decimal initialBalance) in BankAccount.cs:line 31
   at OOProgramming.LineOfCreditAccount..ctor(String name, Decimal initialBalance) in LineOfCreditAccount.cs:line 9
   at OOProgramming.Program.Main(String[] args) in Program.cs:line 29
```

> [!NOTE]
> La salida real incluye la ruta de acceso completa a la carpeta con el proyecto. Los nombres de carpeta se omitieron para ser más breves. Además, dependiendo del formato del código, los números de línea pueden ser ligeramente diferentes.

Este código produce un error porque `BankAccount` supone que el saldo inicial debe ser mayor que 0. Otra suposición incorporada en la clase `BankAccount` es que el saldo no puede entrar en cifras negativas. Lo que sucede que es se rechazan las retiradas que provocan un descubierto en la cuenta. Ambas suposiciones deben cambiar. La línea de la cuenta de crédito comienza en 0, y generalmente tendrá un saldo negativo. Además, si un cliente retira demasiado dinero, generará un cargo. La transacción se acepta, solo que cuesta más. La primera regla se puede implementar agregando un argumento opcional al constructor `BankAccount` que especifica el saldo mínimo. El valor predeterminado es `0`. La segunda regla requiere un mecanismo que permita que las clases derivadas modifiquen el algoritmo predeterminado. En cierto sentido, la clase base "pregunta" al tipo derivado qué debe ocurrir cuando hay un descubierto. El comportamiento predeterminado es rechazar la transacción generando una excepción.

Comencemos agregando un segundo constructor que incluya un parámetro `minimumBalance` opcional. Este nuevo constructor se ocupa de todas las acciones que realiza el constructor existente. Además, establece la propiedad del saldo mínimo. Podría copiar el cuerpo del constructor existente. Sin embargo, esto implica que dos ubicaciones cambiarán en el futuro. Lo que puede hacer es usar un *encadenamiento de constructores* para que un constructor llame a otro. En el código siguiente se muestran los dos constructores y el nuevo campo adicional:

 :::code language="csharp" source="./snippets/object-oriented-programming/BankAccount.cs" ID="ConstructorModifications":::

En el código anterior se muestran dos técnicas nuevas. En primer lugar, el campo `minimumBalance` está marcado como `readonly`. Esto significa que el valor no se puede cambiar después de que se construya el objeto. Una vez que se crea `BankAccount`, `minimumBalance` no puede cambiar. En segundo lugar, el constructor que toma dos parámetros utiliza `: this(name, initialBalance, 0) { }` como su implementación. La expresión `: this()` llama al otro constructor, el que tiene tres parámetros. Esta técnica permite tener una única implementación para inicializar un objeto, aunque el código de cliente puede elegir uno de muchos constructores.

Esta implementación solo llama a `MakeDeposit` si el saldo inicial es mayor que `0`. Esto conserva la regla de que los depósitos deben ser positivos, pero permite que la cuenta de crédito se abra con un saldo de `0`.

Ahora que la clase `BankAccount` tiene un campo de solo lectura para el saldo mínimo, el último cambio es modificar la codificación rígida `0` a `minimumBalance` en el método `MakeWithdrawal`:

```csharp
if (Balance - amount < minimumBalance)
```

Después de extender la clase `BankAccount`, puede modificar el constructor `LineOfCreditAccount` para llamar al nuevo constructor base, como se muestra en el código siguiente:

:::code language="csharp" source="./snippets/object-oriented-programming/LineOfCreditAccount.cs" ID="ConstructLineOfCredit":::

Observe que el constructor `LineOfCreditAccount` cambia el signo del parámetro `creditLimit` para que coincida con el significado del parámetro `minimumBalance`.

## <a name="different-overdraft-rules"></a>Diferentes reglas de descubierto

La última característica que se va a agregar permite a `LineOfCreditAccount` cobrar una cuota por sobrepasar el límite de crédito en lugar de rechazar la transacción.

Una técnica consiste en definir una función virtual en la que se implemente el comportamiento requerido. La clase `BankAccount` refactoriza el método `MakeWithdrawal` en dos métodos. El nuevo método realiza la acción especificada cuando la retirada toma el saldo por debajo del mínimo. El método `MakeWithdrawal` existente tiene el siguiente código:

```csharp
public void MakeWithdrawal(decimal amount, DateTime date, string note)
{
    if (amount <= 0)
    {
        throw new ArgumentOutOfRangeException(nameof(amount), "Amount of withdrawal must be positive");
    }
    if (Balance - amount < minimumBalance)
    {
        throw new InvalidOperationException("Not sufficient funds for this withdrawal");
    }
    var withdrawal = new Transaction(-amount, date, note);
    allTransactions.Add(withdrawal);
}
```

Reemplácelo por el código siguiente:

:::code language="csharp" source="./snippets/object-oriented-programming/BankAccount.cs" ID="RefactoredMakeWithdrawal":::

El método agregado es `protected`, lo que significa que solo se puede llamar desde clases derivadas. Esa declaración impide que otros clientes llamen al método. También es `virtual` para que las clases derivadas puedan cambiar el comportamiento. El tipo de valor devuelto es `Transaction?`. La anotación `?` indica que el método puede devolver `null`. Agregue la siguiente implementación en `LineOfCreditAccount` para cobrar una cuota cuando se supere el límite de retirada:

:::code language="csharp" source="./snippets/object-oriented-programming/LineOfCreditAccount.cs" ID="AddOverdraftFee":::

El reemplazo devuelve una transacción de cuota cuando en la cuenta se produce un descubierto. Si la retirada no supera el límite, el método devuelve una transacción `null`. Esto indica que no hay ninguna cuota. Pruebe estos cambios agregando el código siguiente al método `Main` en la clase `Program`:

:::code language="csharp" source="./snippets/object-oriented-programming/Program.cs" ID="TestLineOfCredit":::

Ejecute el programa y compruebe los resultados.

## <a name="summary"></a>Resumen

En este tutorial se han mostrado muchas de las técnicas que se usan en la programación orientada a objetos:

- Usó la *abstracción* cuando mantenía muchos detalles `private` en cada clase.
- Usó la *encapsulación* cuando definió clases para cada uno de los distintos tipos de cuenta. Esas clases describían el comportamiento de ese tipo de cuenta.
- Usó la *herencia* cuando aprovechó la implementación ya creada en la clase `BankAccount` para guardar el código.
- Usó el *polimorfismo* cuando creó métodos `virtual` que las clases derivadas podrían reemplazar para crear un comportamiento específico para ese tipo de cuenta.

Enhorabuena, ha completado todos nuestros tutoriales de introducción a C#. Para obtener más información, continúe con más [tutoriales](../index.md).
