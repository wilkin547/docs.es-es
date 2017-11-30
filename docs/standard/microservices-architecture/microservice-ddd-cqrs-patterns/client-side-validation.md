---
title: "Validación del lado cliente (validación de los niveles de presentación)"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Validación del lado cliente (validación de los niveles de presentación)"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: db88a3b5c95afdc8d5a20094105f1f5991483ed6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a><span data-ttu-id="3f796-104">Validación del lado cliente (validación de los niveles de presentación)</span><span class="sxs-lookup"><span data-stu-id="3f796-104">Client-side validation (validation in the presentation layers)</span></span>

<span data-ttu-id="3f796-105">Incluso cuando el origen de verdad es el modelo de dominio y en última instancia debe tener validación en el nivel de modelo de dominio, validación todavía puede controlarse en el nivel de modelo de dominio (servidor) y el lado del cliente.</span><span class="sxs-lookup"><span data-stu-id="3f796-105">Even when the source of truth is the domain model and ultimately you must have validation at the domain model level, validation can still be handled at both the domain model level (server side) and the client side.</span></span>

<span data-ttu-id="3f796-106">Validación del lado cliente es una gran ventaja para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3f796-106">Client-side validation is a great convenience for users.</span></span> <span data-ttu-id="3f796-107">Ahorra tiempo en caso contrario, se gastan esperando de ida y vuelta al servidor que se produzcan errores de validación.</span><span class="sxs-lookup"><span data-stu-id="3f796-107">It saves time they would otherwise spend waiting for a round trip to the server that might return validation errors.</span></span> <span data-ttu-id="3f796-108">En términos comerciales, incluso unos fracciones de segundos multiplicados cientos de veces que cada día se agrega a una gran cantidad de tiempo y gastos, frustración.</span><span class="sxs-lookup"><span data-stu-id="3f796-108">In business terms, even a few fractions of seconds multiplied hundreds of times each day adds up to a lot of time, expense, and frustration.</span></span> <span data-ttu-id="3f796-109">La validación inmediata y sencilla permite a los usuarios trabajar de forma más eficiente y generar una mejor calidad de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="3f796-109">Straightforward and immediate validation enables users to work more efficiently and produce better quality input and output.</span></span>

<span data-ttu-id="3f796-110">Al igual que el modelo de vista y el modelo de dominio diferentes, podrían ser similar validación del modelo de vista y la validación del modelo de dominio, pero se sirven para un propósito diferente.</span><span class="sxs-lookup"><span data-stu-id="3f796-110">Just as the view model and the domain model are different, view model validation and domain model validation might be similar but serve a different purpose.</span></span> <span data-ttu-id="3f796-111">Si le preocupa sobre SECA (no repitas principio), tenga en cuenta que en este caso la reutilización del código también puede indicar el acoplamiento y en aplicaciones empresariales es más importante no acoplar el lado del servidor al cliente que al seguir el principio seco.</span><span class="sxs-lookup"><span data-stu-id="3f796-111">If you are concerned about DRY (the Don’t Repeat Yourself principle), consider that in this case code reuse might also mean coupling, and in enterprise applications it is more important not to couple the server side to the client side than to follow the DRY principle.</span></span>

<span data-ttu-id="3f796-112">Incluso cuando se utiliza la validación del lado cliente, siempre debería validar sus comandos o dto de entrada en el código de servidor, ya que las API de servidor son un vector de ataque posibles.</span><span class="sxs-lookup"><span data-stu-id="3f796-112">Even when using client-side validation, you should always validate your commands or input DTOs in server code, because the server APIs are a possible attack vector.</span></span> <span data-ttu-id="3f796-113">Normalmente, usan ambos es la mejor opción porque si tiene una aplicación de cliente, desde una perspectiva UX, es mejor ser proactivo y no permitir que el usuario escriba información no válida.</span><span class="sxs-lookup"><span data-stu-id="3f796-113">Usually, doing both is your best bet because if you have a client application, from a UX perspective, it is best to be proactive and not allow the user to enter invalid information.</span></span>

<span data-ttu-id="3f796-114">Por lo tanto, en el código de cliente suelen validar el ViewModels.</span><span class="sxs-lookup"><span data-stu-id="3f796-114">Therefore, in client-side code you typically validate the ViewModels.</span></span> <span data-ttu-id="3f796-115">También puede validar el cliente dto o comandos de salida antes de enviarlos a los servicios.</span><span class="sxs-lookup"><span data-stu-id="3f796-115">You could also validate the client output DTOs or commands before you send them to the services.</span></span>

<span data-ttu-id="3f796-116">La implementación de la validación del lado cliente depende de qué tipo de aplicación cliente que está creando.</span><span class="sxs-lookup"><span data-stu-id="3f796-116">The implementation of client-side validation depends on what kind of client application you are building.</span></span> <span data-ttu-id="3f796-117">Será diferente si va a validar datos en una aplicación web MVC de web con la mayor parte del código de. NET, una aplicación web SPA con que la validación que se está codificada en JavaScript o TypeScript, o codificada de una aplicación móvil con Xamarin y C\#.</span><span class="sxs-lookup"><span data-stu-id="3f796-117">It will be different if you are validating data in a web MVC web application with most of the code in .NET, an SPA web application with that validation being coded in JavaScript or TypeScript, or a mobile app coded with Xamarin and C\#.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3f796-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="3f796-118">Additional resources</span></span>

### <a name="validation-in-xamarin-mobile-apps"></a><span data-ttu-id="3f796-119">Validación de aplicaciones móviles de Xamarin</span><span class="sxs-lookup"><span data-stu-id="3f796-119">Validation in Xamarin mobile apps</span></span>

-   <span data-ttu-id="3f796-120">**Validar entrada de texto y mostrar errores**
    [*https://developer.xamarin.com/recipes/ios/standard\_controles o texto\_campo/validar\_entrada /*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span><span class="sxs-lookup"><span data-stu-id="3f796-120">**Validate Text Input and Show Errors**
[*https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span></span>

-   <span data-ttu-id="3f796-121">**Devolución de llamada de validación**
    [*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span><span class="sxs-lookup"><span data-stu-id="3f796-121">**Validation Callback**
[*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span></span>

### <a name="validation-in-aspnet-core-apps"></a><span data-ttu-id="3f796-122">Validación en aplicaciones ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3f796-122">Validation in ASP.NET Core apps</span></span>

-   <span data-ttu-id="3f796-123">**Rick Anderson. Agregar validación**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="3f796-123">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a><span data-ttu-id="3f796-124">Validación de SPA Web aplicaciones (Angular 2, TypeScript, JavaScript)</span><span class="sxs-lookup"><span data-stu-id="3f796-124">Validation in SPA Web apps (Angular 2, TypeScript, JavaScript)</span></span>

-   <span data-ttu-id="3f796-125">**Kukic de ADO. 2 angular forman validación** **
     ** [ *https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span><span class="sxs-lookup"><span data-stu-id="3f796-125">**Ado Kukic. Angular 2 Form Validation** **
**[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span></span>

-   <span data-ttu-id="3f796-126">**Validación de formulario**
    [*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span><span class="sxs-lookup"><span data-stu-id="3f796-126">**Form Validation**
[*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span></span>

-   <span data-ttu-id="3f796-127">**Validación.**</span><span class="sxs-lookup"><span data-stu-id="3f796-127">**Validation.**</span></span> <span data-ttu-id="3f796-128">Documentación de es sencilla.</span><span class="sxs-lookup"><span data-stu-id="3f796-128">Breeze documentation.</span></span>
    [<span data-ttu-id="3f796-129">*http://BREEZE.github.IO/doc-js/Validation.HTML*</span><span class="sxs-lookup"><span data-stu-id="3f796-129">*http://breeze.github.io/doc-js/validation.html*</span></span>](http://breeze.github.io/doc-js/validation.html)

<span data-ttu-id="3f796-130">En resumen, estos son los conceptos más importantes en lo que respecta a la validación:</span><span class="sxs-lookup"><span data-stu-id="3f796-130">In summary, these are the most important concepts in regards to validation:</span></span>

-   <span data-ttu-id="3f796-131">Las entidades y agregados deben aplicar su propios coherencia y estar "siempre válido".</span><span class="sxs-lookup"><span data-stu-id="3f796-131">Entities and aggregates should enforce their own consistency and be "always valid”.</span></span> <span data-ttu-id="3f796-132">Las raíces agregadas son responsables de coherencia de varias entidades en el agregado de la mismo.</span><span class="sxs-lookup"><span data-stu-id="3f796-132">Aggregate roots are responsible for multi-entity consistency within the same aggregate.</span></span>

-   <span data-ttu-id="3f796-133">Si cree que una entidad debe entrar en un estado no válido, considere el uso de un modelo de objetos diferentes: por ejemplo, utilizando un DTO temporal hasta que se cree la entidad de dominio final.</span><span class="sxs-lookup"><span data-stu-id="3f796-133">If you think that an entity needs to enter an invalid state, consider using a different object model—for example, using a temporary DTO until you create the final domain entity.</span></span>

-   <span data-ttu-id="3f796-134">Si necesita crear varios objetos relacionados, como un agregado, y solo son válidos una vez que todos ellos se han creado, considere la posibilidad de utilizar el patrón de fábrica.</span><span class="sxs-lookup"><span data-stu-id="3f796-134">If you need to create several related objects, such as an aggregate, and they are only valid once all of them have been created, consider using the Factory pattern.</span></span>

-   <span data-ttu-id="3f796-135">Marcos de trabajo de validación son útiles en capas específicas, como la capa de presentación o la capa de aplicación o un servicio, pero normalmente no está en el nivel de modelo de dominio, ya que es necesario tomar una dependencia fuerte en un marco de trabajo de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="3f796-135">Validation frameworks are best used in specific layers, such as the presentation layer or the application/service layer, but usually not in the domain model layer, because you would need to take a strong dependency on an infrastructure framework.</span></span>

-   <span data-ttu-id="3f796-136">En la mayoría de los casos, con validación redundante en el lado del cliente es correcta, porque la aplicación puede ser automático.</span><span class="sxs-lookup"><span data-stu-id="3f796-136">In most of the cases, having redundant validation in the client side is good, because the application can be proactive.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="3f796-137">[Anterior] (dominio-modelo-layer-validations.md) [siguiente] (dominio eventos-diseño implementation.md)</span><span class="sxs-lookup"><span data-stu-id="3f796-137">[Previous] (domain-model-layer-validations.md) [Next] (domain-events-design-implementation.md)</span></span>
