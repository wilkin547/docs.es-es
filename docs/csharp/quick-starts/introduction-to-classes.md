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
ms.openlocfilehash: b7598309f48cbccf2d270be53a4b40dae11e8df8
ms.sourcegitcommit: 9bee08539b1886c9d57fa3d5bd8a58dfdd7cad94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2017
---
# <a name="introduction-to-classes"></a><span data-ttu-id="f5ad8-103">Introducción a las clases</span><span class="sxs-lookup"><span data-stu-id="f5ad8-103">Introduction to classes</span></span>

<span data-ttu-id="f5ad8-104">En esta guía de inicio rápido se supone que cuenta con una máquina que puede usar para el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-104">This quick start expects that you have a machine you can use for development.</span></span> <span data-ttu-id="f5ad8-105">El tema de .NET [Iniciar en 10 minutos](https://www.microsoft.com/net/core) cuenta con instrucciones para configurar el entorno de desarrollo local en Mac, PC o Linux.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-105">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="f5ad8-106">En las [guías de inicio rápido de introducción al entorno local](local-environment.md) puede obtener información general sobre los comandos que usará con vínculos que amplían la información.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-106">A quick overview of the commands you'll use is in the [introduction to the local quick starts](local-environment.md) with links to more details.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="f5ad8-107">Creación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="f5ad8-107">Create your application</span></span>

<span data-ttu-id="f5ad8-108">En una ventana de terminal, cree un directorio denominado **clases**.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-108">Using a terminal window, create a directory named **classes**.</span></span> <span data-ttu-id="f5ad8-109">Creará la aplicación ahí.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-109">You'll build your application there.</span></span> <span data-ttu-id="f5ad8-110">Cambie a ese directorio y escriba `dotnet new console` en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-110">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="f5ad8-111">Este comando crea la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-111">This command creates your application.</span></span> <span data-ttu-id="f5ad8-112">Abra **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-112">Open **Program.cs**.</span></span> <span data-ttu-id="f5ad8-113">El resultado debería tener un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="f5ad8-113">It should look like this:</span></span>

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

<span data-ttu-id="f5ad8-114">En este inicio rápido, se van a crear tipos nuevos que representan una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-114">In this quick start, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="f5ad8-115">Normalmente los desarrolladores definen cada clase en un archivo de texto diferente.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-115">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="f5ad8-116">De esta forma, la tarea de administración resulta más sencilla a medida que aumenta el tamaño del programa.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-116">That makes it easier to manage as a program grows in size.</span></span>  <span data-ttu-id="f5ad8-117">Cree un archivo denominado **CuentaBancaria.cs** en el directorio **clases**.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-117">Create a new file named **BankAccount.cs** in the **classes** directory.</span></span> 

<span data-ttu-id="f5ad8-118">Este archivo contendrá la definición de un ***cuenta bancaria***.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-118">This file will contain the deefinition of a ***bank account***.</span></span> <span data-ttu-id="f5ad8-119">La programación orientada a objetos organiza el código mediante la creación de tipos en forma de ***clases***.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-119">Object Oriented programming organizes code by creating types in the form of ***classes***.</span></span> <span data-ttu-id="f5ad8-120">Estas clases contienen el código que representa una entidad específica.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-120">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="f5ad8-121">La clase `BankAccount` representa una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-121">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="f5ad8-122">El código implementa operaciones específicas a través de métodos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-122">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="f5ad8-123">En este inicio rápido, la cuenta bancaria admite el siguiente comportamiento:</span><span class="sxs-lookup"><span data-stu-id="f5ad8-123">In this quick start, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="f5ad8-124">Tiene un número de diez dígitos que identifica la cuenta bancaria de forma única.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-124">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="f5ad8-125">Tiene una cadena que almacena el nombre o los nombres de los propietarios.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-125">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="f5ad8-126">Se puede consultar el saldo.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-126">The balance can be retrieved.</span></span>
1. <span data-ttu-id="f5ad8-127">Acepta depósitos.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-127">It accepts deposits.</span></span>
1. <span data-ttu-id="f5ad8-128">Acepta reintegros.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-128">It accepts withdrawals.</span></span>
1. <span data-ttu-id="f5ad8-129">El saldo inicial debe ser positivo.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-129">The initial balance must be positive.</span></span>
1. <span data-ttu-id="f5ad8-130">Los reintegros no pueden resultar en un saldo negativo.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-130">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="f5ad8-131">Definición del tipo de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="f5ad8-131">Define the bank account type</span></span>

<span data-ttu-id="f5ad8-132">Puede empezar por crear los datos básicos de una clase que define dicho comportamiento.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-132">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="f5ad8-133">El resultado debería tener un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="f5ad8-133">It would look like this:</span></span>

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

<span data-ttu-id="f5ad8-134">Antes de avanzar, se va a dar un repaso a lo que ha compilado.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-134">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="f5ad8-135">La declaración `namespace` permite organizar el código de forma lógica.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-135">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="f5ad8-136">Este inicio rápido es relativamente pequeño, por lo que deberá colocar todo el código en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-136">This quick start is relatively small, so you'll put all the code in one namespace.</span></span> 

<span data-ttu-id="f5ad8-137">`public class BankAccount` define la clase o el tipo que va a crear.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-137">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="f5ad8-138">Todo lo que se encuentra entre `{` y `}` después de la declaración de clase define el comportamiento de la clase.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-138">Everything inside the `{` and `}` that follows the class declaration defines the behavior of the class.</span></span> <span data-ttu-id="f5ad8-139">Hay cinco ***miembros*** de la clase `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-139">There are five ***members*** of the `BankAccount` class.</span></span> <span data-ttu-id="f5ad8-140">Los tres primeros son ***propiedades***.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-140">The first three are ***properties***.</span></span> <span data-ttu-id="f5ad8-141">Las propiedades son elementos de datos que pueden contener código que exige la validación u otras reglas.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-141">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="f5ad8-142">Los dos últimos son ***métodos***.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-142">The last two are ***methods***.</span></span> <span data-ttu-id="f5ad8-143">Los métodos son bloques de código que realizan una única función.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-143">Methods are blocks of code that peform a single function.</span></span> <span data-ttu-id="f5ad8-144">La lectura de los nombres de cada miembro debe proporcionar suficiente información tanto al usuario como a otro desarrollador para entender cuál es la función de la clase.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-144">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="f5ad8-145">Apertura de una cuenta nueva</span><span class="sxs-lookup"><span data-stu-id="f5ad8-145">Open a new account</span></span>

<span data-ttu-id="f5ad8-146">La primera característica que se va a implementar es la apertura de una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-146">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="f5ad8-147">Cuando un cliente abre una cuenta, debe proporcionar un saldo inicial y la información sobre el propietario o los propietarios de esa cuenta.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-147">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span> 

<span data-ttu-id="f5ad8-148">La creación de un objeto del tipo `BankAccount` conlleva definir un ***constructor*** que asigne dichos valores.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-148">Creating a new object of the `BankAccount` type means defining a ***constructor*** that assigns those values.</span></span> <span data-ttu-id="f5ad8-149">Un ***constructor*** es un miembro que tiene el mismo nombre que la clase.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-149">A ***constructor*** is a member that has the same name as the class.</span></span> <span data-ttu-id="f5ad8-150">Se utiliza para inicializar los objetos de ese tipo de clase.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-150">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="f5ad8-151">Agregue el siguiente constructor al tipo `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="f5ad8-151">Add the following constructor to the `BankAccount` type:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="f5ad8-152">A los constructores se les llama cuando se crea un objeto mediante [`new`](../language-reference/keywords/new.md).</span><span class="sxs-lookup"><span data-stu-id="f5ad8-152">Constructors are called when you create an object using [`new`](../language-reference/keywords/new.md).</span></span> <span data-ttu-id="f5ad8-153">Reemplace la línea `Console.WriteLine("Hello World!");` de ***program.cs*** con la siguiente línea (reemplace `<name>` con su nombre):</span><span class="sxs-lookup"><span data-stu-id="f5ad8-153">Replace the line `Console.WriteLine("Hello World!");` in ***program.cs*** with the following line (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="f5ad8-154">Escriba `dotnet run` para ver lo que sucede.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-154">Type `dotnet run` to see what happens.</span></span>  

<span data-ttu-id="f5ad8-155">¿Ha observado que el número de cuenta está en blanco?</span><span class="sxs-lookup"><span data-stu-id="f5ad8-155">Did you notice that the account number is blank?</span></span> <span data-ttu-id="f5ad8-156">Es el momento de solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-156">It's time to fix that.</span></span> <span data-ttu-id="f5ad8-157">El número de cuenta debe asignarse cuando se construye el objeto.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-157">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="f5ad8-158">Sin embargo, el autor de la llamada no es el responsable de crearlo.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-158">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="f5ad8-159">El código de la clase `BankAccount` debe saber cómo asignar nuevos números de cuenta.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-159">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="f5ad8-160">Una manera sencilla de hacerlo es empezar con un número de diez dígitos.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-160">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="f5ad8-161">Increméntelo cuando cree cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-161">Increment it when each new account is created.</span></span> <span data-ttu-id="f5ad8-162">Por último, almacene el número de cuenta actual cuando se construya un objeto.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-162">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="f5ad8-163">Agregue la siguiente declaración de miembro a la clase `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="f5ad8-163">Add the following member declaration to the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="f5ad8-164">Se trata de un miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-164">This is a data member.</span></span> <span data-ttu-id="f5ad8-165">Tiene el estado `private`, lo que significa que solo se puede acceder a él con el código incluido en la clase `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-165">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="f5ad8-166">Es una forma de separar las responsabilidades públicas (como tener un número de cuenta) de la implementación privada (cómo se generan los números de cuenta). Agregue las dos líneas siguientes al constructor para asignar el número de cuenta:</span><span class="sxs-lookup"><span data-stu-id="f5ad8-166">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated.) Add the following two lines to the constructor to assign the account number:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="f5ad8-167">Escriba `dotnet run` para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-167">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="f5ad8-168">Creación de depósitos y reintegros</span><span class="sxs-lookup"><span data-stu-id="f5ad8-168">Create deposits and withdrawals</span></span>

<span data-ttu-id="f5ad8-169">La clase de la cuenta bancaria debe aceptar depósitos y reintegros para que el funcionamiento sea adecuado.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-169">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="f5ad8-170">Se van a implementar depósitos y reintegros con la creación de un diario de cada transacción de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-170">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="f5ad8-171">Ofrece algunas ventajas con respecto al mero hecho de actualizar el saldo en cada transacción.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-171">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="f5ad8-172">El historial se puede utilizar para auditar todas las transacciones y administrar los saldos diarios.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-172">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="f5ad8-173">Con el cálculo del saldo a partir del historial de todas las transacciones, cuando proceda, todos los errores de una única transacción que se solucionen se reflejarán correctamente en el saldo cuando se realice el siguiente cálculo.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-173">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="f5ad8-174">Se va a empezar por crear un tipo para representar una transacción.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-174">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="f5ad8-175">Se trata de un tipo simple que no tiene ninguna responsabilidad.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-175">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="f5ad8-176">Necesita algunas propiedades.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-176">It needs a few properties.</span></span> <span data-ttu-id="f5ad8-177">Cree un archivo denominado ***Transaction.cs***.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-177">Create a new file named ***Transaction.cs***.</span></span> <span data-ttu-id="f5ad8-178">Agregue el código siguiente a él:</span><span class="sxs-lookup"><span data-stu-id="f5ad8-178">Add the following code to it:</span></span>

[!code-csharp[Transaction](../../../samples/csharp/classes-quickstart/Transaction.cs "Transaction declaration")]

<span data-ttu-id="f5ad8-179">Ahora se va a agregar <xref:System.Collections.Generic.List%601> de objetos `Transaction` a la clase `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-179">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="f5ad8-180">Agregue la declaración siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5ad8-180">Add the following declaration:</span></span>

[!code-csharp[TransactionDecl](../../../samples/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration "Transaction declaration")]

<span data-ttu-id="f5ad8-181">La clase <xref:System.Collections.Generic.List%601> requiere la importación de un espacio de nombres diferente.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-181">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="f5ad8-182">Agregue lo siguiente al principio de **CuentaBancaria.cs**:</span><span class="sxs-lookup"><span data-stu-id="f5ad8-182">Add the following at the beginning of **BankAccount.cs**:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="f5ad8-183">Ahora se va a cambiar la forma en que se notifica `Balance`.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-183">Now, let's change how the `Balance` is reported.</span></span>  <span data-ttu-id="f5ad8-184">Esto se puede conseguir con la suma de los valores de todas las transacciones.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-184">It can be found by summing the values of all transactions.</span></span> <span data-ttu-id="f5ad8-185">Modifique la declaración de `Balance` en la clase `BankAccount` por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5ad8-185">Modify the declaration of `Balance` in the `BankAccount` class to the following:</span></span>

[!code-csharp[BalanceComputation](../../../samples/csharp/classes-quickstart/BankAccount.cs#BalanceComputation "Computing the balance")]

<span data-ttu-id="f5ad8-186">En este ejemplo se muestra un aspecto importante de las ***propiedades***.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-186">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="f5ad8-187">Ahora va a calcular el saldo cuando otro programador solicite el valor.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-187">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="f5ad8-188">El cálculo enumera todas las transacciones y proporciona la suma como el saldo actual.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-188">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="f5ad8-189">Después, implemente los métodos `MakeDeposit` y `MakeWithdrawal`.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-189">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="f5ad8-190">Estos métodos exigirán las dos reglas finales: el saldo inicial debe ser positivo y ningún reintegro debe generar un saldo negativo.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-190">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span> 

<span data-ttu-id="f5ad8-191">Esta operación introduce el concepto de las ***excepciones***.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-191">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="f5ad8-192">La forma habitual de indicar que un método no puede completar su trabajo correctamente consiste en generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-192">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="f5ad8-193">El tipo de excepción y el mensaje asociado a ella describen el error.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-193">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="f5ad8-194">En este caso, el método `MakeDeposit` genera una excepción si el importe del depósito es negativo.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-194">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="f5ad8-195">El método `MakeWithdrawal` genera una excepción si la cantidad retirada es negativa o si la aplicación del reintegro resulta en un saldo negativo:</span><span class="sxs-lookup"><span data-stu-id="f5ad8-195">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance:</span></span>

[!code-csharp[DepositAndWithdrawal](../../../samples/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal "Make deposits and withdrawals")]

<span data-ttu-id="f5ad8-196">La instrucción [`throw`](../language-reference/keywords/throw.md) **genera** una excepción.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-196">The [`throw`](../language-reference/keywords/throw.md) statement **throws** an exception.</span></span> <span data-ttu-id="f5ad8-197">De esta forma, se finaliza la ejecución del método actual, que se reanudará cuando se encuentre un bloque `catch` correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-197">Execution of the current method ends, and will resume when a matching `catch` block is found.</span></span> <span data-ttu-id="f5ad8-198">Se agregará un bloque `catch` para probar este código un poco más adelante.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-198">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="f5ad8-199">El constructor debe obtener un cambio para que agregue una transacción inicial, en lugar de actualizar el saldo directamente.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-199">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="f5ad8-200">Puesto que ya escribió el método `MakeDeposit`, llámelo desde el constructor.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-200">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="f5ad8-201">El constructor terminado debe tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="f5ad8-201">The finished constructor should look like this:</span></span>

[!code-csharp[Constructor](../../../samples/csharp/classes-quickstart/BankAccount.cs#Constructor "The final version of the constructor")]

<span data-ttu-id="f5ad8-202"><xref:System.DateTime.Now?displayProperty=nameWithType> es una propiedad que devuelve la fecha y hora actuales.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-202"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="f5ad8-203">Agregue algunos depósitos y reintegros en el método `Main` para probar esta operación:</span><span class="sxs-lookup"><span data-stu-id="f5ad8-203">Test this by adding a few deposits and withdrawals in your `Main` method:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="f5ad8-204">Después, compruebe si detecta las condiciones de error al tratar de crear una cuenta con un saldo negativo:</span><span class="sxs-lookup"><span data-stu-id="f5ad8-204">Next, test that you are catching error conditions by trying to create an account with a negative balance:</span></span>

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

<span data-ttu-id="f5ad8-205">Use las [instrucciones `try` y `catch`](../language-reference/keywords/try-catch.md) para marcar un bloque de código que puede generar excepciones y para detectar los errores que se esperan.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-205">You use the [`try` and `catch` statements](../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions, and to catch those errors that you expect.</span></span> <span data-ttu-id="f5ad8-206">Puede usar la misma técnica para probar el código que genera un saldo negativo:</span><span class="sxs-lookup"><span data-stu-id="f5ad8-206">You can use the same technique to test the code that throws for a negative balance:</span></span>

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

<span data-ttu-id="f5ad8-207">Guarde el archivo y escriba `dotnet run` para probarlo.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-207">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="f5ad8-208">Desafío: registro de todas las transacciones</span><span class="sxs-lookup"><span data-stu-id="f5ad8-208">Challenge - log all transactions</span></span>

<span data-ttu-id="f5ad8-209">Para finalizar este inicio rápido, puede escribir el método `GetAccountHistory` que crea `string` para el historial de transacciones.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-209">To finish this quick start, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="f5ad8-210">Agregue este método al tipo `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="f5ad8-210">add this method to the `BankAccount` type:</span></span>

[!code-csharp[History](../../../samples/csharp/classes-quickstart/BankAccount.cs#History "Display transaction history")]

<span data-ttu-id="f5ad8-211">Usa la clase <xref:System.Text.StringBuilder> para dar formato a una cadena que contiene una línea para cada transacción.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-211">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="f5ad8-212">Se ha visto anteriormente en estos inicios rápidos el código utilizado para dar formato a una cadena.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-212">You've seen the string formatting code earlier in these quick starts.</span></span> <span data-ttu-id="f5ad8-213">Un carácter nuevo es `\t`.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-213">One new character is `\t`.</span></span> <span data-ttu-id="f5ad8-214">Inserta una pestaña para dar formato a la salida.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-214">That inserts a tab to format the output.</span></span>

<span data-ttu-id="f5ad8-215">Agregue esta línea para probarla en **Program.cs**:</span><span class="sxs-lookup"><span data-stu-id="f5ad8-215">Add this line to test it in **Program.cs**:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="f5ad8-216">Escriba `dotnet run` para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-216">Type `dotnet run` to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f5ad8-217">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f5ad8-217">Next Steps</span></span>

<span data-ttu-id="f5ad8-218">Si se ha quedado bloqueado, puede consultar el origen de este inicio rápido [en el repositorio de GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/classes-quickstart/).</span><span class="sxs-lookup"><span data-stu-id="f5ad8-218">If you got stuck, you can see the source for this quick start [in our GitHub repo](https://github.com/dotnet/docs/tree/master/samples/csharp/classes-quickstart/)</span></span>

<span data-ttu-id="f5ad8-219">Enhorabuena, ha completado todos los inicios rápidos.</span><span class="sxs-lookup"><span data-stu-id="f5ad8-219">Congratulations, you've finished all our Quick Starts.</span></span> <span data-ttu-id="f5ad8-220">Si le interesa obtener más información, continúe con los [tutoriales](../tutorials/index.md).</span><span class="sxs-lookup"><span data-stu-id="f5ad8-220">If you're eager to learn more, try our [tutorials](../tutorials/index.md)</span></span>
