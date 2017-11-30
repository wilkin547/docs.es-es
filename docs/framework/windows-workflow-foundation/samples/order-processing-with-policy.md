---
title: Procesar pedidos con directiva
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66833724-dc36-4fad-86b0-59ffeaa3ba6a
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b479e6129cc5ba158549294acf25d4b8f71a3ff4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="order-processing-with-policy"></a><span data-ttu-id="ab07a-102">Procesar pedidos con directiva</span><span class="sxs-lookup"><span data-stu-id="ab07a-102">Order Processing with Policy</span></span>
<span data-ttu-id="ab07a-103">El ejemplo de directiva de procesamiento de orden muestra algunas de las características clave introducidas en [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] de Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="ab07a-103">The Order Processing Policy sample demonstrates some of the key features introduced in the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] of the Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="ab07a-104">La funcionalidad siguiente es nueva para el motor de reglas de WF:</span><span class="sxs-lookup"><span data-stu-id="ab07a-104">The following functionality is new for the WF rules engine:</span></span>  
  
-   <span data-ttu-id="ab07a-105">Admisión de sobrecarga del operador.</span><span class="sxs-lookup"><span data-stu-id="ab07a-105">Support for operator overloading.</span></span>  
  
-   <span data-ttu-id="ab07a-106">Compatibilidad para el operador `new`, permitiendo a los usuarios crear nuevos objetos y matrices a partir de las reglas de WF.</span><span class="sxs-lookup"><span data-stu-id="ab07a-106">Support for the `new` operator, allowing users to create new objects and arrays from WF rules.</span></span>  
  
-   <span data-ttu-id="ab07a-107">Compatibilidad para los métodos de extensión para que el usuario experimente llamando a métodos de extensión desde las reglas de WF compatibles con los estilos de codificación C#.</span><span class="sxs-lookup"><span data-stu-id="ab07a-107">Support for extension methods to make the user experience in calling extension methods from WF rules compatible with C# coding styles.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab07a-108">Este ejemplo necesita que [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] esté instalado para compilarse y ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="ab07a-108">This sample requires that [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] is installed to build and run.</span></span> [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]<span data-ttu-id="ab07a-109"> es necesario para abrir los archivos de proyecto y de solución.</span><span class="sxs-lookup"><span data-stu-id="ab07a-109"> is required to open the project and solution files.</span></span>  
  
 <span data-ttu-id="ab07a-110">El ejemplo muestra un proyecto `OrderProcessingPolicy` donde se introduce una orden de cliente, que está compuesta de una lista numerada de elementos disponibles, y un código postal.</span><span class="sxs-lookup"><span data-stu-id="ab07a-110">The sample demonstrates an `OrderProcessingPolicy` project in which a customer order, which consists of a numbered list of available items and a zip code, is entered.</span></span> <span data-ttu-id="ab07a-111">La orden se procesa correctamente si ambas entradas son correctas; de lo contrario, la directiva crea los objetos de error, utilizando un operador `+` sobrecargado y un método de extensión predefinido para informar al usuario de los errores.</span><span class="sxs-lookup"><span data-stu-id="ab07a-111">The order is processed successfully if both entries are correct; otherwise, the policy creates error objects, utilizing an overloaded `+` operator and a predefined extension method to inform the user of the errors.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="ab07a-112">métodos de extensión, vea [C# versión 3.0 especificación](http://go.microsoft.com/fwlink/?LinkId=95402).</span><span class="sxs-lookup"><span data-stu-id="ab07a-112"> extension methods, see [C# Version 3.0 Specification](http://go.microsoft.com/fwlink/?LinkId=95402).</span></span>  
  
 <span data-ttu-id="ab07a-113">El ejemplo consta de los proyectos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ab07a-113">The sample is comprised of the following projects:</span></span>  
  
-   `OrderErrorLibrary`  
  
     <span data-ttu-id="ab07a-114">`OrderErrorLibrary` es una biblioteca de clases que define las clases `OrderError` y `OrderErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="ab07a-114">The `OrderErrorLibrary` is a class library that defines `OrderError` and `OrderErrorCollection` classes.</span></span> <span data-ttu-id="ab07a-115">Se crea una instancia `OrderError` cuando se escribe una entrada no válida.</span><span class="sxs-lookup"><span data-stu-id="ab07a-115">An `OrderError` instance is created when an invalid input is entered.</span></span> <span data-ttu-id="ab07a-116">La biblioteca también proporciona un método de extensión en la clase `OrderErrorCollection` que genera la propiedad `ErrorText` en todos los objetos `OrderError` en `OrderErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="ab07a-116">The library also provides an extension method on the `OrderErrorCollection` class that outputs the `ErrorText` property on all `OrderError` objects in the `OrderErrorCollection`.</span></span>  
  
-   `OrderProcessingPolicy`  
  
     <span data-ttu-id="ab07a-117">El proyecto `OrderProcessingPolicy` es una aplicación de consola de WF que define una actividad `PolicyFromFile` única.</span><span class="sxs-lookup"><span data-stu-id="ab07a-117">The `OrderProcessingPolicy` project is a WF console application that defines a single `PolicyFromFile` activity.</span></span> <span data-ttu-id="ab07a-118">La actividad tiene las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="ab07a-118">The activity has the following rules:</span></span>  
  
    -   `invalidItemNum`  
  
         <span data-ttu-id="ab07a-119">Esta regla valida que el número del elemento esté entre 1 y 6, incluido.</span><span class="sxs-lookup"><span data-stu-id="ab07a-119">This rule validates that the item number is between 1 and 6, inclusive.</span></span> <span data-ttu-id="ab07a-120">Si el número del elemento está dentro del intervalo válido, la regla no hace nada (excepto imprimir en la consola).</span><span class="sxs-lookup"><span data-stu-id="ab07a-120">If the item number is within the valid range, the rule does nothing (other than printing to the console).</span></span> <span data-ttu-id="ab07a-121">Si el número del elemento no está entre 1 y 6, la regla `invalidItemNum` hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ab07a-121">If the item number is not between 1 and 6, the `invalidItemNum` rule does the following:</span></span>  
  
        1.  <span data-ttu-id="ab07a-122">Crea un nuevo objeto `OrderError`, pasándole el número del elemento introducido y establece las propiedades `ErrorText` y `CustomerName` en el objeto.</span><span class="sxs-lookup"><span data-stu-id="ab07a-122">Creates a new `OrderError` object, passing it the item number entered, and sets the `ErrorText` and `CustomerName` properties on the object.</span></span>  
  
        2.  <span data-ttu-id="ab07a-123">Crea un objeto `invalidItemNumErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="ab07a-123">Creates an `invalidItemNumErrorCollection` object.</span></span>  
  
        3.  <span data-ttu-id="ab07a-124">Agrega la instancia creada recientemente `OrderError` a `invalidItemNumErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="ab07a-124">Adds the newly-created `OrderError` instance to the `invalidItemNumErrorCollection`.</span></span>  
  
         <span data-ttu-id="ab07a-125">Esto muestra la compatibilidad para el operador `new`, con el que puede crear instancias de los objetos dentro de las reglas.</span><span class="sxs-lookup"><span data-stu-id="ab07a-125">This demonstrates support for the `new` operator, with which you can instantiate objects inside rules.</span></span>  
  
    -   `invalidZip`  
  
         <span data-ttu-id="ab07a-126">Esta regla valida que el código postal tiene 5 dígitos y que se sitúa dentro del intervalo 600 a 99998.</span><span class="sxs-lookup"><span data-stu-id="ab07a-126">This rule validates that the zip code has 5 digits, and is within the range 600 to 99998.</span></span> <span data-ttu-id="ab07a-127">Si el código postal está dentro del intervalo válido, la regla no hace nada (excepto imprimir en la consola).</span><span class="sxs-lookup"><span data-stu-id="ab07a-127">If the zip code is within the valid range, the rule does nothing (other than printing to the console).</span></span> <span data-ttu-id="ab07a-128">Si la longitud del código postal es menor que 5 o el código postal no está entre 00600 y 99998, la regla `invalidZip` hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ab07a-128">If the length of the zip code is less than 5, or the zip code is not between 00600 and 99998, the `invalidZip` rule does the following:</span></span>  
  
        1.  <span data-ttu-id="ab07a-129">Crea un objeto `OrderError`, pasándole el código postal introducido y establece las propiedades `ErrorText` y l`CustomerName` en el objeto.</span><span class="sxs-lookup"><span data-stu-id="ab07a-129">Creates an `OrderError` object, passing it the zip code entered, and sets the `ErrorText` and `CustomerName` properties on the object.</span></span>  
  
        2.  <span data-ttu-id="ab07a-130">Crea un objeto `invalidZipCodeErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="ab07a-130">Creates an `invalidZipCodeErrorCollection` object.</span></span>  
  
        3.  <span data-ttu-id="ab07a-131">Agrega la instancia creada recientemente `OrderError` a la `invalidZipCodeErrorCollection` creada recientemente.</span><span class="sxs-lookup"><span data-stu-id="ab07a-131">Adds the newly-created `OrderError` instance to the newly-created `invalidZipCodeErrorCollection`.</span></span>  
  
         <span data-ttu-id="ab07a-132">Esta regla muestra de nuevo la compatibilidad para el operador `new`, que le permite crear instancias de los objetos dentro de las reglas.</span><span class="sxs-lookup"><span data-stu-id="ab07a-132">This rule again demonstrates support for the `new` operator, which allows you to instantiate objects inside rules.</span></span>  
  
    -   `displayErrors`  
  
         <span data-ttu-id="ab07a-133">Esta regla comprueba si las dos reglas anteriores han agregado errores en los dos objetos `OrderErrorCollection``invalidItemNumErrorCollection` y `invalidIZipCodeErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="ab07a-133">This rule checks to see if there were any errors added by the previous two rules in the two `OrderErrorCollection` objects `invalidItemNumErrorCollection` and `invalidIZipCodeErrorCollection`.</span></span> <span data-ttu-id="ab07a-134">Si hay errores ( `invalidItemNumErrorCollection` o `invalidZipCodeErrorCollection` no es `null`), la regla hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ab07a-134">If there were errors (either `invalidItemNumErrorCollection` or `invalidZipCodeErrorCollection` is not `null`), the rule does the following:</span></span>  
  
        1.  <span data-ttu-id="ab07a-135">Llama a sobrecargado `+` operador que se va a copiar el contenido de `invalidItemNumErrorCollection` y `invalidZipCodeErrorCollection` a una `invalidOrdersCollection``OrderErrorCollection` instancia.</span><span class="sxs-lookup"><span data-stu-id="ab07a-135">Calls the overloaded `+` operator to copy the contents of `invalidItemNumErrorCollection` and `invalidZipCodeErrorCollection` to an `invalidOrdersCollection``OrderErrorCollection` instance.</span></span>  
  
        2.  <span data-ttu-id="ab07a-136">Llama al método de extensión `PrintOrderErrors` en `invalidOrdersCollection` y genera la propiedad `ErrorText` en todos los objetos `orderError` en `invalidOrdersCollection`.</span><span class="sxs-lookup"><span data-stu-id="ab07a-136">Calls the `PrintOrderErrors` extension method on `invalidOrdersCollection` and outputs the `ErrorText` property on all `orderError` objects in `invalidOrdersCollection`.</span></span>  
  
 <span data-ttu-id="ab07a-137">El operador `+` sobrecargado en `OrderErrorCollection` se define en la clase `OrderErrorCollection`, en el proyecto `OrderErrorLibrary`.</span><span class="sxs-lookup"><span data-stu-id="ab07a-137">The overloaded operator `+` on the `OrderErrorCollection` is defined in the `OrderErrorCollection` class, in the `OrderErrorLibrary` project.</span></span> <span data-ttu-id="ab07a-138">Toma dos objetos `OrderErrorCollection` y los combina en un objeto `OrderErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="ab07a-138">It takes two `OrderErrorCollection` objects and combines them into one `OrderErrorCollection` object.</span></span>  
  
 <span data-ttu-id="ab07a-139">El método de extensión `PrintOrderErrors` también se define en el proyecto `OrderErrorLibrary`.</span><span class="sxs-lookup"><span data-stu-id="ab07a-139">The `PrintOrderErrors` extension method is also defined in the `OrderErrorLibrary` project.</span></span> <span data-ttu-id="ab07a-140">Los métodos de extensión son una nueva característica de C# que permite a los programadores agregar nuevos métodos al contrato público de un tipo CLR existente, sin tener que derivar una clase del mismo o recompilar el tipo original.</span><span class="sxs-lookup"><span data-stu-id="ab07a-140">Extension methods are a new C# feature that enables developers to add new methods to the public contract of an existing CLR type, without having to derive a class from it or recompile the original type.</span></span>  
  
 <span data-ttu-id="ab07a-141">Al ejecutar el ejemplo se le pide que escriba un nombre, el número del elemento del elemento que se va a comprar y un código postal.</span><span class="sxs-lookup"><span data-stu-id="ab07a-141">When you run the sample you are prompted to enter a name, the item number of the item to be purchased, and a zip code.</span></span> <span data-ttu-id="ab07a-142">Las reglas definidas en la actividad de directiva comprueban a continuación esta información.</span><span class="sxs-lookup"><span data-stu-id="ab07a-142">This information is then verified by the rules defined in the policy activity.</span></span> <span data-ttu-id="ab07a-143">A continuación, puede ver un resultado de ejemplo del programa.</span><span class="sxs-lookup"><span data-stu-id="ab07a-143">The following is sample output from the program.</span></span>  
  
```  
Please enter your name: John  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 1  
  
Please enter your 5-Digit zip code: 98102  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Thank you for your order, it has been processed.  
  
Workflow Completed  
Another Order? (Y/N): y  
  
Please enter your name: Joel  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 8  
  
Please enter your 5-Digit zip code: 0000  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Your order contains the following error(s)  
  
Error: No item number found. Please choose an available item.  
Error: Invalid zip code. Please choose a zip code between 00600 and 99998.  
  
Workflow Completed  
Another Order? (Y/N): n  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ab07a-144">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ab07a-144">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ab07a-145">Abra el archivo de proyecto OrderProcessingPolicy.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab07a-145">Open the OrderProcessingPolicy.sln project file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="ab07a-146">Hay dos proyectos diferentes en la solución: `OrderErrorLibrary` y `OrderProcessingPolicy`.</span><span class="sxs-lookup"><span data-stu-id="ab07a-146">There are two different projects in the solution: `OrderErrorLibrary` and `OrderProcessingPolicy`.</span></span> <span data-ttu-id="ab07a-147">El proyecto `OrderProcessingPolicy` utiliza clases y métodos definidos en `OrderErrorLibrary`.</span><span class="sxs-lookup"><span data-stu-id="ab07a-147">The `OrderProcessingPolicy` project uses classes and methods defined in the `OrderErrorLibrary`.</span></span>  
  
3.  <span data-ttu-id="ab07a-148">Compile todos los proyectos.</span><span class="sxs-lookup"><span data-stu-id="ab07a-148">Build all projects.</span></span>  
  
4.  <span data-ttu-id="ab07a-149">Haga clic en **ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ab07a-149">Click **Run**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ab07a-150">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ab07a-150">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ab07a-151">Compruebe el siguiente directorio (predeterminado) antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="ab07a-151">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ab07a-152">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ab07a-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ab07a-153">Este ejemplo se encuentra en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="ab07a-153">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\OrderProcessingPolicy`  
  
## <a name="see-also"></a><span data-ttu-id="ab07a-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab07a-154">See Also</span></span>
