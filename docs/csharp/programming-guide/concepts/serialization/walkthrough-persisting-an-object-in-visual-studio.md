---
title: 'Tutorial: Conservar un objeto con C#'
description: En este ejemplo se crea un objeto Loan básico en C# y se conservan los datos en un archivo; luego, se crea un objeto con datos del archivo.
ms.date: 04/26/2018
ms.openlocfilehash: 0fc733982b7800653a3c8c283bd0af8384d72168
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104876453"
---
# <a name="walkthrough-persisting-an-object-using-c"></a><span data-ttu-id="458f4-103">Tutorial: Conservar un objeto con C\#</span><span class="sxs-lookup"><span data-stu-id="458f4-103">Walkthrough: persisting an object using C\#</span></span>

<span data-ttu-id="458f4-104">Puede usar la serialización para conservar los datos de un objeto entre instancias, lo que le permite almacenar valores y recuperarlos la próxima vez que se cree una instancia del objeto.</span><span class="sxs-lookup"><span data-stu-id="458f4-104">You can use serialization to persist an object's data between instances, which enables you to store values and retrieve them the next time that the object is instantiated.</span></span>

<span data-ttu-id="458f4-105">En este tutorial, creará un objeto `Loan` básico y conservará sus datos en un archivo.</span><span class="sxs-lookup"><span data-stu-id="458f4-105">In this walkthrough, you will create a basic `Loan` object and persist its data to a file.</span></span> <span data-ttu-id="458f4-106">Después, recuperará los datos del archivo cuando vuelva a crear el objeto.</span><span class="sxs-lookup"><span data-stu-id="458f4-106">You will then retrieve the data from the file when you re-create the object.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="458f4-107">En este ejemplo se crea un nuevo archivo, si este no existe aún.</span><span class="sxs-lookup"><span data-stu-id="458f4-107">This example creates a new file if the file does not already exist.</span></span> <span data-ttu-id="458f4-108">Si una aplicación debe crear un archivo, es necesario que tenga el permiso `Create` en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="458f4-108">If an application must create a file, that application must have `Create` permission for the folder.</span></span> <span data-ttu-id="458f4-109">Los permisos se establecen mediante el uso de las listas de control de acceso.</span><span class="sxs-lookup"><span data-stu-id="458f4-109">Permissions are set by using access control lists.</span></span> <span data-ttu-id="458f4-110">Si el archivo ya existe, la aplicación necesitará solo un permiso `Write`, un permiso menor.</span><span class="sxs-lookup"><span data-stu-id="458f4-110">If the file already exists, the application needs only `Write` permission, a lesser permission.</span></span> <span data-ttu-id="458f4-111">Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder solo permisos `Read` a un único archivo (en lugar de crear permisos para una carpeta).</span><span class="sxs-lookup"><span data-stu-id="458f4-111">Where possible, it's more secure to create the file during deployment and only grant `Read` permissions to a single file (instead of Create permissions for a folder).</span></span> <span data-ttu-id="458f4-112">También es más seguro escribir datos en carpetas de usuario en lugar de hacerlo en la carpeta raíz o en la carpeta Archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="458f4-112">Also, it's more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="458f4-113">En este ejemplo se almacenan datos en un archivo de formato binario.</span><span class="sxs-lookup"><span data-stu-id="458f4-113">This example stores data in a binary format file.</span></span> <span data-ttu-id="458f4-114">Estos formatos no deben usarse para datos confidenciales, como contraseñas o información de tarjetas de crédito.</span><span class="sxs-lookup"><span data-stu-id="458f4-114">These formats should not be used for sensitive data, such as passwords or credit-card information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="458f4-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="458f4-115">Prerequisites</span></span>

- <span data-ttu-id="458f4-116">Para compilar y ejecutar, instalar el [SDK de .NET Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="458f4-116">To build and run, install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

- <span data-ttu-id="458f4-117">Instale el editor de código que prefiera si aún no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="458f4-117">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="458f4-118">¿Es necesario instalar un editor de código?</span><span class="sxs-lookup"><span data-stu-id="458f4-118">Need to install a code editor?</span></span> <span data-ttu-id="458f4-119">Pruebe [Visual Studio](https://visualstudio.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="458f4-119">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

- <span data-ttu-id="458f4-120">El ejemplo requiere C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="458f4-120">The example requires C# 7.3.</span></span> <span data-ttu-id="458f4-121">Consulte [Seleccionar la versión del lenguaje C#](../../../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="458f4-121">See [Select the C# language version](../../../language-reference/configure-language-version.md)</span></span>

<span data-ttu-id="458f4-122">En el [repositorio de GitHub de ejemplos de .NET](https://github.com/dotnet/samples/tree/main/csharp/serialization) puede examinar el código de ejemplo en línea.</span><span class="sxs-lookup"><span data-stu-id="458f4-122">You can examine the sample code online [at the .NET samples GitHub repository](https://github.com/dotnet/samples/tree/main/csharp/serialization).</span></span>

## <a name="creating-the-loan-object"></a><span data-ttu-id="458f4-123">Crear el objeto Loan</span><span class="sxs-lookup"><span data-stu-id="458f4-123">Creating the loan object</span></span>

<span data-ttu-id="458f4-124">El primer paso consiste en crear una clase `Loan` y una aplicación de consola que use la clase:</span><span class="sxs-lookup"><span data-stu-id="458f4-124">The first step is to create a `Loan` class and a console application that uses the class:</span></span>

1. <span data-ttu-id="458f4-125">Cree una aplicación.</span><span class="sxs-lookup"><span data-stu-id="458f4-125">Create a new application.</span></span> <span data-ttu-id="458f4-126">Escriba `dotnet new console -o serialization` para crear una aplicación de consola en un subdirectorio llamado `serialization`.</span><span class="sxs-lookup"><span data-stu-id="458f4-126">Type `dotnet new console -o serialization` to create a new console application in a subdirectory named `serialization`.</span></span>
1. <span data-ttu-id="458f4-127">Abra la aplicación en el editor y agregue una nueva clase denominada `Loan.cs`.</span><span class="sxs-lookup"><span data-stu-id="458f4-127">Open the application in your editor, and add a new class named `Loan.cs`.</span></span>
1. <span data-ttu-id="458f4-128">Agregue el siguiente código a la clase `Loan`:</span><span class="sxs-lookup"><span data-stu-id="458f4-128">Add the following code to your `Loan` class:</span></span>

[!code-csharp[Loan class definition](../../../../../samples/snippets/csharp/serialization/Loan.cs#1)]

<span data-ttu-id="458f4-129">También tendrá que crear una aplicación que use la clase `Loan`.</span><span class="sxs-lookup"><span data-stu-id="458f4-129">You will also have to create an application that uses the `Loan` class.</span></span>

## <a name="serialize-the-loan-object"></a><span data-ttu-id="458f4-130">Serializar el objeto Loan</span><span class="sxs-lookup"><span data-stu-id="458f4-130">Serialize the loan object</span></span>

1. <span data-ttu-id="458f4-131">Abra `Program.cs`.</span><span class="sxs-lookup"><span data-stu-id="458f4-131">Open `Program.cs`.</span></span> <span data-ttu-id="458f4-132">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="458f4-132">Add the following code:</span></span>

[!code-csharp[Create a loan object](../../../../../samples/snippets/csharp/serialization/Program.cs#1)]

<span data-ttu-id="458f4-133">Agregue un controlador de eventos del evento `PropertyChanged` y unas cuantas líneas para modificar el objeto `Loan` y ver los cambios.</span><span class="sxs-lookup"><span data-stu-id="458f4-133">Add an event handler for the `PropertyChanged` event, and a few lines to modify the `Loan` object and display the changes.</span></span> <span data-ttu-id="458f4-134">En el siguiente código puede ver las adiciones realizadas:</span><span class="sxs-lookup"><span data-stu-id="458f4-134">You can see the additions in the following code:</span></span>

[!code-csharp[Listening for the PropertyChanged event](../../../../../samples/snippets/csharp/serialization/Program.cs#2)]

<span data-ttu-id="458f4-135">Llegado este punto, puede ejecutar el código y ver el resultado actual:</span><span class="sxs-lookup"><span data-stu-id="458f4-135">At this point, you can run the code, and see the current output:</span></span>

```console
New customer value: Henry Clay
7.5
7.1
```

<span data-ttu-id="458f4-136">Si ejecuta esta aplicación repetidamente, verá que siempre escribe los mismos valores.</span><span class="sxs-lookup"><span data-stu-id="458f4-136">Running this application repeatedly always writes the same values.</span></span> <span data-ttu-id="458f4-137">Se creará un objeto Loan cada vez que ejecute el programa.</span><span class="sxs-lookup"><span data-stu-id="458f4-137">A new Loan object is created every time you run the program.</span></span> <span data-ttu-id="458f4-138">En el mundo real, las tasas de interés cambian periódicamente, pero no necesariamente cada vez que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="458f4-138">In the real world, interest rates change periodically, but not necessarily every time that the application is run.</span></span> <span data-ttu-id="458f4-139">El código de serialización conlleva que se va a conservar la tasa de interés más reciente entre las instancias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="458f4-139">Serialization code means you preserve the most recent interest rate between instances of the application.</span></span> <span data-ttu-id="458f4-140">En el paso siguiente, hará esto agregando la serialización a la clase Loan.</span><span class="sxs-lookup"><span data-stu-id="458f4-140">In the next step, you will do just that by adding serialization to the Loan class.</span></span>

## <a name="using-serialization-to-persist-the-object"></a><span data-ttu-id="458f4-141">Usar la serialización para conservar el objeto</span><span class="sxs-lookup"><span data-stu-id="458f4-141">Using Serialization to Persist the Object</span></span>

<span data-ttu-id="458f4-142">Para conservar los valores de la clase Loan, primero debe marcar la clase con el atributo `Serializable`.</span><span class="sxs-lookup"><span data-stu-id="458f4-142">In order to persist the values for the Loan class, you must first mark the class with the `Serializable` attribute.</span></span> <span data-ttu-id="458f4-143">Agregue el siguiente código encima de la declaración de la clase Loan:</span><span class="sxs-lookup"><span data-stu-id="458f4-143">Add the following code above the Loan class definition:</span></span>

[!code-csharp[Loan class definition](../../../../../samples/snippets/csharp/serialization/Loan.cs#2)]

<span data-ttu-id="458f4-144"><xref:System.SerializableAttribute> indica al compilador que todo el contenido de la clase se puede conservar en un archivo.</span><span class="sxs-lookup"><span data-stu-id="458f4-144">The <xref:System.SerializableAttribute> tells the compiler that everything in the class can be persisted to a file.</span></span> <span data-ttu-id="458f4-145">El evento `PropertyChanged` no representa la parte del gráfico de objeto que se debe almacenar, de modo que no se debería serializar.</span><span class="sxs-lookup"><span data-stu-id="458f4-145">Because the `PropertyChanged` event does not represent part of the object graph that should be stored, it should not be serialized.</span></span> <span data-ttu-id="458f4-146">Si lo hace, se serializarían todos los objetos que estén asociados a ese evento.</span><span class="sxs-lookup"><span data-stu-id="458f4-146">Doing so would serialize all objects that are attached to that event.</span></span> <span data-ttu-id="458f4-147">Puede agregar <xref:System.NonSerializedAttribute> a la declaración de campo del controlador de eventos `PropertyChanged`.</span><span class="sxs-lookup"><span data-stu-id="458f4-147">You can add the <xref:System.NonSerializedAttribute> to the field declaration for the `PropertyChanged` event handler.</span></span>

[!code-csharp[Disable serialization for the event handler](../../../../../samples/snippets/csharp/serialization/Loan.cs#3)]

<span data-ttu-id="458f4-148">A partir de C# 7.3, los atributos se pueden asociar al campo de respaldo de una propiedad implementada automáticamente usando el valor de destino `field`.</span><span class="sxs-lookup"><span data-stu-id="458f4-148">Beginning with C# 7.3, you can attach attributes to the backing field of an auto-implemented property using the `field` target value.</span></span> <span data-ttu-id="458f4-149">El siguiente código agrega una propiedad `TimeLastLoaded` y la marca como no serializable:</span><span class="sxs-lookup"><span data-stu-id="458f4-149">The following code adds a `TimeLastLoaded` property and marks it as not serializable:</span></span>

[!code-csharp[Disable serialization for an auto-implemented property](../../../../../samples/snippets/csharp/serialization/Loan.cs#4)]

<span data-ttu-id="458f4-150">El siguiente paso consiste en agregar el código de serialización a la aplicación LoanApp.</span><span class="sxs-lookup"><span data-stu-id="458f4-150">The next step is to add the serialization code to the LoanApp application.</span></span> <span data-ttu-id="458f4-151">Para serializar la clase y escribirla en un archivo, usaremos los espacios de nombres <xref:System.IO> y <xref:System.Runtime.Serialization.Formatters.Binary>.</span><span class="sxs-lookup"><span data-stu-id="458f4-151">In order to serialize the class and write it to a file, you use the <xref:System.IO> and <xref:System.Runtime.Serialization.Formatters.Binary> namespaces.</span></span> <span data-ttu-id="458f4-152">Para evitar escribir los nombres completos, puede agregar referencias a los espacios de nombres necesarios, tal y como se muestra en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="458f4-152">To avoid typing the fully qualified names, you can add references to the necessary namespaces as shown in the following code:</span></span>

[!code-csharp[Adding namespaces for serialization](../../../../../samples/snippets/csharp/serialization/Program.cs#3)]

<span data-ttu-id="458f4-153">El siguiente paso es agregar código para deserializar el objeto del archivo cuando el objeto se crea.</span><span class="sxs-lookup"><span data-stu-id="458f4-153">The next step is to add code to deserialize the object from the file when the object is created.</span></span> <span data-ttu-id="458f4-154">Agregue una constante a la clase para el nombre de archivo de los datos serializados, tal y como se muestra en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="458f4-154">Add a constant to the class for the serialized data's file name as shown in the following code:</span></span>

[!code-csharp[Define the name of the saved file](../../../../../samples/snippets/csharp/serialization/Program.cs#4)]

<span data-ttu-id="458f4-155">Luego, agregue el siguiente código después de la línea que crea el objeto `TestLoan`:</span><span class="sxs-lookup"><span data-stu-id="458f4-155">Next, add the following code after the line that creates the `TestLoan` object:</span></span>

[!code-csharp[Read from a file if it exists](../../../../../samples/snippets/csharp/serialization/Program.cs#5)]

<span data-ttu-id="458f4-156">Primero hay que confirmar que el archivo existe.</span><span class="sxs-lookup"><span data-stu-id="458f4-156">You first must check that the file exists.</span></span> <span data-ttu-id="458f4-157">Si existe, cree una clase <xref:System.IO.Stream> para leer el archivo binario y una clase <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> para traducirlo.</span><span class="sxs-lookup"><span data-stu-id="458f4-157">If it exists, create a <xref:System.IO.Stream> class to read the binary file and a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> class to translate the file.</span></span> <span data-ttu-id="458f4-158">También necesita convertir del tipo de secuencia al tipo de objeto Loan.</span><span class="sxs-lookup"><span data-stu-id="458f4-158">You also need to convert from the stream type to the Loan object type.</span></span>

<span data-ttu-id="458f4-159">Luego, debemos agregar código para serializar la clase en un archivo.</span><span class="sxs-lookup"><span data-stu-id="458f4-159">Next you must add code to serialize the class to a file.</span></span> <span data-ttu-id="458f4-160">Agregue el siguiente código después del código existente en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="458f4-160">Add the following code after the existing code in the `Main` method:</span></span>

[!code-csharp[Save the existing Loan object](../../../../../samples/snippets/csharp/serialization/Program.cs#6)]

<span data-ttu-id="458f4-161">En este punto, podrá compilar y ejecutar la aplicación de nuevo.</span><span class="sxs-lookup"><span data-stu-id="458f4-161">At this point, you can again build and run the application.</span></span> <span data-ttu-id="458f4-162">La primera vez que se ejecuta, observe que el tipo de interés comienza en 7.5 y, después, pasa a 7.1.</span><span class="sxs-lookup"><span data-stu-id="458f4-162">The first time it runs, notice that the interest rates starts at 7.5, and then changes to 7.1.</span></span> <span data-ttu-id="458f4-163">Cierre la aplicación y, después, ejecútela de nuevo.</span><span class="sxs-lookup"><span data-stu-id="458f4-163">Close the application and then run it again.</span></span> <span data-ttu-id="458f4-164">Ahora, la aplicación muestra un mensaje que indica que se ha leído el archivo guardado y la tasa de interés es 7.1 incluso antes del código que la cambia.</span><span class="sxs-lookup"><span data-stu-id="458f4-164">Now, the application prints the message that it has read the saved file, and the interest rate is 7.1 even before the code that changes it.</span></span>

## <a name="see-also"></a><span data-ttu-id="458f4-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="458f4-165">See also</span></span>

- [<span data-ttu-id="458f4-166">Serialización (C#)</span><span class="sxs-lookup"><span data-stu-id="458f4-166">Serialization (C#)</span></span>](index.md)
- [<span data-ttu-id="458f4-167">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="458f4-167">C# Programming Guide</span></span>](../../index.md)
