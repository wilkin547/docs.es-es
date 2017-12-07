---
title: "Inicios rápidos: introducción a las clases (Guía de C#)"
description: "Creación del primer programa con C# y análisis de los conceptos orientados a objetos"
author: billwagner
ms.author: wiwagn
ms.date: 10/11/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: ad6e83d427b55482f9615e0083682bdca6c56704
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="introduction-to-classes"></a><span data-ttu-id="160f2-103">Introducción a las clases</span><span class="sxs-lookup"><span data-stu-id="160f2-103">Introduction to classes</span></span>

<span data-ttu-id="160f2-104">En esta lección se asume que ha instalado el [SDK de .NET Core](http://dot.net/core) y un editor de su elección.</span><span class="sxs-lookup"><span data-stu-id="160f2-104">This lesson assumes that you've installed [.NET Core SDK](http://dot.net/core), and an editor of your choice.</span></span> <span data-ttu-id="160f2-105">De lo contrario, pruebe [Visual Studio Code](https://code.visualstudio.com/) o [Visual Studio](https://www.visualstudio.com/) en Mac o Windows.</span><span class="sxs-lookup"><span data-stu-id="160f2-105">If you don't have one, try [Visual Studio Code](https://code.visualstudio.com/), or [Visual Studio](https://www.visualstudio.com/) on Mac or Windows.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="160f2-106">Creación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="160f2-106">Create your application</span></span>

<span data-ttu-id="160f2-107">En una ventana de terminal, cree un directorio denominado **clases**.</span><span class="sxs-lookup"><span data-stu-id="160f2-107">Using a terminal window, create a directory named **classes**.</span></span> <span data-ttu-id="160f2-108">Creará la aplicación ahí.</span><span class="sxs-lookup"><span data-stu-id="160f2-108">You'll build your application there.</span></span> <span data-ttu-id="160f2-109">Cambie a ese directorio y escriba `dotnet new console` en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="160f2-109">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="160f2-110">Este comando crea la aplicación.</span><span class="sxs-lookup"><span data-stu-id="160f2-110">This command creates your application.</span></span> <span data-ttu-id="160f2-111">Abra **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="160f2-111">Open **Program.cs**.</span></span> <span data-ttu-id="160f2-112">El resultado debería tener un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="160f2-112">It should look like this:</span></span>

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

<span data-ttu-id="160f2-113">En este inicio rápido, se van a crear tipos nuevos que representan una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="160f2-113">In this quick start, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="160f2-114">Normalmente los desarrolladores definen cada clase en un archivo de texto diferente.</span><span class="sxs-lookup"><span data-stu-id="160f2-114">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="160f2-115">De esta forma, la tarea de administración resulta más sencilla a medida que aumenta el tamaño del programa.</span><span class="sxs-lookup"><span data-stu-id="160f2-115">That makes it easier to manage as a program grows in size.</span></span>  <span data-ttu-id="160f2-116">Cree un archivo denominado **CuentaBancaria.cs** en el directorio **clases**.</span><span class="sxs-lookup"><span data-stu-id="160f2-116">Create a new file named **BankAccount.cs** in the **classes** directory.</span></span> 

<span data-ttu-id="160f2-117">Este archivo contendrá la definición de un ***cuenta bancaria***.</span><span class="sxs-lookup"><span data-stu-id="160f2-117">This file will contain the deefinition of a ***bank account***.</span></span> <span data-ttu-id="160f2-118">La programación orientada a objetos organiza el código mediante la creación de tipos en forma de ***clases***.</span><span class="sxs-lookup"><span data-stu-id="160f2-118">Object Oriented programming organizes code by creating types in the form of ***classes***.</span></span> <span data-ttu-id="160f2-119">Estas clases contienen el código que representa una entidad específica.</span><span class="sxs-lookup"><span data-stu-id="160f2-119">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="160f2-120">La clase `BankAccount` representa una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="160f2-120">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="160f2-121">El código implementa operaciones específicas a través de métodos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="160f2-121">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="160f2-122">En este inicio rápido, la cuenta bancaria admite el siguiente comportamiento:</span><span class="sxs-lookup"><span data-stu-id="160f2-122">In this quick start, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="160f2-123">Tiene un número de diez dígitos que identifica la cuenta bancaria de forma única.</span><span class="sxs-lookup"><span data-stu-id="160f2-123">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="160f2-124">Tiene una cadena que almacena el nombre o los nombres de los propietarios.</span><span class="sxs-lookup"><span data-stu-id="160f2-124">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="160f2-125">Se puede consultar el saldo.</span><span class="sxs-lookup"><span data-stu-id="160f2-125">The balance can be retrieved.</span></span>
1. <span data-ttu-id="160f2-126">Acepta depósitos.</span><span class="sxs-lookup"><span data-stu-id="160f2-126">It accepts deposits.</span></span>
1. <span data-ttu-id="160f2-127">Acepta reintegros.</span><span class="sxs-lookup"><span data-stu-id="160f2-127">It accepts withdrawals.</span></span>
1. <span data-ttu-id="160f2-128">El saldo inicial debe ser positivo.</span><span class="sxs-lookup"><span data-stu-id="160f2-128">The initial balance must be positive.</span></span>
1. <span data-ttu-id="160f2-129">Los reintegros no pueden resultar en un saldo negativo.</span><span class="sxs-lookup"><span data-stu-id="160f2-129">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="160f2-130">Definición del tipo de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="160f2-130">Define the bank account type</span></span>

<span data-ttu-id="160f2-131">Puede empezar por crear los datos básicos de una clase que define dicho comportamiento.</span><span class="sxs-lookup"><span data-stu-id="160f2-131">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="160f2-132">El resultado debería tener un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="160f2-132">It would look like this:</span></span>

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

        public void MakeWithdrawal(decimal amount, DateTime date, string payee, string note)
        {
        }
    }
}
```

<span data-ttu-id="160f2-133">Antes de avanzar, se va a dar un repaso a lo que ha compilado.</span><span class="sxs-lookup"><span data-stu-id="160f2-133">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="160f2-134">La declaración `namespace` permite organizar el código de forma lógica.</span><span class="sxs-lookup"><span data-stu-id="160f2-134">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="160f2-135">Este inicio rápido es relativamente pequeño, por lo que deberá colocar todo el código en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="160f2-135">This quick start is relatively small, so you'll put all the code in one namespace.</span></span> 

<span data-ttu-id="160f2-136">`public class BankAccount` define la clase o el tipo que va a crear.</span><span class="sxs-lookup"><span data-stu-id="160f2-136">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="160f2-137">Todo lo que se encuentra entre `{` y `}` después de la declaración de clase define el comportamiento de la clase.</span><span class="sxs-lookup"><span data-stu-id="160f2-137">Everything inside the `{` and `}` that follows the class declaration defines the behavior of the class.</span></span> <span data-ttu-id="160f2-138">Hay cinco ***miembros*** de la clase `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="160f2-138">There are five ***members*** of the `BankAccount` class.</span></span> <span data-ttu-id="160f2-139">Los tres primeros son ***propiedades***.</span><span class="sxs-lookup"><span data-stu-id="160f2-139">The first three are ***properties***.</span></span> <span data-ttu-id="160f2-140">Las propiedades son elementos de datos que pueden contener código que exige la validación u otras reglas.</span><span class="sxs-lookup"><span data-stu-id="160f2-140">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="160f2-141">Los dos últimos son ***métodos***.</span><span class="sxs-lookup"><span data-stu-id="160f2-141">The last two are ***methods***.</span></span> <span data-ttu-id="160f2-142">Los métodos son bloques de código que realizan una única función.</span><span class="sxs-lookup"><span data-stu-id="160f2-142">Methods are blocks of code that peform a single function.</span></span> <span data-ttu-id="160f2-143">La lectura de los nombres de cada miembro debe proporcionar suficiente información tanto al usuario como a otro desarrollador para entender cuál es la función de la clase.</span><span class="sxs-lookup"><span data-stu-id="160f2-143">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="160f2-144">Apertura de una cuenta nueva</span><span class="sxs-lookup"><span data-stu-id="160f2-144">Open a new account</span></span>

<span data-ttu-id="160f2-145">La primera característica que se va a implementar es la apertura de una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="160f2-145">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="160f2-146">Cuando un cliente abre una cuenta, debe proporcionar un saldo inicial y la información sobre el propietario o los propietarios de esa cuenta.</span><span class="sxs-lookup"><span data-stu-id="160f2-146">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span> 

<span data-ttu-id="160f2-147">La creación de un objeto del tipo `BankAccount` conlleva definir un ***constructor*** que asigne dichos valores.</span><span class="sxs-lookup"><span data-stu-id="160f2-147">Creating a new object of the `BankAccount` type means defining a ***constructor*** that assigns those values.</span></span> <span data-ttu-id="160f2-148">Un ***constructor*** es un miembro que tiene el mismo nombre que la clase.</span><span class="sxs-lookup"><span data-stu-id="160f2-148">A ***constructor*** is a member that has the same name as the class.</span></span> <span data-ttu-id="160f2-149">Se utiliza para inicializar los objetos de ese tipo de clase.</span><span class="sxs-lookup"><span data-stu-id="160f2-149">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="160f2-150">Agregue el siguiente constructor al tipo `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="160f2-150">Add the following constructor to the `BankAccount` type:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="160f2-151">A los constructores se les llama cuando se crea un objeto mediante [`new`](../language-reference/keywords/new.md).</span><span class="sxs-lookup"><span data-stu-id="160f2-151">Constructors are called when you create an object using [`new`](../language-reference/keywords/new.md).</span></span> <span data-ttu-id="160f2-152">Reemplace la línea `Console.WriteLine("Hello World!");` de ***program.cs*** con la siguiente línea (reemplace `<name>` con su nombre):</span><span class="sxs-lookup"><span data-stu-id="160f2-152">Replace the line `Console.WriteLine("Hello World!");` in ***program.cs*** with the following line (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="160f2-153">Escriba `dotnet run` para ver lo que sucede.</span><span class="sxs-lookup"><span data-stu-id="160f2-153">Type `dotnet run` to see what happens.</span></span>  

<span data-ttu-id="160f2-154">¿Ha observado que el número de cuenta está en blanco?</span><span class="sxs-lookup"><span data-stu-id="160f2-154">Did you notice that the account number is blank?</span></span> <span data-ttu-id="160f2-155">Es el momento de solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="160f2-155">It's time to fix that.</span></span> <span data-ttu-id="160f2-156">El número de cuenta debe asignarse cuando se construye el objeto.</span><span class="sxs-lookup"><span data-stu-id="160f2-156">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="160f2-157">Sin embargo, el autor de la llamada no es el responsable de crearlo.</span><span class="sxs-lookup"><span data-stu-id="160f2-157">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="160f2-158">El código de la clase `BankAccount` debe saber cómo asignar nuevos números de cuenta.</span><span class="sxs-lookup"><span data-stu-id="160f2-158">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="160f2-159">Una manera sencilla de hacerlo es empezar con un número de diez dígitos.</span><span class="sxs-lookup"><span data-stu-id="160f2-159">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="160f2-160">Increméntelo cuando cree cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="160f2-160">Increment it when each new account is created.</span></span> <span data-ttu-id="160f2-161">Por último, almacene el número de cuenta actual cuando se construya un objeto.</span><span class="sxs-lookup"><span data-stu-id="160f2-161">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="160f2-162">Agregue la siguiente declaración de miembro a la clase `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="160f2-162">Add the following member declaration to the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="160f2-163">Se trata de un miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="160f2-163">This is a data member.</span></span> <span data-ttu-id="160f2-164">Tiene el estado `private`, lo que significa que solo se puede acceder a él con el código incluido en la clase `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="160f2-164">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="160f2-165">Es una forma de separar las responsabilidades públicas (como tener un número de cuenta) de la implementación privada (cómo se generan los números de cuenta). Agregue las dos líneas siguientes al constructor para asignar el número de cuenta:</span><span class="sxs-lookup"><span data-stu-id="160f2-165">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated.) Add the following two lines to the constructor to assign the account number:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="160f2-166">Escriba `dotnet run` para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="160f2-166">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="160f2-167">Creación de depósitos y reintegros</span><span class="sxs-lookup"><span data-stu-id="160f2-167">Create deposits and withdrawals</span></span>

<span data-ttu-id="160f2-168">La clase de la cuenta bancaria debe aceptar depósitos y reintegros para que el funcionamiento sea adecuado.</span><span class="sxs-lookup"><span data-stu-id="160f2-168">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="160f2-169">Se van a implementar depósitos y reintegros con la creación de un diario de cada transacción de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="160f2-169">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="160f2-170">Ofrece algunas ventajas con respecto al mero hecho de actualizar el saldo en cada transacción.</span><span class="sxs-lookup"><span data-stu-id="160f2-170">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="160f2-171">El historial se puede utilizar para auditar todas las transacciones y administrar los saldos diarios.</span><span class="sxs-lookup"><span data-stu-id="160f2-171">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="160f2-172">Con el cálculo del saldo a partir del historial de todas las transacciones, cuando proceda, todos los errores de una única transacción que se solucionen se reflejarán correctamente en el saldo cuando se realice el siguiente cálculo.</span><span class="sxs-lookup"><span data-stu-id="160f2-172">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="160f2-173">Se va a empezar por crear un tipo para representar una transacción.</span><span class="sxs-lookup"><span data-stu-id="160f2-173">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="160f2-174">Se trata de un tipo simple que no tiene ninguna responsabilidad.</span><span class="sxs-lookup"><span data-stu-id="160f2-174">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="160f2-175">Necesita algunas propiedades.</span><span class="sxs-lookup"><span data-stu-id="160f2-175">It needs a few properties.</span></span> <span data-ttu-id="160f2-176">Cree un archivo denominado ***Transaction.cs***.</span><span class="sxs-lookup"><span data-stu-id="160f2-176">Create a new file named ***Transaction.cs***.</span></span> <span data-ttu-id="160f2-177">Agregue el código siguiente a él:</span><span class="sxs-lookup"><span data-stu-id="160f2-177">Add the following code to it:</span></span>

[!code-csharp[Transaction](../../../samples/csharp/classes-quickstart/Transaction.cs "Transaction declaration")]

<span data-ttu-id="160f2-178">Ahora se va a agregar <xref:System.Collections.Generic.List%601> de objetos `Transaction` a la clase `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="160f2-178">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="160f2-179">Agregue la declaración siguiente:</span><span class="sxs-lookup"><span data-stu-id="160f2-179">Add the following declaration:</span></span>

[!code-csharp[TransactionDecl](../../../samples/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration "Transaction declaration")]

<span data-ttu-id="160f2-180">La clase <xref:System.Collections.Generic.List%601> requiere la importación de un espacio de nombres diferente.</span><span class="sxs-lookup"><span data-stu-id="160f2-180">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="160f2-181">Agregue lo siguiente al principio de **CuentaBancaria.cs**:</span><span class="sxs-lookup"><span data-stu-id="160f2-181">Add the following at the beginning of **BankAccount.cs**:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="160f2-182">Ahora se va a cambiar la forma en que se notifica `Balance`.</span><span class="sxs-lookup"><span data-stu-id="160f2-182">Now, let's change how the `Balance` is reported.</span></span>  <span data-ttu-id="160f2-183">Esto se puede conseguir con la suma de los valores de todas las transacciones.</span><span class="sxs-lookup"><span data-stu-id="160f2-183">It can be found by summing the values of all transactions.</span></span> <span data-ttu-id="160f2-184">Modifique la declaración de `Balance` en la clase `BankAccount` por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="160f2-184">Modify the declaration of `Balance` in the `BankAccount` class to the following:</span></span>

[!code-csharp[BalanceComputation](../../../samples/csharp/classes-quickstart/BankAccount.cs#BalanceComputation "Computing the balance")]

<span data-ttu-id="160f2-185">En este ejemplo se muestra un aspecto importante de las ***propiedades***.</span><span class="sxs-lookup"><span data-stu-id="160f2-185">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="160f2-186">Ahora va a calcular el saldo cuando otro programador solicite el valor.</span><span class="sxs-lookup"><span data-stu-id="160f2-186">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="160f2-187">El cálculo enumera todas las transacciones y proporciona la suma como el saldo actual.</span><span class="sxs-lookup"><span data-stu-id="160f2-187">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="160f2-188">Después, implemente los métodos `MakeDeposit` y `MakeWithdrawal`.</span><span class="sxs-lookup"><span data-stu-id="160f2-188">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="160f2-189">Estos métodos exigirán las dos reglas finales: el saldo inicial debe ser positivo y ningún reintegro debe generar un saldo negativo.</span><span class="sxs-lookup"><span data-stu-id="160f2-189">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span> 

<span data-ttu-id="160f2-190">Esta operación introduce el concepto de las ***excepciones***.</span><span class="sxs-lookup"><span data-stu-id="160f2-190">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="160f2-191">La forma habitual de indicar que un método no puede completar su trabajo correctamente consiste en generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="160f2-191">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="160f2-192">El tipo de excepción y el mensaje asociado a ella describen el error.</span><span class="sxs-lookup"><span data-stu-id="160f2-192">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="160f2-193">En este caso, el método `MakeDeposit` genera una excepción si el importe del depósito es negativo.</span><span class="sxs-lookup"><span data-stu-id="160f2-193">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="160f2-194">El método `MakeWithdrawal` genera una excepción si la cantidad retirada es negativa o si la aplicación del reintegro resulta en un saldo negativo:</span><span class="sxs-lookup"><span data-stu-id="160f2-194">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance:</span></span>

[!code-csharp[DepositAndWithdrawal](../../../samples/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal "Make deposits and withdrawals")]

<span data-ttu-id="160f2-195">La instrucción [`throw`](../language-reference/keywords/throw.md) **genera** una excepción.</span><span class="sxs-lookup"><span data-stu-id="160f2-195">The [`throw`](../language-reference/keywords/throw.md) statement **throws** an exception.</span></span> <span data-ttu-id="160f2-196">De esta forma, se finaliza la ejecución del método actual, que se reanudará cuando se encuentre un bloque `catch` correspondiente.</span><span class="sxs-lookup"><span data-stu-id="160f2-196">Execution of the current method ends, and will resume when a matching `catch` block is found.</span></span> <span data-ttu-id="160f2-197">Se agregará un bloque `catch` para probar este código un poco más adelante.</span><span class="sxs-lookup"><span data-stu-id="160f2-197">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="160f2-198">El constructor debe obtener un cambio para que agregue una transacción inicial, en lugar de actualizar el saldo directamente.</span><span class="sxs-lookup"><span data-stu-id="160f2-198">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="160f2-199">Puesto que ya escribió el método `MakeDeposit`, llámelo desde el constructor.</span><span class="sxs-lookup"><span data-stu-id="160f2-199">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="160f2-200">El constructor terminado debe tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="160f2-200">The finished constructor should look like this:</span></span>

[!code-csharp[Constructor](../../../samples/csharp/classes-quickstart/BankAccount.cs#Constructor "The final version of the constructor")]

<span data-ttu-id="160f2-201"><xref:System.DateTime.Now?displayProperty=nameWithType> es una propiedad que devuelve la fecha y hora actuales.</span><span class="sxs-lookup"><span data-stu-id="160f2-201"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="160f2-202">Agregue algunos depósitos y reintegros en el método `Main` para probar esta operación:</span><span class="sxs-lookup"><span data-stu-id="160f2-202">Test this by adding a few deposits and withdrawals in your `Main` method:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="160f2-203">Después, compruebe si detecta las condiciones de error al tratar de crear una cuenta con un saldo negativo:</span><span class="sxs-lookup"><span data-stu-id="160f2-203">Next, test that you are catching error conditions by trying to create an account with a negative balance:</span></span>

```csharp
// Test that the initial balances must be positive:
try {
    var invalidAccount = new BankAccount("invalid", -55);
} catch (ArgumentOutOfRangeException e)
{
    Console.WriteLine("Exception caught creating account with negative balance");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="160f2-204">Use las [instrucciones `try` y `catch`](../language-reference/keywords/try-catch.md) para marcar un bloque de código que puede generar excepciones y para detectar los errores que se esperan.</span><span class="sxs-lookup"><span data-stu-id="160f2-204">You use the [`try` and `catch` statements](../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions, and to catch those errors that you expect.</span></span> <span data-ttu-id="160f2-205">Puede usar la misma técnica para probar el código que genera un saldo negativo:</span><span class="sxs-lookup"><span data-stu-id="160f2-205">You can use the same technique to test the code that throws for a negative balance:</span></span>

```csharp
// Test for a negative balance
try {
    account.MakeWithdrawal(750, DateTime.Now, "Attempt to overdraw");
} catch (InvalidOperationException e)
{
    Console.WriteLine("Exception caught trying to overdraw");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="160f2-206">Guarde el archivo y escriba `dotnet run` para probarlo.</span><span class="sxs-lookup"><span data-stu-id="160f2-206">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="160f2-207">Desafío: registro de todas las transacciones</span><span class="sxs-lookup"><span data-stu-id="160f2-207">Challenge - log all transactions</span></span>

<span data-ttu-id="160f2-208">Para finalizar este inicio rápido, puede escribir el método `GetAccountHistory` que crea `string` para el historial de transacciones.</span><span class="sxs-lookup"><span data-stu-id="160f2-208">To finish this quick start, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="160f2-209">Agregue este método al tipo `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="160f2-209">add this method to the `BankAccount` type:</span></span>

[!code-csharp[History](../../../samples/csharp/classes-quickstart/BankAccount.cs#History "Display transaction history")]

<span data-ttu-id="160f2-210">Usa la clase <xref:System.Text.StringBuilder> para dar formato a una cadena que contiene una línea para cada transacción.</span><span class="sxs-lookup"><span data-stu-id="160f2-210">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="160f2-211">Se ha visto anteriormente en estos inicios rápidos el código utilizado para dar formato a una cadena.</span><span class="sxs-lookup"><span data-stu-id="160f2-211">You've seen the string formatting code earlier in these quick starts.</span></span> <span data-ttu-id="160f2-212">Un carácter nuevo es `\t`.</span><span class="sxs-lookup"><span data-stu-id="160f2-212">One new character is `\t`.</span></span> <span data-ttu-id="160f2-213">Inserta una pestaña para dar formato a la salida.</span><span class="sxs-lookup"><span data-stu-id="160f2-213">That inserts a tab to format the output.</span></span>

<span data-ttu-id="160f2-214">Agregue esta línea para probarla en **Program.cs**:</span><span class="sxs-lookup"><span data-stu-id="160f2-214">Add this line to test it in **Program.cs**:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="160f2-215">Escriba `dotnet run` para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="160f2-215">Type `dotnet run` to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="160f2-216">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="160f2-216">Next Steps</span></span>

<span data-ttu-id="160f2-217">Si se ha quedado bloqueado, puede consultar el origen de este inicio rápido [en el repositorio de GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/classes-quickstart/).</span><span class="sxs-lookup"><span data-stu-id="160f2-217">If you got stuck, you can see the source for this quick start [in our GitHub repo](https://github.com/dotnet/docs/tree/master/samples/csharp/classes-quickstart/)</span></span>

<span data-ttu-id="160f2-218">Enhorabuena, ha completado todos los inicios rápidos.</span><span class="sxs-lookup"><span data-stu-id="160f2-218">Congratulations, you've finished all our Quick Starts.</span></span> <span data-ttu-id="160f2-219">Si le interesa obtener más información, continúe con los [tutoriales](../tutorials/index.md).</span><span class="sxs-lookup"><span data-stu-id="160f2-219">If you're eager to learn more, try our [tutorials](../tutorials/index.md)</span></span>
