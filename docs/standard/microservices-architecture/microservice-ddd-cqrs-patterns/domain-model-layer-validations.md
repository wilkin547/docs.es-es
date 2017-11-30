---
title: "Diseñar las validaciones en el nivel de modelo de dominio"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Diseñar las validaciones en el nivel de modelo de dominio"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f4870d0568c3539f296bcb3f577291cb0250cfca
ms.sourcegitcommit: 62d3e3e74c1b7ffa927590012c0b9f87de1b0848
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2017
---
# <a name="designing-validations-in-the-domain-model-layer"></a><span data-ttu-id="ba077-104">Diseñar las validaciones en el nivel de modelo de dominio</span><span class="sxs-lookup"><span data-stu-id="ba077-104">Designing validations in the domain model layer</span></span>

<span data-ttu-id="ba077-105">En el DDD, reglas de validación pueden considerarse como invariables.</span><span class="sxs-lookup"><span data-stu-id="ba077-105">In DDD, validation rules can be thought as invariants.</span></span> <span data-ttu-id="ba077-106">La responsabilidad principal de un agregado es exigir las invariantes en todos los cambios de estado para todas las entidades dentro de ese agregado.</span><span class="sxs-lookup"><span data-stu-id="ba077-106">The main responsibility of an aggregate is to enforce invariants across state changes for all the entities within that aggregate.</span></span>

<span data-ttu-id="ba077-107">Las entidades de dominio deben ser siempre entidades válidas.</span><span class="sxs-lookup"><span data-stu-id="ba077-107">Domain entities should always be valid entities.</span></span> <span data-ttu-id="ba077-108">Hay un número determinado de invariables para un objeto que siempre debe ser true.</span><span class="sxs-lookup"><span data-stu-id="ba077-108">There are a certain number of invariants for an object that should always be true.</span></span> <span data-ttu-id="ba077-109">Por ejemplo, un objeto de elemento de pedido siempre debe tener una cantidad que debe ser un entero positivo, además de un nombre de artículo y precio.</span><span class="sxs-lookup"><span data-stu-id="ba077-109">For example, an order item object always has to have a quantity that must be a positive integer, plus an article name and price.</span></span> <span data-ttu-id="ba077-110">Por lo tanto, el cumplimiento de las invariantes es responsabilidad de las entidades de dominio (especialmente tratándose de la raíz agregada) y un objeto de entidad no debe ser capaz de existir sin necesidad de ser válido.</span><span class="sxs-lookup"><span data-stu-id="ba077-110">Therefore, invariants enforcement is the responsibility of the domain entities (especially of the aggregate root) and an entity object should not be able to exist without being valid.</span></span> <span data-ttu-id="ba077-111">Reglas invariables simplemente se expresan como contratos y las excepciones o las notificaciones se generan cuando se infringen.</span><span class="sxs-lookup"><span data-stu-id="ba077-111">Invariant rules are simply expressed as contracts, and exceptions or notifications are raised when they are violated.</span></span>

<span data-ttu-id="ba077-112">El razonamiento es que se producen muchos errores porque los objetos están en un estado en que nunca deberían haber estado.</span><span class="sxs-lookup"><span data-stu-id="ba077-112">The reasoning behind this is that many bugs occur because objects are in a state they should never have been in.</span></span> <span data-ttu-id="ba077-113">La siguiente es una buena explicación de Greg Young en un [discusión en línea](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span><span class="sxs-lookup"><span data-stu-id="ba077-113">The following is a good explanation from Greg Young in an [online discussion](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span></span>

<span data-ttu-id="ba077-114">Vamos a proponer que ahora tenemos un SendUserCreationEmailService que toma UserProfile... ¿cómo podemos se racionalizar en ese servicio que no sea nulo nombre?</span><span class="sxs-lookup"><span data-stu-id="ba077-114">Let's propose we now have a SendUserCreationEmailService that takes a UserProfile ... how can we rationalize in that service that Name is not null?</span></span> <span data-ttu-id="ba077-115">¿Se comprueba lo nuevo?</span><span class="sxs-lookup"><span data-stu-id="ba077-115">Do we check it again?</span></span> <span data-ttu-id="ba077-116">O con mayor probabilidad... simplemente no pierda tiempo para comprobar y "esperar para obtener la mejor": esperar a que alguien obtienes para validar antes de enviarlo a usted.</span><span class="sxs-lookup"><span data-stu-id="ba077-116">Or more likely ... you just don't bother to check and "hope for the best"—you hope that someone bothered to validate it before sending it to you.</span></span> <span data-ttu-id="ba077-117">Por supuesto, utilizar TDD una de las primeras pruebas que se deben escribir es que si se envían a un cliente con un nombre nulo que debe generar un error.</span><span class="sxs-lookup"><span data-stu-id="ba077-117">Of course, using TDD one of the first tests we should be writing is that if I send a customer with a null name that it should raise an error.</span></span> <span data-ttu-id="ba077-118">Pero una vez comience a escribir estos tipos de pruebas y otra vez sabemos... "esperar si nunca se permite nombre para convertirse en null no tenemos todas estas pruebas"</span><span class="sxs-lookup"><span data-stu-id="ba077-118">But once we start writing these kinds of tests over and over again we realize ... "wait if we never allowed name to become null we wouldn't have all of these tests"</span></span>

## <a name="implementing-validations-in-the-domain-model-layer"></a><span data-ttu-id="ba077-119">Implementación de validaciones en el nivel de modelo de dominio</span><span class="sxs-lookup"><span data-stu-id="ba077-119">Implementing validations in the domain model layer</span></span>

<span data-ttu-id="ba077-120">Validaciones normalmente se implementan en los constructores de la entidad de dominio o en los métodos que pueden actualizar la entidad.</span><span class="sxs-lookup"><span data-stu-id="ba077-120">Validations are usually implemented in domain entity constructors or in methods that can update the entity.</span></span> <span data-ttu-id="ba077-121">Hay varias maneras de implementar las validaciones, como datos de comprobación y generación de excepciones si se produce un error en la validación.</span><span class="sxs-lookup"><span data-stu-id="ba077-121">There are multiple ways to implement validations, such as verifying data and raising exceptions if the validation fails.</span></span> <span data-ttu-id="ba077-122">También hay patrones más avanzadas, como utilizar el modelo de especificación para validaciones y el patrón de notificación para devolver una colección de errores en lugar de devolver una excepción para cada validación mientras se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="ba077-122">There are also more advanced patterns such as using the Specification pattern for validations, and the Notification pattern to return a collection of errors instead of returning an exception for each validation as it occurs.</span></span>

### <a name="validating-conditions-and-throwing-exceptions"></a><span data-ttu-id="ba077-123">Validar las condiciones y producir excepciones</span><span class="sxs-lookup"><span data-stu-id="ba077-123">Validating conditions and throwing exceptions</span></span>

<span data-ttu-id="ba077-124">En el ejemplo de código siguiente se muestra el método más sencillo para la validación en una entidad del dominio lanza una excepción.</span><span class="sxs-lookup"><span data-stu-id="ba077-124">The following code example shows the simplest approach to validation in a domain entity by raising an exception.</span></span> <span data-ttu-id="ba077-125">En la tabla de referencias al final de esta sección puede ver vínculos a las implementaciones más avanzadas según los patrones que hemos analizado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ba077-125">In the references table at the end of this section you can see links to more advanced implementations based on the patterns we have discussed previously.</span></span>

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

<span data-ttu-id="ba077-126">Un ejemplo mejor sería demuestra que era necesario para asegurarse de que el estado interno no cambió o que se ha producido la de las mutaciones para un método.</span><span class="sxs-lookup"><span data-stu-id="ba077-126">A better example would demonstrate the need to ensure that either the internal state did not change, or that all the mutations for a method occurred.</span></span> <span data-ttu-id="ba077-127">Por ejemplo, la siguiente implementación dejaría el objeto en un estado no válido:</span><span class="sxs-lookup"><span data-stu-id="ba077-127">For example, the following implementation would leave the object in an invalid state:</span></span>

```csharp
public void SetAddress(string line1, string line2,
    string city, string state, int zip)
{
    _shipingAddress.line1 = line1 ?? throw new ...
    _shippingAddress.line2 = line2;
    _shippingAddress.city = city ?? throw new ...
    _shippingAddress.state = (IsValid(state) ? state : throw new …);
}
```

<span data-ttu-id="ba077-128">Si el valor del estado no es válido, la primera línea de dirección y la ciudad ya han cambiado.</span><span class="sxs-lookup"><span data-stu-id="ba077-128">If the value of the state is invalid, the first address line and the city have already been changed.</span></span> <span data-ttu-id="ba077-129">La dirección que puede que no sean válidos.</span><span class="sxs-lookup"><span data-stu-id="ba077-129">That might make the address invalid.</span></span>

<span data-ttu-id="ba077-130">Un enfoque similar puede usarse en el constructor de la entidad, cuando se genera una excepción para asegurarse de que la entidad es válido una vez que se crea.</span><span class="sxs-lookup"><span data-stu-id="ba077-130">A similar approach can be used in the entity’s constructor, raising an exception to make sure that the entity is valid once it is created.</span></span>

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a><span data-ttu-id="ba077-131">Uso de atributos de validación en el modelo en función de las anotaciones de datos</span><span class="sxs-lookup"><span data-stu-id="ba077-131">Using validation attributes in the model based on data annotations</span></span>

<span data-ttu-id="ba077-132">Otro enfoque consiste en utilizar atributos de validación en función de las anotaciones de datos.</span><span class="sxs-lookup"><span data-stu-id="ba077-132">Another approach is to use validation attributes based on data annotations.</span></span> <span data-ttu-id="ba077-133">Atributos de validación proporcionan una manera de configurar la validación del modelo, que es similar conceptualmente a la validación en los campos de tablas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="ba077-133">Validation attributes provide a way to configure model validation, which is similar conceptually to validation on fields in database tables.</span></span> <span data-ttu-id="ba077-134">Esto incluye las restricciones como la asignación de tipos de datos o campos obligatorios.</span><span class="sxs-lookup"><span data-stu-id="ba077-134">This includes constraints such as assigning data types or required fields.</span></span> <span data-ttu-id="ba077-135">Otros tipos de validación aplicar patrones a datos que se va a aplicar las reglas de negocios, como un número de tarjeta de crédito, número de teléfono o dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ba077-135">Other types of validation include applying patterns to data to enforce business rules, such as a credit card number, phone number, or email address.</span></span> <span data-ttu-id="ba077-136">Atributos de validación facilitan la tarea exigir requisitos.</span><span class="sxs-lookup"><span data-stu-id="ba077-136">Validation attributes make it easy to enforce requirements.</span></span>

<span data-ttu-id="ba077-137">Sin embargo, como se muestra en el código siguiente, este enfoque sería demasiado intrusivo en un modelo DDD, porque toma una dependencia en ModelState.IsValid de Microsoft.AspNetCore.Mvc.ModelState, que se debe llamar desde los controladores MVC.</span><span class="sxs-lookup"><span data-stu-id="ba077-137">However, as shown in the following code, this approach might be too intrusive in a DDD model, because it takes a dependency on ModelState.IsValid from Microsoft.AspNetCore.Mvc.ModelState, which you must call from your MVC controllers.</span></span> <span data-ttu-id="ba077-138">La validación del modelo se produce antes de cada acción de controlador que se invoca y es responsabilidad del método de controlador para inspeccionar el resultado de llamada ModelState.IsValid y reaccionar de manera apropiada.</span><span class="sxs-lookup"><span data-stu-id="ba077-138">The model validation occurs prior to each controller action being invoked, and it is the controller method’s responsibility to inspect the result of calling ModelState.IsValid and react appropriately.</span></span> <span data-ttu-id="ba077-139">La decisión de usar depende de cómo estrechamente desea que el modelo con el que la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="ba077-139">The decision to use it depends on how tightly coupled you want the model to be with that infrastructure.</span></span>

```csharp
using System.ComponentModel.DataAnnotations;
// Other using statements ...
// Entity is a custom base class which has the ID
public class Product : Entity
{
    [Required]
    [StringLength(100)]
    public string Title { get; private set; }

    [Required]
    [Range(0, 999.99)]
    public decimal Price { get; private set; }

    [Required]
    [VintageProduct(1970)]
    [DataType(DataType.Date)]
    public DateTime ReleaseDate { get; private set; }

    [Required]
    [StringLength(1000)]
    public string Description { get; private set; }

    // Constructor...
    // Additional methods for entity logic and constructor...
}
```

<span data-ttu-id="ba077-140">Sin embargo, desde un punto de vista DDD, el modelo de dominio es mejor guardar eficiente con el uso de excepciones en métodos de comportamiento de la entidad, o mediante la implementación de los patrones de especificación y notificación para exigir reglas de validación.</span><span class="sxs-lookup"><span data-stu-id="ba077-140">However, from a DDD point of view, the domain model is best kept lean with the use of exceptions in your entity’s behavior methods, or by implementing the Specification and Notification patterns to enforce validation rules.</span></span> <span data-ttu-id="ba077-141">Marcos de validación como anotaciones de datos en ASP.NET Core o ningún otro marco de validación como FluentValidation llevan un requisito para invocar el marco de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ba077-141">Validation frameworks like data annotations in ASP.NET Core or any other validation frameworks like FluentValidation carry a requirement to invoke the application framework.</span></span> <span data-ttu-id="ba077-142">Por ejemplo, al llamar al método ModelState.IsValid en las anotaciones de datos, debe invocar controladores de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ba077-142">For example, when calling the ModelState.IsValid method in data annotations, you need to invoke ASP.NET controllers.</span></span>

<span data-ttu-id="ba077-143">Puede tener sentido usar anotaciones de datos en el nivel de aplicación en las clases de ViewModel (en lugar de las entidades de dominio) que acepta datos proporcionados, para permitir la validación del modelo dentro de la capa de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="ba077-143">It can make sense to use data annotations at the application layer in ViewModel classes (instead of domain entities) that will accept input, to allow for model validation within the UI layer.</span></span> <span data-ttu-id="ba077-144">Sin embargo, esto no debería realizarse en la exclusión de validación en el modelo de dominio.</span><span class="sxs-lookup"><span data-stu-id="ba077-144">However, this should not be done at the exclusion of validation within the domain model.</span></span>

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a><span data-ttu-id="ba077-145">Validar entidades al implementar el patrón de especificación y la notificación</span><span class="sxs-lookup"><span data-stu-id="ba077-145">Validating entities by implementing the Specification pattern and the Notification pattern</span></span>

<span data-ttu-id="ba077-146">Por último, un enfoque más elaborado para implementar las validaciones en el modelo de dominio es al implementar el patrón de especificación junto con el patrón de notificación, como se explica en algunos de los recursos adicionales que se muestra más adelante.</span><span class="sxs-lookup"><span data-stu-id="ba077-146">Finally, a more elaborate approach to implementing validations in the domain model is by implementing the Specification pattern in conjunction with the Notification pattern, as explained in some of the additional resources listed later.</span></span>

<span data-ttu-id="ba077-147">Merece la pena mencionar que también puede usar solo uno de esos patrones, por ejemplo, validación manual con las instrucciones de control, pero utilizando el modelo de notificación de la pila y devolver una lista de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="ba077-147">It is worth mentioning that you can also use just one of those patterns—for example, validating manually with control statements, but using the Notification pattern to stack and return a list of validation errors.</span></span>

### <a name="using-deferred-validation-in-the-domain"></a><span data-ttu-id="ba077-148">Usar validación diferida en el dominio</span><span class="sxs-lookup"><span data-stu-id="ba077-148">Using deferred validation in the domain</span></span>

<span data-ttu-id="ba077-149">Hay varios enfoques para tratar con aplazada validaciones en el dominio.</span><span class="sxs-lookup"><span data-stu-id="ba077-149">There are various approaches to deal with deferred validations in the domain.</span></span> <span data-ttu-id="ba077-150">En su libro [Implementing Domain-Driven diseño](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon describe estas opciones en la sección sobre la validación.</span><span class="sxs-lookup"><span data-stu-id="ba077-150">In his book [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon discusses these in the section on validation.</span></span>

### <a name="two-step-validation"></a><span data-ttu-id="ba077-151">Validación de dos pasos</span><span class="sxs-lookup"><span data-stu-id="ba077-151">Two-step validation</span></span>

<span data-ttu-id="ba077-152">Considere también la validación de dos pasos.</span><span class="sxs-lookup"><span data-stu-id="ba077-152">Also consider two-step validation.</span></span> <span data-ttu-id="ba077-153">Utilizar la validación de nivel de campo en la validación de nivel de dominio dentro de las entidades y los objetos de transferencia de comandos datos (dto).</span><span class="sxs-lookup"><span data-stu-id="ba077-153">Use field-level validation on your command Data Transfer Objects (DTOs) and domain-level validation inside your entities.</span></span> <span data-ttu-id="ba077-154">Para ello, puede devolver un objeto de resultado en su lugar, las excepciones para que resulten más fáciles de tratar los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="ba077-154">You can do this by returning a result object instead exceptions in order to make it easier to deal with the validation errors.</span></span>

<span data-ttu-id="ba077-155">Usar la validación de campos con las anotaciones de datos, por ejemplo, no duplica la definición de validación.</span><span class="sxs-lookup"><span data-stu-id="ba077-155">Using field validation with data annotations, for example, you do not duplicate the validation definition.</span></span> <span data-ttu-id="ba077-156">Sin embargo, la ejecución, puede ser servidor y cliente en el caso de Dto (comandos y ViewModels, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="ba077-156">The execution, though, can be both server-side and client-side in the case of DTOs (commands and ViewModels, for instance).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ba077-157">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ba077-157">Additional resources</span></span>

-   <span data-ttu-id="ba077-158">**Rachel Appel. Introducción a la validación del modelo en MVC de ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span><span class="sxs-lookup"><span data-stu-id="ba077-158">**Rachel Appel. Introduction to model validation in ASP.NET Core MVC**
[*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span></span>

-   <span data-ttu-id="ba077-159">**Rick Anderson. Agregar validación**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="ba077-159">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

-   <span data-ttu-id="ba077-160">**Martin Fowler. Reemplazar producir excepciones con notificación de validaciones**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span><span class="sxs-lookup"><span data-stu-id="ba077-160">**Martin Fowler. Replacing Throwing Exceptions with Notification in Validations**
[*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span></span>

-   <span data-ttu-id="ba077-161">**Especificación y patrones de notificación**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span><span class="sxs-lookup"><span data-stu-id="ba077-161">**Specification and Notification Patterns**
[*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span></span>

-   <span data-ttu-id="ba077-162">**Lev Gorodinski. Validación de diseño basado en dominio (DDD)**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span><span class="sxs-lookup"><span data-stu-id="ba077-162">**Lev Gorodinski. Validation in Domain-Driven Design (DDD)**
[*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span></span>

-   <span data-ttu-id="ba077-163">**Colin conector. Validación del modelo de dominio**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span><span class="sxs-lookup"><span data-stu-id="ba077-163">**Colin Jack. Domain Model Validation**
[*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span></span>

-   <span data-ttu-id="ba077-164">**Jimmy Bogard. Validación en un mundo DDD**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span><span class="sxs-lookup"><span data-stu-id="ba077-164">**Jimmy Bogard. Validation in a DDD world**
[*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="ba077-165">[Anterior] (enumeración-clases-over-enum-types.md) [siguiente] (validation.md de lado de cliente)</span><span class="sxs-lookup"><span data-stu-id="ba077-165">[Previous] (enumeration-classes-over-enum-types.md) [Next] (client-side-validation.md)</span></span>
