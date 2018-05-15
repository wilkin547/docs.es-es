---
title: Validación del lado cliente (validación de los niveles de presentación)
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Validación del lado cliente (validación de los niveles de presentación)
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2057609c7f5c26668eac49cecce522135545e7dd
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a><span data-ttu-id="8e9c2-104">Validación del lado cliente (validación de los niveles de presentación)</span><span class="sxs-lookup"><span data-stu-id="8e9c2-104">Client-side validation (validation in the presentation layers)</span></span>

<span data-ttu-id="8e9c2-105">Incluso cuando el origen de verdad es el modelo del dominio y, en última instancia, debe tener validación en el nivel de modelo de dominio, la validación todavía puede controlarse en el nivel de modelo de dominio (servidor) y en el lado cliente.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-105">Even when the source of truth is the domain model and ultimately you must have validation at the domain model level, validation can still be handled at both the domain model level (server side) and the client side.</span></span>

<span data-ttu-id="8e9c2-106">La validación del lado cliente es una gran ventaja para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-106">Client-side validation is a great convenience for users.</span></span> <span data-ttu-id="8e9c2-107">Les permite ahorrar un tiempo que, de otro modo, pasarían esperando un viaje de ida y vuelta al servidor que podría devolver errores de validación.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-107">It saves time they would otherwise spend waiting for a round trip to the server that might return validation errors.</span></span> <span data-ttu-id="8e9c2-108">En términos comerciales, incluso unas pocas fracciones de segundos multiplicadas por cientos de veces al día suman una gran cantidad de tiempo, gastos y frustración.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-108">In business terms, even a few fractions of seconds multiplied hundreds of times each day adds up to a lot of time, expense, and frustration.</span></span> <span data-ttu-id="8e9c2-109">La validación inmediata y sencilla permite a los usuarios trabajar de forma más eficiente y generar una entrada y salida de datos de mayor calidad.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-109">Straightforward and immediate validation enables users to work more efficiently and produce better quality input and output.</span></span>

<span data-ttu-id="8e9c2-110">Al igual que el modelo de vista y el modelo de dominio son diferentes, la validación del modelo de vista y la validación del modelo de dominio podrían ser similares, pero servir para un propósito diferente.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-110">Just as the view model and the domain model are different, view model validation and domain model validation might be similar but serve a different purpose.</span></span> <span data-ttu-id="8e9c2-111">Si le preocupa DRY (el principio de No repetirse), tenga en cuenta que en este caso la reutilización del código también puede indicar el acoplamiento y en las aplicaciones empresariales es más importante no acoplar el lado servidor al lado cliente que seguir el principio DRY.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-111">If you are concerned about DRY (the Don’t Repeat Yourself principle), consider that in this case code reuse might also mean coupling, and in enterprise applications it is more important not to couple the server side to the client side than to follow the DRY principle.</span></span>

<span data-ttu-id="8e9c2-112">Incluso cuando se usa la validación del lado cliente, siempre debe validar sus comandos o DTO de entrada en el código de servidor, ya que las API de servidor son un posible vector de ataque.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-112">Even when using client-side validation, you should always validate your commands or input DTOs in server code, because the server APIs are a possible attack vector.</span></span> <span data-ttu-id="8e9c2-113">Normalmente, la mejor opción es hacer ambas cosas porque, si tiene una aplicación cliente, desde la perspectiva de la experiencia del usuario es mejor anticiparse y no permitir que el usuario escriba información no válida.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-113">Usually, doing both is your best bet because if you have a client application, from a UX perspective, it is best to be proactive and not allow the user to enter invalid information.</span></span>

<span data-ttu-id="8e9c2-114">Por tanto, normalmente se validan los ViewModels en el código del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-114">Therefore, in client-side code you typically validate the ViewModels.</span></span> <span data-ttu-id="8e9c2-115">También puede validar los DTO o los comandos de salida del cliente antes de enviarlos a los servicios.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-115">You could also validate the client output DTOs or commands before you send them to the services.</span></span>

<span data-ttu-id="8e9c2-116">La implementación de la validación del lado cliente depende del tipo de aplicación cliente que esté creando.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-116">The implementation of client-side validation depends on what kind of client application you are building.</span></span> <span data-ttu-id="8e9c2-117">Será diferente si valida los datos en una aplicación web de web MVC con la mayor parte del código en .NET, una aplicación web SPA en que la validación se codifique en JavaScript o TypeScript o una aplicación móvil codificada con Xamarin y C\#.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-117">It will be different if you are validating data in a web MVC web application with most of the code in .NET, an SPA web application with that validation being coded in JavaScript or TypeScript, or a mobile app coded with Xamarin and C\#.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8e9c2-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8e9c2-118">Additional resources</span></span>

### <a name="validation-in-xamarin-mobile-apps"></a><span data-ttu-id="8e9c2-119">Validación en aplicaciones móviles de Xamarin</span><span class="sxs-lookup"><span data-stu-id="8e9c2-119">Validation in Xamarin mobile apps</span></span>

-   <span data-ttu-id="8e9c2-120">**Validate Text Input and Show Errors (Validar la entrada de texto y mostrar errores)**
    [*https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span><span class="sxs-lookup"><span data-stu-id="8e9c2-120">**Validate Text Input and Show Errors**
[*https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span></span>

-   <span data-ttu-id="8e9c2-121">**Validation Callback (Devolución de llamada de validación)**
    [*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span><span class="sxs-lookup"><span data-stu-id="8e9c2-121">**Validation Callback**
[*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span></span>

### <a name="validation-in-aspnet-core-apps"></a><span data-ttu-id="8e9c2-122">Validación en aplicaciones ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8e9c2-122">Validation in ASP.NET Core apps</span></span>

-   <span data-ttu-id="8e9c2-123">**Rick Anderson. Adding validation (Adición de validación)**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="8e9c2-123">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a><span data-ttu-id="8e9c2-124">Validación en aplicaciones SPA Web (Angular 2, TypeScript, JavaScript)</span><span class="sxs-lookup"><span data-stu-id="8e9c2-124">Validation in SPA Web apps (Angular 2, TypeScript, JavaScript)</span></span>

-   <span data-ttu-id="8e9c2-125">**Ado Kukic. Angular 2 Form Validation (Validación de formularios de Angular 2)** **
    **[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span><span class="sxs-lookup"><span data-stu-id="8e9c2-125">**Ado Kukic. Angular 2 Form Validation** **
**[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span></span>

-   <span data-ttu-id="8e9c2-126">**Form Validation (Validación de formularios)**
    [*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span><span class="sxs-lookup"><span data-stu-id="8e9c2-126">**Form Validation**
[*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span></span>

-   <span data-ttu-id="8e9c2-127">**Validation (Validación).**</span><span class="sxs-lookup"><span data-stu-id="8e9c2-127">**Validation.**</span></span> <span data-ttu-id="8e9c2-128">Documentación de Breeze.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-128">Breeze documentation.</span></span>
    [*https://breeze.github.io/doc-js/validation.html*](https://breeze.github.io/doc-js/validation.html)

<span data-ttu-id="8e9c2-129">En resumen, estos son los conceptos más importantes en lo que respecta a la validación:</span><span class="sxs-lookup"><span data-stu-id="8e9c2-129">In summary, these are the most important concepts in regards to validation:</span></span>

-   <span data-ttu-id="8e9c2-130">Las entidades y los agregados deben aplicar su propia coherencia y ser "siempre válidos".</span><span class="sxs-lookup"><span data-stu-id="8e9c2-130">Entities and aggregates should enforce their own consistency and be "always valid”.</span></span> <span data-ttu-id="8e9c2-131">Las raíces agregadas son responsables de la coherencia de varias entidades dentro del mismo agregado.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-131">Aggregate roots are responsible for multi-entity consistency within the same aggregate.</span></span>

-   <span data-ttu-id="8e9c2-132">Si cree que una entidad debe entrar en un estado no válido, considere el uso de un modelo de objetos diferente: por ejemplo, usando un DTO temporal hasta que cree la entidad de dominio final.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-132">If you think that an entity needs to enter an invalid state, consider using a different object model—for example, using a temporary DTO until you create the final domain entity.</span></span>

-   <span data-ttu-id="8e9c2-133">Si necesita crear varios objetos relacionados, como un agregado, y solo son válidos una vez que todos ellos se han creado, considere la posibilidad de usar el patrón Factory.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-133">If you need to create several related objects, such as an aggregate, and they are only valid once all of them have been created, consider using the Factory pattern.</span></span>

-   <span data-ttu-id="8e9c2-134">Los marcos de validación son más útiles en niveles específicos, como el nivel de presentación o el nivel de aplicación/servicio, pero normalmente no en el nivel de modelo de dominio, ya que es necesario tomar una dependencia fuerte en un marco de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-134">Validation frameworks are best used in specific layers, such as the presentation layer or the application/service layer, but usually not in the domain model layer, because you would need to take a strong dependency on an infrastructure framework.</span></span>

-   <span data-ttu-id="8e9c2-135">En la mayoría de los casos, tener validación redundante en el lado cliente es adecuado, porque la aplicación puede ser proactiva.</span><span class="sxs-lookup"><span data-stu-id="8e9c2-135">In most of the cases, having redundant validation in the client side is good, because the application can be proactive.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="8e9c2-136">[Previous] (domain-model-layer-validations.md) [Next] (domain-events-design-implementation.md)</span><span class="sxs-lookup"><span data-stu-id="8e9c2-136">[Previous] (domain-model-layer-validations.md) [Next] (domain-events-design-implementation.md)</span></span>
