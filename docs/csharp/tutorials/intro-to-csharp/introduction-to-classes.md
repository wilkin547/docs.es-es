---
title: 'Clases y objetos: tutorial de introducción a C#'
description: Creación del primer programa con C# y análisis de los conceptos orientados a objetos
ms.date: 10/11/2017
ms.custom: mvc
ms.openlocfilehash: 57394ecb02745d69e22f4d9f1dbd4213f290cd5a
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609055"
---
# <a name="explore-object-oriented-programming-with-classes-and-objects"></a>Exploración de la programación orientada a objetos con clases y objetos

En este tutorial se supone que cuenta con una máquina que puede usar para el desarrollo. El tutorial de .NET [Hola mundo en 10 minutos](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) cuenta con instrucciones para configurar el entorno de desarrollo local en Windows, Linux o macOS. En [Become familiar with the development tools](local-environment.md) (Familiarizarse con las herramientas de desarrollo) puede obtener información general sobre los comandos que usará, donde hay vínculos que amplían la información.

## <a name="create-your-application"></a>Creación de una aplicación

En una ventana de terminal, cree un directorio denominado *clases*. Creará la aplicación ahí. Cambie a ese directorio y escriba `dotnet new console` en la ventana de la consola. Este comando crea la aplicación. Abra *Program.cs*. El resultado debería tener un aspecto similar a este:

```csharp
using System;

namespace classes
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

En este tutorial, se van a crear tipos nuevos que representan una cuenta bancaria. Normalmente los desarrolladores definen cada clase en un archivo de texto diferente. De esta forma, la tarea de administración resulta más sencilla a medida que aumenta el tamaño del programa. Cree un archivo denominado *CuentaBancaria.cs* en el directorio *clases*.

Este archivo contendrá la definición de una ***cuenta bancaria***. La programación orientada a objetos organiza el código mediante la creación de tipos en forma de ***clases***. Estas clases contienen el código que representa una entidad específica. La clase `BankAccount` representa una cuenta bancaria. El código implementa operaciones específicas a través de métodos y propiedades. En este tutorial, la cuenta bancaria admite el siguiente comportamiento:

1. Tiene un número de diez dígitos que identifica la cuenta bancaria de forma única.
1. Tiene una cadena que almacena el nombre o los nombres de los propietarios.
1. Se puede consultar el saldo.
1. Acepta depósitos.
1. Acepta reintegros.
1. El saldo inicial debe ser positivo.
1. Los reintegros no pueden resultar en un saldo negativo.

## <a name="define-the-bank-account-type"></a>Definición del tipo de cuenta bancaria

Puede empezar por crear los datos básicos de una clase que define dicho comportamiento. Cree un archivo con el comando **File:New**. Asígnele el nombre *BankAccount.cs*. Agregue el código siguiente al archivo *BankAccount.cs*:

```csharp
using System;

namespace classes
{
    public class BankAccount
    {
        public string Number { get; }
        public string Owner { get; set; }
        public decimal Balance { get; }

        public void MakeDeposit(decimal amount, DateTime date, string note)
        {
        }

        public void MakeWithdrawal(decimal amount, DateTime date, string note)
        {
        }
    }
}
```

Antes de avanzar, se va a dar un repaso a lo que ha compilado.  La declaración `namespace` permite organizar el código de forma lógica. Este tutorial es relativamente pequeño, por lo que deberá colocar todo el código en un espacio de nombres.

`public class BankAccount` define la clase o el tipo que va a crear. Todo lo que se encuentra entre `{` y `}` después de la declaración de clase define el estado y el comportamiento de la clase. Hay cinco ***miembros*** de la clase `BankAccount`. Los tres primeros son ***propiedades***. Las propiedades son elementos de datos que pueden contener código que exige la validación u otras reglas. Los dos últimos son ***métodos***. Los métodos son bloques de código que realizan una única función. La lectura de los nombres de cada miembro debe proporcionar suficiente información tanto al usuario como a otro desarrollador para entender cuál es la función de la clase.

## <a name="open-a-new-account"></a>Apertura de una cuenta nueva

La primera característica que se va a implementar es la apertura de una cuenta bancaria. Cuando un cliente abre una cuenta, debe proporcionar un saldo inicial y la información sobre el propietario o los propietarios de esa cuenta.

La creación de un objeto del tipo `BankAccount` conlleva definir un ***constructor*** que asigne dichos valores. Un ***constructor*** es un miembro que tiene el mismo nombre que la clase. Se utiliza para inicializar los objetos de ese tipo de clase. Agregue el siguiente constructor al tipo `BankAccount`. Coloque el siguiente código encima de la declaración de `MakeDeposit`.

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

A los constructores se les llama cuando se crea un objeto mediante [`new`](../../language-reference/operators/new-operator.md). Reemplace la línea `Console.WriteLine("Hello World!");` de *Program.cs* por la siguiente línea (reemplace `<name>` por su nombre):

```csharp
var account = new BankAccount("<name>", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

Vamos a ejecutar lo que se ha creado hasta ahora. Si usa Visual Studio, seleccione **Iniciar sin depurar** en el menú **Ejecutar**. Si va a usar una línea de comandos, escriba `dotnet run` en el directorio en el que ha creado el proyecto.

¿Ha observado que el número de cuenta está en blanco? Es el momento de solucionarlo. El número de cuenta debe asignarse cuando se construye el objeto. Sin embargo, el autor de la llamada no es el responsable de crearlo. El código de la clase `BankAccount` debe saber cómo asignar nuevos números de cuenta.  Una manera sencilla de hacerlo es empezar con un número de diez dígitos. Increméntelo cuando cree cada cuenta. Por último, almacene el número de cuenta actual cuando se construya un objeto.

Agregue una declaración de miembro a la clase `BankAccount`. Coloque la siguiente línea de código después de la llave de apertura `{` al principio de la clase `BankAccount`:

```csharp
private static int accountNumberSeed = 1234567890;
```

Se trata de un miembro de datos. Tiene el estado `private`, lo que significa que solo se puede acceder a él con el código incluido en la clase `BankAccount`. Es una forma de separar las responsabilidades públicas (como tener un número de cuenta) de la implementación privada (cómo se generan los números de cuenta). También es `static`, lo que significa que se comparte entre todos los objetos `BankAccount`. El valor de una variable no estática es único para cada instancia del objeto `BankAccount`. Agregue las dos líneas siguientes al constructor para asignar el número de cuenta: Colóquelas después de la línea donde pone `this.Balance = initialBalance`:

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

Escriba `dotnet run` para ver los resultados.

## <a name="create-deposits-and-withdrawals"></a>Creación de depósitos y reintegros

La clase de la cuenta bancaria debe aceptar depósitos y reintegros para que el funcionamiento sea adecuado. Se van a implementar depósitos y reintegros con la creación de un diario de cada transacción de la cuenta. Ofrece algunas ventajas con respecto al mero hecho de actualizar el saldo en cada transacción. El historial se puede utilizar para auditar todas las transacciones y administrar los saldos diarios. Con el cálculo del saldo a partir del historial de todas las transacciones, cuando proceda, todos los errores de una única transacción que se solucionen se reflejarán correctamente en el saldo cuando se realice el siguiente cálculo.

Se va a empezar por crear un tipo para representar una transacción. Se trata de un tipo simple que no tiene ninguna responsabilidad. Necesita algunas propiedades. Cree un archivo denominado *Transaction.cs*. Agregue el código siguiente a él:

:::code language="csharp" source="./snippets/introduction-to-classes/Transaction.cs":::

Ahora se va a agregar <xref:System.Collections.Generic.List%601> de objetos `Transaction` a la clase `BankAccount`. Agregue la siguiente declaración después del constructor en el archivo *BankAccount.cs*:

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="TransactionDeclaration":::

La clase <xref:System.Collections.Generic.List%601> requiere la importación de un espacio de nombres diferente. Agregue lo siguiente al principio de *CuentaBancaria.cs*:

```csharp
using System.Collections.Generic;
```

Ahora se va a cambiar la forma en que se notifica `Balance`.  Esto se puede conseguir con la suma de los valores de todas las transacciones. Modifique la declaración de `Balance` en la clase `BankAccount` por lo siguiente:

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="BalanceComputation":::

En este ejemplo se muestra un aspecto importante de las ***propiedades***. Ahora va a calcular el saldo cuando otro programador solicite el valor. El cálculo enumera todas las transacciones y proporciona la suma como el saldo actual.

Después, implemente los métodos `MakeDeposit` y `MakeWithdrawal`. Estos métodos exigirán las dos reglas finales: el saldo inicial debe ser positivo y ningún reintegro debe generar un saldo negativo.

Esta operación introduce el concepto de las ***excepciones***. La forma habitual de indicar que un método no puede completar su trabajo correctamente consiste en generar una excepción. El tipo de excepción y el mensaje asociado a ella describen el error. En este caso, el método `MakeDeposit` genera una excepción si el importe del depósito es negativo. El método `MakeWithdrawal` genera una excepción si la cantidad retirada es negativa o si la aplicación del reintegro tiene como resultado un saldo negativo: Agregue el código siguiente después de la declaración de la lista `allTransactions`:

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="DepositAndWithdrawal":::

La instrucción [`throw`](../../language-reference/keywords/throw.md)**genera** una excepción. La ejecución del bloque actual finaliza y el control se transfiere al primer bloque `catch` coincidente que se encuentra en la pila de llamadas. Se agregará un bloque `catch` para probar este código un poco más adelante.

El constructor debe obtener un cambio para que agregue una transacción inicial, en lugar de actualizar el saldo directamente. Puesto que ya escribió el método `MakeDeposit`, llámelo desde el constructor. El constructor terminado debe tener este aspecto:

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="Constructor":::

<xref:System.DateTime.Now?displayProperty=nameWithType> es una propiedad que devuelve la fecha y hora actuales. Para probar esto, agregue algunos depósitos y reintegros en el método `Main`, a continuación del código que crea un elemento `BankAccount`:

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "Friend paid me back");
Console.WriteLine(account.Balance);
```

Después, compruebe si detecta las condiciones de error al tratar de crear una cuenta con un saldo negativo. Agregue el código siguiente después del código anterior que acaba de agregar:

```csharp
// Test that the initial balances must be positive.
try
{
    var invalidAccount = new BankAccount("invalid", -55);
}
catch (ArgumentOutOfRangeException e)
{
    Console.WriteLine("Exception caught creating account with negative balance");
    Console.WriteLine(e.ToString());
}
```

Use las [instrucciones `try` y `catch`](../../language-reference/keywords/try-catch.md) para marcar un bloque de código que puede generar excepciones y para detectar los errores que se esperan. Puede usar la misma técnica para probar el código que genera una excepción para un saldo negativo. Agregue el código siguiente al final del método `Main`:

```csharp
// Test for a negative balance.
try
{
    account.MakeWithdrawal(750, DateTime.Now, "Attempt to overdraw");
}
catch (InvalidOperationException e)
{
    Console.WriteLine("Exception caught trying to overdraw");
    Console.WriteLine(e.ToString());
}
```

Guarde el archivo y escriba `dotnet run` para probarlo.

## <a name="challenge---log-all-transactions"></a>Desafío: registro de todas las transacciones

Para finalizar este tutorial, puede escribir el método `GetAccountHistory` que crea `string` para el historial de transacciones. Agregue este método al tipo `BankAccount`:

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="History":::

Usa la clase <xref:System.Text.StringBuilder> para dar formato a una cadena que contiene una línea para cada transacción. Se ha visto anteriormente en estos tutoriales el código utilizado para dar formato a una cadena. Un carácter nuevo es `\t`. Inserta una pestaña para dar formato a la salida.

Agregue esta línea para probarla en *Program.cs*:

```csharp
Console.WriteLine(account.GetAccountHistory());
```

Ejecute el programa para ver los resultados.

## <a name="next-steps"></a>Pasos siguientes

Si se ha quedado bloqueado, puede consultar el origen de este tutorial [en el repositorio de GitHub](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/classes-quickstart/).

Puede continuar con el tutorial de la [programación orientada a objetos](object-oriented-programming.md).

Puede aprender más sobre estos conceptos en los artículos siguientes:

- [Instrucciones If y else](../../language-reference/keywords/if-else.md)
- [Instrucción while](../../language-reference/keywords/while.md)
- [Instrucción do](../../language-reference/keywords/do.md)
- [Instrucción for](../../language-reference/keywords/for.md)
