---
title: 'Clases y objetos: tutorial de introducción a C#'
description: Creación del primer programa con C# y análisis de los conceptos orientados a objetos
ms.date: 10/11/2017
ms.custom: mvc
ms.openlocfilehash: a48e5790d2872ca3074bd7ce06c23412086b00f3
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585369"
---
# <a name="explore-object-oriented-programming-with-classes-and-objects"></a><span data-ttu-id="1c598-103">Exploración de la programación orientada a objetos con clases y objetos</span><span class="sxs-lookup"><span data-stu-id="1c598-103">Explore object oriented programming with classes and objects</span></span>

<span data-ttu-id="1c598-104">En este tutorial, creará una aplicación de consola y conocerá las características básicas orientadas a objetos que forman parte del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="1c598-104">In this tutorial, you'll build a console application and see the basic object-oriented features that are part of the C# language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1c598-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1c598-105">Prerequisites</span></span>

<span data-ttu-id="1c598-106">En el tutorial se espera que tenga una máquina configurada para el desarrollo local.</span><span class="sxs-lookup"><span data-stu-id="1c598-106">The tutorial expects that you have a machine set up for local development.</span></span> <span data-ttu-id="1c598-107">En Windows, Linux o macOS, puede usar la CLI de .NET para crear, compilar y ejecutar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1c598-107">On Windows, Linux, or macOS, you can use the .NET CLI to create, build, and run applications.</span></span> <span data-ttu-id="1c598-108">En Windows, también puede usar Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="1c598-108">On Windows, you can use Visual Studio 2019.</span></span> <span data-ttu-id="1c598-109">Para obtener instrucciones de configuración, consulte cómo [configurar el entorno local](local-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1c598-109">For setup instructions, see [Set up your local environment](local-environment.md).</span></span>

## <a name="create-your-application"></a><span data-ttu-id="1c598-110">Creación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="1c598-110">Create your application</span></span>

<span data-ttu-id="1c598-111">En una ventana de terminal, cree un directorio denominado *clases*.</span><span class="sxs-lookup"><span data-stu-id="1c598-111">Using a terminal window, create a directory named *classes*.</span></span> <span data-ttu-id="1c598-112">Creará la aplicación ahí.</span><span class="sxs-lookup"><span data-stu-id="1c598-112">You'll build your application there.</span></span> <span data-ttu-id="1c598-113">Cambie a ese directorio y escriba `dotnet new console` en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="1c598-113">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="1c598-114">Este comando crea la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1c598-114">This command creates your application.</span></span> <span data-ttu-id="1c598-115">Abra *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="1c598-115">Open *Program.cs*.</span></span> <span data-ttu-id="1c598-116">El resultado debería tener un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="1c598-116">It should look like this:</span></span>

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

<span data-ttu-id="1c598-117">En este tutorial, se van a crear tipos nuevos que representan una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="1c598-117">In this tutorial, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="1c598-118">Normalmente los desarrolladores definen cada clase en un archivo de texto diferente.</span><span class="sxs-lookup"><span data-stu-id="1c598-118">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="1c598-119">De esta forma, la tarea de administración resulta más sencilla a medida que aumenta el tamaño del programa.</span><span class="sxs-lookup"><span data-stu-id="1c598-119">That makes it easier to manage as a program grows in size.</span></span> <span data-ttu-id="1c598-120">Cree un archivo denominado *CuentaBancaria.cs* en el directorio *clases*.</span><span class="sxs-lookup"><span data-stu-id="1c598-120">Create a new file named *BankAccount.cs* in the *classes* directory.</span></span>

<span data-ttu-id="1c598-121">Este archivo va a contener la definición de una **cuenta bancaria**.</span><span class="sxs-lookup"><span data-stu-id="1c598-121">This file will contain the definition of a \***bank account** _.</span></span> <span data-ttu-id="1c598-122">La programación orientada a objetos organiza el código mediante la creación de tipos en forma de _\*_clases_\*\*.</span><span class="sxs-lookup"><span data-stu-id="1c598-122">Object Oriented programming organizes code by creating types in the form of _\*_classes_\*\*.</span></span> <span data-ttu-id="1c598-123">Estas clases contienen el código que representa una entidad específica.</span><span class="sxs-lookup"><span data-stu-id="1c598-123">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="1c598-124">La clase `BankAccount` representa una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="1c598-124">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="1c598-125">El código implementa operaciones específicas a través de métodos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="1c598-125">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="1c598-126">En este tutorial, la cuenta bancaria admite el siguiente comportamiento:</span><span class="sxs-lookup"><span data-stu-id="1c598-126">In this tutorial, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="1c598-127">Tiene un número de diez dígitos que identifica la cuenta bancaria de forma única.</span><span class="sxs-lookup"><span data-stu-id="1c598-127">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="1c598-128">Tiene una cadena que almacena el nombre o los nombres de los propietarios.</span><span class="sxs-lookup"><span data-stu-id="1c598-128">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="1c598-129">Se puede consultar el saldo.</span><span class="sxs-lookup"><span data-stu-id="1c598-129">The balance can be retrieved.</span></span>
1. <span data-ttu-id="1c598-130">Acepta depósitos.</span><span class="sxs-lookup"><span data-stu-id="1c598-130">It accepts deposits.</span></span>
1. <span data-ttu-id="1c598-131">Acepta reintegros.</span><span class="sxs-lookup"><span data-stu-id="1c598-131">It accepts withdrawals.</span></span>
1. <span data-ttu-id="1c598-132">El saldo inicial debe ser positivo.</span><span class="sxs-lookup"><span data-stu-id="1c598-132">The initial balance must be positive.</span></span>
1. <span data-ttu-id="1c598-133">Los reintegros no pueden resultar en un saldo negativo.</span><span class="sxs-lookup"><span data-stu-id="1c598-133">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="1c598-134">Definición del tipo de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="1c598-134">Define the bank account type</span></span>

<span data-ttu-id="1c598-135">Puede empezar por crear los datos básicos de una clase que define dicho comportamiento.</span><span class="sxs-lookup"><span data-stu-id="1c598-135">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="1c598-136">Cree un archivo con el comando **File:New**.</span><span class="sxs-lookup"><span data-stu-id="1c598-136">Create a new file using the **File:New** command.</span></span> <span data-ttu-id="1c598-137">Asígnele el nombre *BankAccount.cs*.</span><span class="sxs-lookup"><span data-stu-id="1c598-137">Name it *BankAccount.cs*.</span></span> <span data-ttu-id="1c598-138">Agregue el código siguiente al archivo *BankAccount.cs*:</span><span class="sxs-lookup"><span data-stu-id="1c598-138">Add the following code to your *BankAccount.cs* file:</span></span>

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

<span data-ttu-id="1c598-139">Antes de avanzar, se va a dar un repaso a lo que ha compilado.</span><span class="sxs-lookup"><span data-stu-id="1c598-139">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="1c598-140">La declaración `namespace` permite organizar el código de forma lógica.</span><span class="sxs-lookup"><span data-stu-id="1c598-140">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="1c598-141">Este tutorial es relativamente pequeño, por lo que deberá colocar todo el código en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="1c598-141">This tutorial is relatively small, so you'll put all the code in one namespace.</span></span>

<span data-ttu-id="1c598-142">`public class BankAccount` define la clase o el tipo que va a crear.</span><span class="sxs-lookup"><span data-stu-id="1c598-142">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="1c598-143">Todo lo que se encuentra entre `{` y `}` después de la declaración de clase define el estado y el comportamiento de la clase.</span><span class="sxs-lookup"><span data-stu-id="1c598-143">Everything inside the `{` and `}` that follows the class declaration defines the state and behavior of the class.</span></span> <span data-ttu-id="1c598-144">Hay cinco **miembros** de la clase `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="1c598-144">There are five \***members** _ of the `BankAccount` class.</span></span> <span data-ttu-id="1c598-145">Los tres primeros son _*_propiedades_*_.</span><span class="sxs-lookup"><span data-stu-id="1c598-145">The first three are _*_properties_*_.</span></span> <span data-ttu-id="1c598-146">Las propiedades son elementos de datos que pueden contener código que exige la validación u otras reglas.</span><span class="sxs-lookup"><span data-stu-id="1c598-146">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="1c598-147">Los dos últimos son _\*_métodos_\*\*.</span><span class="sxs-lookup"><span data-stu-id="1c598-147">The last two are _\*_methods_\*\*.</span></span> <span data-ttu-id="1c598-148">Los métodos son bloques de código que realizan una única función.</span><span class="sxs-lookup"><span data-stu-id="1c598-148">Methods are blocks of code that perform a single function.</span></span> <span data-ttu-id="1c598-149">La lectura de los nombres de cada miembro debe proporcionar suficiente información tanto al usuario como a otro desarrollador para entender cuál es la función de la clase.</span><span class="sxs-lookup"><span data-stu-id="1c598-149">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="1c598-150">Apertura de una cuenta nueva</span><span class="sxs-lookup"><span data-stu-id="1c598-150">Open a new account</span></span>

<span data-ttu-id="1c598-151">La primera característica que se va a implementar es la apertura de una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="1c598-151">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="1c598-152">Cuando un cliente abre una cuenta, debe proporcionar un saldo inicial y la información sobre el propietario o los propietarios de esa cuenta.</span><span class="sxs-lookup"><span data-stu-id="1c598-152">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span>

<span data-ttu-id="1c598-153">La creación de un nuevo objeto de tipo `BankAccount` conlleva definir un \***constructor** _ que asigne esos valores.</span><span class="sxs-lookup"><span data-stu-id="1c598-153">Creating a new object of the `BankAccount` type means defining a \***constructor** _ that assigns those values.</span></span> <span data-ttu-id="1c598-154">Un _ *_constructor_*\* es un miembro que tiene el mismo nombre que la clase.</span><span class="sxs-lookup"><span data-stu-id="1c598-154">A _ *_constructor_*\* is a member that has the same name as the class.</span></span> <span data-ttu-id="1c598-155">Se utiliza para inicializar los objetos de ese tipo de clase.</span><span class="sxs-lookup"><span data-stu-id="1c598-155">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="1c598-156">Agregue el siguiente constructor al tipo `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="1c598-156">Add the following constructor to the `BankAccount` type.</span></span> <span data-ttu-id="1c598-157">Coloque el siguiente código encima de la declaración de `MakeDeposit`.</span><span class="sxs-lookup"><span data-stu-id="1c598-157">Place the following code above the declaration of `MakeDeposit`:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="1c598-158">A los constructores se les llama cuando se crea un objeto mediante [`new`](../../language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1c598-158">Constructors are called when you create an object using [`new`](../../language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="1c598-159">Reemplace la línea `Console.WriteLine("Hello World!");` de *Program.cs* por la siguiente línea (reemplace `<name>` por su nombre):</span><span class="sxs-lookup"><span data-stu-id="1c598-159">Replace the line `Console.WriteLine("Hello World!");` in *Program.cs* with the following code (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name>", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="1c598-160">Vamos a ejecutar lo que se ha creado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="1c598-160">Let's run what you've built so far.</span></span> <span data-ttu-id="1c598-161">Si usa Visual Studio, seleccione **Iniciar sin depurar** en el menú **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="1c598-161">If you're using Visual Studio, Select **Start without debugging** from the **Run** menu.</span></span> <span data-ttu-id="1c598-162">Si va a usar una línea de comandos, escriba `dotnet run` en el directorio en el que ha creado el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1c598-162">If you're using a command line, type `dotnet run` in the directory where you've created your project.</span></span>

<span data-ttu-id="1c598-163">¿Ha observado que el número de cuenta está en blanco?</span><span class="sxs-lookup"><span data-stu-id="1c598-163">Did you notice that the account number is blank?</span></span> <span data-ttu-id="1c598-164">Es el momento de solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="1c598-164">It's time to fix that.</span></span> <span data-ttu-id="1c598-165">El número de cuenta debe asignarse cuando se construye el objeto.</span><span class="sxs-lookup"><span data-stu-id="1c598-165">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="1c598-166">Sin embargo, el autor de la llamada no es el responsable de crearlo.</span><span class="sxs-lookup"><span data-stu-id="1c598-166">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="1c598-167">El código de la clase `BankAccount` debe saber cómo asignar nuevos números de cuenta.</span><span class="sxs-lookup"><span data-stu-id="1c598-167">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="1c598-168">Una manera sencilla de hacerlo es empezar con un número de diez dígitos.</span><span class="sxs-lookup"><span data-stu-id="1c598-168">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="1c598-169">Increméntelo cuando cree cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="1c598-169">Increment it when each new account is created.</span></span> <span data-ttu-id="1c598-170">Por último, almacene el número de cuenta actual cuando se construya un objeto.</span><span class="sxs-lookup"><span data-stu-id="1c598-170">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="1c598-171">Agregue una declaración de miembro a la clase `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="1c598-171">Add a member declaration to the `BankAccount` class.</span></span> <span data-ttu-id="1c598-172">Coloque la siguiente línea de código después de la llave de apertura `{` al principio de la clase `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="1c598-172">Place the following line of code after the opening brace `{` at the beginning of the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="1c598-173">Se trata de un miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="1c598-173">This is a data member.</span></span> <span data-ttu-id="1c598-174">Tiene el estado `private`, lo que significa que solo se puede acceder a él con el código incluido en la clase `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="1c598-174">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="1c598-175">Es una forma de separar las responsabilidades públicas (como tener un número de cuenta) de la implementación privada (cómo se generan los números de cuenta).</span><span class="sxs-lookup"><span data-stu-id="1c598-175">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated).</span></span> <span data-ttu-id="1c598-176">También es `static`, lo que significa que se comparte entre todos los objetos `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="1c598-176">It is also `static`, which means it is shared by all of the `BankAccount` objects.</span></span> <span data-ttu-id="1c598-177">El valor de una variable no estática es único para cada instancia del objeto `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="1c598-177">The value of a non-static variable is unique to each instance of the `BankAccount` object.</span></span> <span data-ttu-id="1c598-178">Agregue las dos líneas siguientes al constructor para asignar el número de cuenta:</span><span class="sxs-lookup"><span data-stu-id="1c598-178">Add the following two lines to the constructor to assign the account number.</span></span> <span data-ttu-id="1c598-179">Colóquelas después de la línea donde pone `this.Balance = initialBalance`:</span><span class="sxs-lookup"><span data-stu-id="1c598-179">Place them after the line that says `this.Balance = initialBalance`:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="1c598-180">Escriba `dotnet run` para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="1c598-180">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="1c598-181">Creación de depósitos y reintegros</span><span class="sxs-lookup"><span data-stu-id="1c598-181">Create deposits and withdrawals</span></span>

<span data-ttu-id="1c598-182">La clase de la cuenta bancaria debe aceptar depósitos y reintegros para que el funcionamiento sea adecuado.</span><span class="sxs-lookup"><span data-stu-id="1c598-182">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="1c598-183">Se van a implementar depósitos y reintegros con la creación de un diario de cada transacción de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="1c598-183">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="1c598-184">Ofrece algunas ventajas con respecto al mero hecho de actualizar el saldo en cada transacción.</span><span class="sxs-lookup"><span data-stu-id="1c598-184">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="1c598-185">El historial se puede utilizar para auditar todas las transacciones y administrar los saldos diarios.</span><span class="sxs-lookup"><span data-stu-id="1c598-185">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="1c598-186">Con el cálculo del saldo a partir del historial de todas las transacciones, cuando proceda, todos los errores de una única transacción que se solucionen se reflejarán correctamente en el saldo cuando se realice el siguiente cálculo.</span><span class="sxs-lookup"><span data-stu-id="1c598-186">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="1c598-187">Se va a empezar por crear un tipo para representar una transacción.</span><span class="sxs-lookup"><span data-stu-id="1c598-187">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="1c598-188">Se trata de un tipo simple que no tiene ninguna responsabilidad.</span><span class="sxs-lookup"><span data-stu-id="1c598-188">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="1c598-189">Necesita algunas propiedades.</span><span class="sxs-lookup"><span data-stu-id="1c598-189">It needs a few properties.</span></span> <span data-ttu-id="1c598-190">Cree un archivo denominado *Transaction.cs*.</span><span class="sxs-lookup"><span data-stu-id="1c598-190">Create a new file named *Transaction.cs*.</span></span> <span data-ttu-id="1c598-191">Agregue el código siguiente a él:</span><span class="sxs-lookup"><span data-stu-id="1c598-191">Add the following code to it:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/Transaction.cs":::

<span data-ttu-id="1c598-192">Ahora se va a agregar <xref:System.Collections.Generic.List%601> de objetos `Transaction` a la clase `BankAccount`.</span><span class="sxs-lookup"><span data-stu-id="1c598-192">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="1c598-193">Agregue la siguiente declaración después del constructor en el archivo *BankAccount.cs*:</span><span class="sxs-lookup"><span data-stu-id="1c598-193">Add the following declaration after the constructor in your *BankAccount.cs* file:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="TransactionDeclaration":::

<span data-ttu-id="1c598-194">La clase <xref:System.Collections.Generic.List%601> requiere la importación de un espacio de nombres diferente.</span><span class="sxs-lookup"><span data-stu-id="1c598-194">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="1c598-195">Agregue lo siguiente al principio de *CuentaBancaria.cs*:</span><span class="sxs-lookup"><span data-stu-id="1c598-195">Add the following at the beginning of *BankAccount.cs*:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="1c598-196">Ahora vamos a calcular correctamente `Balance`.</span><span class="sxs-lookup"><span data-stu-id="1c598-196">Now, let's correctly compute the `Balance`.</span></span> <span data-ttu-id="1c598-197">El saldo actual se puede averiguar si se suman los valores de todas las transacciones.</span><span class="sxs-lookup"><span data-stu-id="1c598-197">The current balance can be found by summing the values of all transactions.</span></span> <span data-ttu-id="1c598-198">Como el código es actual, solo puede obtener el saldo inicial de la cuenta, así que tiene que actualizar la propiedad `Balance`.</span><span class="sxs-lookup"><span data-stu-id="1c598-198">As the code is currently, you can only get the initial balance of the account, so you'll have to update the `Balance` property.</span></span> <span data-ttu-id="1c598-199">Reemplace la línea `public decimal Balance { get; }` de *BankAccount.cs* con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="1c598-199">Replace the line `public decimal Balance { get; }` in *BankAccount.cs* with the following code:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="BalanceComputation":::

<span data-ttu-id="1c598-200">En este ejemplo se muestra un aspecto importante de las ***propiedades***.</span><span class="sxs-lookup"><span data-stu-id="1c598-200">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="1c598-201">Ahora va a calcular el saldo cuando otro programador solicite el valor.</span><span class="sxs-lookup"><span data-stu-id="1c598-201">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="1c598-202">El cálculo enumera todas las transacciones y proporciona la suma como el saldo actual.</span><span class="sxs-lookup"><span data-stu-id="1c598-202">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="1c598-203">Después, implemente los métodos `MakeDeposit` y `MakeWithdrawal`.</span><span class="sxs-lookup"><span data-stu-id="1c598-203">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="1c598-204">Estos métodos exigirán las dos reglas finales: el saldo inicial debe ser positivo y ningún reintegro debe generar un saldo negativo.</span><span class="sxs-lookup"><span data-stu-id="1c598-204">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span>

<span data-ttu-id="1c598-205">Esta operación introduce el concepto de las ***excepciones***.</span><span class="sxs-lookup"><span data-stu-id="1c598-205">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="1c598-206">La forma habitual de indicar que un método no puede completar su trabajo correctamente consiste en generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="1c598-206">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="1c598-207">El tipo de excepción y el mensaje asociado a ella describen el error.</span><span class="sxs-lookup"><span data-stu-id="1c598-207">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="1c598-208">En este caso, el método `MakeDeposit` genera una excepción si el importe del depósito es negativo.</span><span class="sxs-lookup"><span data-stu-id="1c598-208">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="1c598-209">El método `MakeWithdrawal` genera una excepción si la cantidad retirada es negativa o si la aplicación del reintegro tiene como resultado un saldo negativo:</span><span class="sxs-lookup"><span data-stu-id="1c598-209">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance.</span></span> <span data-ttu-id="1c598-210">Agregue el código siguiente después de la declaración de la lista `allTransactions`:</span><span class="sxs-lookup"><span data-stu-id="1c598-210">Add the following code after the declaration of the `allTransactions` list:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="DepositAndWithdrawal":::

<span data-ttu-id="1c598-211">La instrucción [`throw`](../../language-reference/keywords/throw.md)**genera** una excepción.</span><span class="sxs-lookup"><span data-stu-id="1c598-211">The [`throw`](../../language-reference/keywords/throw.md) statement **throws** an exception.</span></span> <span data-ttu-id="1c598-212">La ejecución del bloque actual finaliza y el control se transfiere al primer bloque `catch` coincidente que se encuentra en la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1c598-212">Execution of the current block ends, and control transfers to the first matching `catch` block found in the call stack.</span></span> <span data-ttu-id="1c598-213">Se agregará un bloque `catch` para probar este código un poco más adelante.</span><span class="sxs-lookup"><span data-stu-id="1c598-213">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="1c598-214">El constructor debe obtener un cambio para que agregue una transacción inicial, en lugar de actualizar el saldo directamente.</span><span class="sxs-lookup"><span data-stu-id="1c598-214">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="1c598-215">Puesto que ya escribió el método `MakeDeposit`, llámelo desde el constructor.</span><span class="sxs-lookup"><span data-stu-id="1c598-215">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="1c598-216">El constructor terminado debe tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="1c598-216">The finished constructor should look like this:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="Constructor":::

<span data-ttu-id="1c598-217"><xref:System.DateTime.Now?displayProperty=nameWithType> es una propiedad que devuelve la fecha y hora actuales.</span><span class="sxs-lookup"><span data-stu-id="1c598-217"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="1c598-218">Para probar esto, agregue algunos depósitos y reintegros en el método `Main`, a continuación del código que crea un elemento `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="1c598-218">Test this by adding a few deposits and withdrawals in your `Main` method, following the code that creates a new `BankAccount`:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "Friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="1c598-219">Después, compruebe si detecta las condiciones de error al tratar de crear una cuenta con un saldo negativo.</span><span class="sxs-lookup"><span data-stu-id="1c598-219">Next, test that you are catching error conditions by trying to create an account with a negative balance.</span></span> <span data-ttu-id="1c598-220">Agregue el código siguiente después del código anterior que acaba de agregar:</span><span class="sxs-lookup"><span data-stu-id="1c598-220">Add the following code after the preceding code you just added:</span></span>

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

<span data-ttu-id="1c598-221">Use las [instrucciones `try` y `catch`](../../language-reference/keywords/try-catch.md) para marcar un bloque de código que puede generar excepciones y para detectar los errores que se esperan.</span><span class="sxs-lookup"><span data-stu-id="1c598-221">You use the [`try` and `catch` statements](../../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions and to catch those errors that you expect.</span></span> <span data-ttu-id="1c598-222">Puede usar la misma técnica para probar el código que genera una excepción para un saldo negativo.</span><span class="sxs-lookup"><span data-stu-id="1c598-222">You can use the same technique to test the code that throws an exception for a negative balance.</span></span> <span data-ttu-id="1c598-223">Agregue el código siguiente al final del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="1c598-223">Add the following code at the end of your `Main` method:</span></span>

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

<span data-ttu-id="1c598-224">Guarde el archivo y escriba `dotnet run` para probarlo.</span><span class="sxs-lookup"><span data-stu-id="1c598-224">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="1c598-225">Desafío: registro de todas las transacciones</span><span class="sxs-lookup"><span data-stu-id="1c598-225">Challenge - log all transactions</span></span>

<span data-ttu-id="1c598-226">Para finalizar este tutorial, puede escribir el método `GetAccountHistory` que crea `string` para el historial de transacciones.</span><span class="sxs-lookup"><span data-stu-id="1c598-226">To finish this tutorial, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="1c598-227">Agregue este método al tipo `BankAccount`:</span><span class="sxs-lookup"><span data-stu-id="1c598-227">Add this method to the `BankAccount` type:</span></span>

:::code language="csharp" source="./snippets/introduction-to-classes/BankAccount.cs" id="History":::

<span data-ttu-id="1c598-228">Usa la clase <xref:System.Text.StringBuilder> para dar formato a una cadena que contiene una línea para cada transacción.</span><span class="sxs-lookup"><span data-stu-id="1c598-228">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="1c598-229">Se ha visto anteriormente en estos tutoriales el código utilizado para dar formato a una cadena.</span><span class="sxs-lookup"><span data-stu-id="1c598-229">You've seen the string formatting code earlier in these tutorials.</span></span> <span data-ttu-id="1c598-230">Un carácter nuevo es `\t`.</span><span class="sxs-lookup"><span data-stu-id="1c598-230">One new character is `\t`.</span></span> <span data-ttu-id="1c598-231">Inserta una pestaña para dar formato a la salida.</span><span class="sxs-lookup"><span data-stu-id="1c598-231">That inserts a tab to format the output.</span></span>

<span data-ttu-id="1c598-232">Agregue esta línea para probarla en *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="1c598-232">Add this line to test it in *Program.cs*:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="1c598-233">Ejecute el programa para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="1c598-233">Run your program to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1c598-234">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1c598-234">Next steps</span></span>

<span data-ttu-id="1c598-235">Si se ha quedado bloqueado, puede consultar el origen de este tutorial [en el repositorio de GitHub](https://github.com/dotnet/docs/tree/master/docs/csharp/tutorials/intro-to-csharp/snippets/introduction-to-classes).</span><span class="sxs-lookup"><span data-stu-id="1c598-235">If you got stuck, you can see the source for this tutorial [in our GitHub repo](https://github.com/dotnet/docs/tree/master/docs/csharp/tutorials/intro-to-csharp/snippets/introduction-to-classes).</span></span>

<span data-ttu-id="1c598-236">Puede continuar con el tutorial de la [programación orientada a objetos](object-oriented-programming.md).</span><span class="sxs-lookup"><span data-stu-id="1c598-236">You can continue with the [object oriented programming](object-oriented-programming.md) tutorial.</span></span>

<span data-ttu-id="1c598-237">Puede aprender más sobre estos conceptos en los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1c598-237">You can learn more about these concepts in these articles:</span></span>

- [<span data-ttu-id="1c598-238">Instrucciones If y else</span><span class="sxs-lookup"><span data-stu-id="1c598-238">If and else statement</span></span>](../../language-reference/keywords/if-else.md)
- [<span data-ttu-id="1c598-239">Instrucción while</span><span class="sxs-lookup"><span data-stu-id="1c598-239">While statement</span></span>](../../language-reference/keywords/while.md)
- [<span data-ttu-id="1c598-240">Instrucción do</span><span class="sxs-lookup"><span data-stu-id="1c598-240">Do statement</span></span>](../../language-reference/keywords/do.md)
- [<span data-ttu-id="1c598-241">Instrucción for</span><span class="sxs-lookup"><span data-stu-id="1c598-241">For statement</span></span>](../../language-reference/keywords/for.md)
