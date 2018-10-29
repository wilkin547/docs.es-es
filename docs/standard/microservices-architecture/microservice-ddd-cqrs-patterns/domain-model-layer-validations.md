---
title: Diseñar las validaciones en el nivel de modelo de dominio
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Diseñar las validaciones en el nivel de modelo de dominio
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 6ff325bb062da2ebff815fc847d2247707a0bf7f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188058"
---
# <a name="designing-validations-in-the-domain-model-layer"></a><span data-ttu-id="46584-103">Diseñar las validaciones en el nivel de modelo de dominio</span><span class="sxs-lookup"><span data-stu-id="46584-103">Designing validations in the domain model layer</span></span>

<span data-ttu-id="46584-104">En el diseño guiado por el dominio (DDD), las reglas de validación se pueden considerar invariables.</span><span class="sxs-lookup"><span data-stu-id="46584-104">In DDD, validation rules can be thought as invariants.</span></span> <span data-ttu-id="46584-105">La responsabilidad principal de un agregado es aplicar invariables en todos los cambios de estado para todas las entidades de ese agregado.</span><span class="sxs-lookup"><span data-stu-id="46584-105">The main responsibility of an aggregate is to enforce invariants across state changes for all the entities within that aggregate.</span></span>

<span data-ttu-id="46584-106">Las entidades de dominio siempre deben ser entidades válidas.</span><span class="sxs-lookup"><span data-stu-id="46584-106">Domain entities should always be valid entities.</span></span> <span data-ttu-id="46584-107">Hay un número determinado de invariables para un objeto que siempre deben ser verdaderas.</span><span class="sxs-lookup"><span data-stu-id="46584-107">There are a certain number of invariants for an object that should always be true.</span></span> <span data-ttu-id="46584-108">Por ejemplo, un objeto de un elemento de pedido siempre debe tener una cantidad que debe constar de un entero positivo, un nombre de artículo y un precio.</span><span class="sxs-lookup"><span data-stu-id="46584-108">For example, an order item object always has to have a quantity that must be a positive integer, plus an article name and price.</span></span> <span data-ttu-id="46584-109">Por lo tanto, la aplicación de invariables es responsabilidad de las entidades de dominio (en especial de la raíz agregada) y un objeto de entidad no debería poder existir si no es válido.</span><span class="sxs-lookup"><span data-stu-id="46584-109">Therefore, invariants enforcement is the responsibility of the domain entities (especially of the aggregate root) and an entity object should not be able to exist without being valid.</span></span> <span data-ttu-id="46584-110">Las reglas invariables se expresan como contratos y, si se infringen, se generan excepciones o notificaciones.</span><span class="sxs-lookup"><span data-stu-id="46584-110">Invariant rules are simply expressed as contracts, and exceptions or notifications are raised when they are violated.</span></span>

<span data-ttu-id="46584-111">El razonamiento es que se producen muchos errores porque los objetos tienen un estado que no deberían tener nunca.</span><span class="sxs-lookup"><span data-stu-id="46584-111">The reasoning behind this is that many bugs occur because objects are in a state they should never have been in.</span></span> <span data-ttu-id="46584-112">A continuación se muestra una buena explicación de Greg Young, publicada en un [debate en línea](https://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span><span class="sxs-lookup"><span data-stu-id="46584-112">The following is a good explanation from Greg Young in an [online discussion](https://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span></span>

<span data-ttu-id="46584-113">Ahora imaginémonos que tenemos un SendUserCreationEmailService que toma un UserProfile… ¿Cómo podemos justificar en ese servicio que Name no es nulo?</span><span class="sxs-lookup"><span data-stu-id="46584-113">Let's propose we now have a SendUserCreationEmailService that takes a UserProfile ... how can we rationalize in that service that Name is not null?</span></span> <span data-ttu-id="46584-114">¿Lo volvemos a comprobar?</span><span class="sxs-lookup"><span data-stu-id="46584-114">Do we check it again?</span></span> <span data-ttu-id="46584-115">O lo que es más probable: no se molesta en comprobarlo y "espera lo mejor" (espera que alguien se haya molestado en validarlo antes de enviárselo).</span><span class="sxs-lookup"><span data-stu-id="46584-115">Or more likely ... you just don't bother to check and "hope for the best"—you hope that someone bothered to validate it before sending it to you.</span></span> <span data-ttu-id="46584-116">Por supuesto, si usamos TDD, una de las primeras pruebas que deberíamos escribir es que si, al enviar un cliente con un nombre nulo, se generaría un error.</span><span class="sxs-lookup"><span data-stu-id="46584-116">Of course, using TDD one of the first tests we should be writing is that if I send a customer with a null name that it should raise an error.</span></span> <span data-ttu-id="46584-117">Pero una vez que comenzamos a escribir estos tipos de pruebas una y otra vez nos damos cuenta de que… "Espera, si no hubiéramos dejado que Name fuera nulo, no tendríamos todas estas pruebas".</span><span class="sxs-lookup"><span data-stu-id="46584-117">But once we start writing these kinds of tests over and over again we realize ... "wait if we never allowed name to become null we wouldn't have all of these tests"</span></span>

## <a name="implementing-validations-in-the-domain-model-layer"></a><span data-ttu-id="46584-118">Implementar las validaciones en el nivel de modelo de dominio</span><span class="sxs-lookup"><span data-stu-id="46584-118">Implementing validations in the domain model layer</span></span>

<span data-ttu-id="46584-119">Las validaciones se suelen implementar en constructores de entidad de dominio o en métodos que pueden actualizar la entidad.</span><span class="sxs-lookup"><span data-stu-id="46584-119">Validations are usually implemented in domain entity constructors or in methods that can update the entity.</span></span> <span data-ttu-id="46584-120">Hay varias maneras de implementar las validaciones, como la comprobación de los datos y la generación de excepciones si se produce un error en la validación.</span><span class="sxs-lookup"><span data-stu-id="46584-120">There are multiple ways to implement validations, such as verifying data and raising exceptions if the validation fails.</span></span> <span data-ttu-id="46584-121">También hay patrones más avanzados, como el uso del patrón de especificación para las validaciones y el patrón de notificación para devolver una colección de errores en lugar de devolver una excepción para cada validación mientras se produce.</span><span class="sxs-lookup"><span data-stu-id="46584-121">There are also more advanced patterns such as using the Specification pattern for validations, and the Notification pattern to return a collection of errors instead of returning an exception for each validation as it occurs.</span></span>

### <a name="validating-conditions-and-throwing-exceptions"></a><span data-ttu-id="46584-122">Validar condiciones y generar excepciones</span><span class="sxs-lookup"><span data-stu-id="46584-122">Validating conditions and throwing exceptions</span></span>

<span data-ttu-id="46584-123">En el siguiente ejemplo de código se muestra el método de validación más sencillo en una entidad de dominio mediante la generación de una excepción.</span><span class="sxs-lookup"><span data-stu-id="46584-123">The following code example shows the simplest approach to validation in a domain entity by raising an exception.</span></span> <span data-ttu-id="46584-124">En la tabla de referencias que encontrará al final de esta sección puede ver vínculos a implementaciones más avanzadas según los patrones que hemos analizado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="46584-124">In the references table at the end of this section you can see links to more advanced implementations based on the patterns we have discussed previously.</span></span>

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

<span data-ttu-id="46584-125">Un ejemplo mejor demostraría la necesidad de garantizar que el estado interno no varió o que se produjeron todas las mutaciones de un método.</span><span class="sxs-lookup"><span data-stu-id="46584-125">A better example would demonstrate the need to ensure that either the internal state did not change, or that all the mutations for a method occurred.</span></span> <span data-ttu-id="46584-126">Por ejemplo, la siguiente implementación dejaría el objeto en un estado no válido:</span><span class="sxs-lookup"><span data-stu-id="46584-126">For example, the following implementation would leave the object in an invalid state:</span></span>

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

<span data-ttu-id="46584-127">Si el valor del estado no es válido, la primera línea de dirección y la ciudad ya se han cambiado,</span><span class="sxs-lookup"><span data-stu-id="46584-127">If the value of the state is invalid, the first address line and the city have already been changed.</span></span> <span data-ttu-id="46584-128">lo cual podría invalidar la dirección.</span><span class="sxs-lookup"><span data-stu-id="46584-128">That might make the address invalid.</span></span>

<span data-ttu-id="46584-129">Se puede aplicar un enfoque similar en el constructor de la entidad, generando una excepción para garantizar que la entidad sea válida una vez creada.</span><span class="sxs-lookup"><span data-stu-id="46584-129">A similar approach can be used in the entity’s constructor, raising an exception to make sure that the entity is valid once it is created.</span></span>

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a><span data-ttu-id="46584-130">Usar atributos de validación en el modelo en función de las anotaciones de datos</span><span class="sxs-lookup"><span data-stu-id="46584-130">Using validation attributes in the model based on data annotations</span></span>

<span data-ttu-id="46584-131">Otro enfoque consiste en usar atributos de validación en función de las anotaciones de datos.</span><span class="sxs-lookup"><span data-stu-id="46584-131">Another approach is to use validation attributes based on data annotations.</span></span> <span data-ttu-id="46584-132">Los atributos de validación permiten configurar la validación del modelo, que conceptualmente es similar a la validación en campos de tablas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="46584-132">Validation attributes provide a way to configure model validation, which is similar conceptually to validation on fields in database tables.</span></span> <span data-ttu-id="46584-133">Esto incluye las restricciones, como la asignación de tipos de datos o los campos obligatorios.</span><span class="sxs-lookup"><span data-stu-id="46584-133">This includes constraints such as assigning data types or required fields.</span></span> <span data-ttu-id="46584-134">Entre otros tipos de validación se encuentran el de aplicar patrones a los datos para aplicar reglas de negocio, como números de tarjetas de crédito, números de teléfono o direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="46584-134">Other types of validation include applying patterns to data to enforce business rules, such as a credit card number, phone number, or email address.</span></span> <span data-ttu-id="46584-135">Los atributos de validación facilitan la aplicación de requisitos.</span><span class="sxs-lookup"><span data-stu-id="46584-135">Validation attributes make it easy to enforce requirements.</span></span>

<span data-ttu-id="46584-136">Pero, como se muestra en el código siguiente, este enfoque resultaría demasiado invasivo en un modelo DDD, porque toma una dependencia en ModelState.IsValid de Microsoft.AspNetCore.Mvc.ModelState, al que se debe llamar desde los controladores de MVC.</span><span class="sxs-lookup"><span data-stu-id="46584-136">However, as shown in the following code, this approach might be too intrusive in a DDD model, because it takes a dependency on ModelState.IsValid from Microsoft.AspNetCore.Mvc.ModelState, which you must call from your MVC controllers.</span></span> <span data-ttu-id="46584-137">La validación del modelo tiene lugar antes de cada acción de controlador que se invoca, y es responsabilidad del método del controlador inspeccionar el resultado de la llamada a ModelState.IsValid y reaccionar de manera apropiada.</span><span class="sxs-lookup"><span data-stu-id="46584-137">The model validation occurs prior to each controller action being invoked, and it is the controller method’s responsibility to inspect the result of calling ModelState.IsValid and react appropriately.</span></span> <span data-ttu-id="46584-138">La decisión de usarlo depende del grado de asociación que quiere que tenga el modelo con esa infraestructura.</span><span class="sxs-lookup"><span data-stu-id="46584-138">The decision to use it depends on how tightly coupled you want the model to be with that infrastructure.</span></span>

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

<span data-ttu-id="46584-139">Pero desde la óptica del DDD, el modelo de dominio se ajusta mejor con el uso de excepciones en los métodos de comportamiento de la entidad o con la implementación de los patrones de especificación y notificación para aplicar reglas de validación.</span><span class="sxs-lookup"><span data-stu-id="46584-139">However, from a DDD point of view, the domain model is best kept lean with the use of exceptions in your entity’s behavior methods, or by implementing the Specification and Notification patterns to enforce validation rules.</span></span> <span data-ttu-id="46584-140">Los marcos de validación, como las anotaciones de datos en ASP.NET Core, o cualquier otro marco de validación como FluentValidation incluyen un requisito para invocar el marco de trabajo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="46584-140">Validation frameworks like data annotations in ASP.NET Core or any other validation frameworks like FluentValidation carry a requirement to invoke the application framework.</span></span> <span data-ttu-id="46584-141">Por ejemplo, al llamar al método ModelState.IsValid en las anotaciones de datos, debe invocar controladores de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="46584-141">For example, when calling the ModelState.IsValid method in data annotations, you need to invoke ASP.NET controllers.</span></span>

<span data-ttu-id="46584-142">Puede resultar lógico usar anotaciones de datos en el nivel de aplicación en las clases ViewModel (en lugar de hacerlo en las entidades de dominio) que aceptarán la entrada a fin de permitirlas para la validación del modelo en la capa de la interfaz de usuario,</span><span class="sxs-lookup"><span data-stu-id="46584-142">It can make sense to use data annotations at the application layer in ViewModel classes (instead of domain entities) that will accept input, to allow for model validation within the UI layer.</span></span> <span data-ttu-id="46584-143">pero no se debería hacer en la exclusión de validación dentro del modelo de dominio.</span><span class="sxs-lookup"><span data-stu-id="46584-143">However, this should not be done at the exclusion of validation within the domain model.</span></span>

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a><span data-ttu-id="46584-144">Validar entidades implementando el patrón de especificación y el patrón de notificación</span><span class="sxs-lookup"><span data-stu-id="46584-144">Validating entities by implementing the Specification pattern and the Notification pattern</span></span>

<span data-ttu-id="46584-145">Por último, un enfoque más elaborado para implementar validaciones en el modelo de dominio consiste en implementar el patrón de especificación junto con el patrón de notificación, como se explica en algunos de los recursos adicionales que se muestran más adelante.</span><span class="sxs-lookup"><span data-stu-id="46584-145">Finally, a more elaborate approach to implementing validations in the domain model is by implementing the Specification pattern in conjunction with the Notification pattern, as explained in some of the additional resources listed later.</span></span>

<span data-ttu-id="46584-146">Merece la pena mencionar que también se puede usar solo uno de estos patrones (por ejemplo, validándolo manualmente con instrucciones de control, pero usando el patrón de notificación para apilar y devolver una lista de errores de validación).</span><span class="sxs-lookup"><span data-stu-id="46584-146">It is worth mentioning that you can also use just one of those patterns—for example, validating manually with control statements, but using the Notification pattern to stack and return a list of validation errors.</span></span>

### <a name="using-deferred-validation-in-the-domain"></a><span data-ttu-id="46584-147">Usar la validación diferida en el dominio</span><span class="sxs-lookup"><span data-stu-id="46584-147">Using deferred validation in the domain</span></span>

<span data-ttu-id="46584-148">Hay varios métodos para tratar las validaciones diferidas en el dominio.</span><span class="sxs-lookup"><span data-stu-id="46584-148">There are various approaches to deal with deferred validations in the domain.</span></span> <span data-ttu-id="46584-149">En su libro [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577) (Implementación del diseño guiado por el dominio), Vaughn Vernon habla de ellos en la sección sobre la validación.</span><span class="sxs-lookup"><span data-stu-id="46584-149">In his book [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon discusses these in the section on validation.</span></span>

### <a name="two-step-validation"></a><span data-ttu-id="46584-150">Validación en dos pasos</span><span class="sxs-lookup"><span data-stu-id="46584-150">Two-step validation</span></span>

<span data-ttu-id="46584-151">Plantéese también usar la validación en dos pasos.</span><span class="sxs-lookup"><span data-stu-id="46584-151">Also consider two-step validation.</span></span> <span data-ttu-id="46584-152">Use la validación de nivel de campo en los objetos de transferencia de datos (DTO) de comandos y la validación de nivel de dominio dentro de las entidades.</span><span class="sxs-lookup"><span data-stu-id="46584-152">Use field-level validation on your command Data Transfer Objects (DTOs) and domain-level validation inside your entities.</span></span> <span data-ttu-id="46584-153">Para ello, puede devolver un objeto de resultado en vez de excepciones para que resulte más fácil tratar los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="46584-153">You can do this by returning a result object instead exceptions in order to make it easier to deal with the validation errors.</span></span>

<span data-ttu-id="46584-154">Si usa la validación de campos con anotaciones de datos, por ejemplo, no se duplica la definición de validación.</span><span class="sxs-lookup"><span data-stu-id="46584-154">Using field validation with data annotations, for example, you do not duplicate the validation definition.</span></span> <span data-ttu-id="46584-155">Pero la ejecución puede ser del lado servidor y del lado cliente en el caso de los DTO (comandos y ViewModels, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="46584-155">The execution, though, can be both server-side and client-side in the case of DTOs (commands and ViewModels, for instance).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="46584-156">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="46584-156">Additional resources</span></span>

-   <span data-ttu-id="46584-157">**Rachel Appel. Introducción a la validación de modelos en ASP.NET Core MVC**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span><span class="sxs-lookup"><span data-stu-id="46584-157">**Rachel Appel. Introduction to model validation in ASP.NET Core MVC**
[*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span></span>

-   <span data-ttu-id="46584-158">**Rick Anderson. Adding validation (Adición de validación)**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="46584-158">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

-   <span data-ttu-id="46584-159">**Martin Fowler. Replacing Throwing Exceptions with Notification in Validations (Reemplazar el inicio de excepciones por notificaciones en validaciones)**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span><span class="sxs-lookup"><span data-stu-id="46584-159">**Martin Fowler. Replacing Throwing Exceptions with Notification in Validations**
[*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span></span>

-   <span data-ttu-id="46584-160">**Specification and Notification Patterns (Patrones de especificación y notificación)**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span><span class="sxs-lookup"><span data-stu-id="46584-160">**Specification and Notification Patterns**
[*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span></span>

-   <span data-ttu-id="46584-161">**Lev Gorodinski. Validation in Domain-Driven Design (DDD) (Validación en diseños guiados por dominio)**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span><span class="sxs-lookup"><span data-stu-id="46584-161">**Lev Gorodinski. Validation in Domain-Driven Design (DDD)**
[*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span></span>

-   <span data-ttu-id="46584-162">**Colin Jack. Domain Model Validation (Validación de modelos de dominio)**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span><span class="sxs-lookup"><span data-stu-id="46584-162">**Colin Jack. Domain Model Validation**
[*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span></span>

-   <span data-ttu-id="46584-163">**Jimmy Bogard. Validation in a DDD world (Validación en un mundo de diseños guiados por dominio)**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span><span class="sxs-lookup"><span data-stu-id="46584-163">**Jimmy Bogard. Validation in a DDD world**
[*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="46584-164">[Anterior](enumeration-classes-over-enum-types.md)
[Siguiente](client-side-validation.md)</span><span class="sxs-lookup"><span data-stu-id="46584-164">[Previous](enumeration-classes-over-enum-types.md)
[Next](client-side-validation.md)</span></span>
