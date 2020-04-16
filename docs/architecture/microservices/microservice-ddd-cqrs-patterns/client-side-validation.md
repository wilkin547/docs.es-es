---
title: Validación del lado cliente (validación de los niveles de presentación)
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Explore los conceptos clave de las validaciones del lado del cliente.
ms.date: 10/08/2018
ms.openlocfilehash: 44c1e9fa280b19fcee87d4d1cdfcaa2ab9462f27
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988706"
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a><span data-ttu-id="8fc8c-103">Validación del lado cliente (validación de los niveles de presentación)</span><span class="sxs-lookup"><span data-stu-id="8fc8c-103">Client-side validation (validation in the presentation layers)</span></span>

<span data-ttu-id="8fc8c-104">Incluso cuando el origen de verdad es el modelo del dominio y, en última instancia, debe tener validación en el nivel de modelo de dominio, la validación todavía puede controlarse en el nivel de modelo de dominio (servidor) y la IU (lado cliente).</span><span class="sxs-lookup"><span data-stu-id="8fc8c-104">Even when the source of truth is the domain model and ultimately you must have validation at the domain model level, validation can still be handled at both the domain model level (server side) and the UI (client side).</span></span>

<span data-ttu-id="8fc8c-105">La validación del lado cliente es una gran ventaja para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8fc8c-105">Client-side validation is a great convenience for users.</span></span> <span data-ttu-id="8fc8c-106">Les permite ahorrar un tiempo que, de otro modo, pasarían esperando un viaje de ida y vuelta al servidor que podría devolver errores de validación.</span><span class="sxs-lookup"><span data-stu-id="8fc8c-106">It saves time they would otherwise spend waiting for a round trip to the server that might return validation errors.</span></span> <span data-ttu-id="8fc8c-107">En términos comerciales, incluso unas pocas fracciones de segundos multiplicadas por cientos de veces al día suman una gran cantidad de tiempo, gastos y frustración.</span><span class="sxs-lookup"><span data-stu-id="8fc8c-107">In business terms, even a few fractions of seconds multiplied hundreds of times each day adds up to a lot of time, expense, and frustration.</span></span> <span data-ttu-id="8fc8c-108">La validación inmediata y sencilla permite a los usuarios trabajar de forma más eficiente y generar una entrada y salida de datos de mayor calidad.</span><span class="sxs-lookup"><span data-stu-id="8fc8c-108">Straightforward and immediate validation enables users to work more efficiently and produce better quality input and output.</span></span>

<span data-ttu-id="8fc8c-109">Al igual que el modelo de vista y el modelo de dominio son diferentes, la validación del modelo de vista y la validación del modelo de dominio podrían ser similares, pero servir para un propósito diferente.</span><span class="sxs-lookup"><span data-stu-id="8fc8c-109">Just as the view model and the domain model are different, view model validation and domain model validation might be similar but serve a different purpose.</span></span> <span data-ttu-id="8fc8c-110">Si le preocupa DRY (el principio de No repetirse), tenga en cuenta que en este caso la reutilización del código también puede indicar acoplamiento y en las aplicaciones empresariales es más importante no acoplar el lado servidor al lado cliente que seguir el principio DRY.</span><span class="sxs-lookup"><span data-stu-id="8fc8c-110">If you are concerned about DRY (the Don't Repeat Yourself principle), consider that in this case code reuse might also mean coupling, and in enterprise applications it is more important not to couple the server side to the client side than to follow the DRY principle.</span></span>

<span data-ttu-id="8fc8c-111">Incluso cuando se usa la validación del lado cliente, siempre debe validar sus comandos o DTO de entrada en el código de servidor, ya que las API de servidor son un posible vector de ataque.</span><span class="sxs-lookup"><span data-stu-id="8fc8c-111">Even when using client-side validation, you should always validate your commands or input DTOs in server code, because the server APIs are a possible attack vector.</span></span> <span data-ttu-id="8fc8c-112">Normalmente, la mejor opción es hacer ambas cosas porque, si tiene una aplicación cliente, desde la perspectiva de la experiencia del usuario es mejor anticiparse y no permitir que el usuario escriba información no válida.</span><span class="sxs-lookup"><span data-stu-id="8fc8c-112">Usually, doing both is your best bet because if you have a client application, from a UX perspective, it is best to be proactive and not allow the user to enter invalid information.</span></span>

<span data-ttu-id="8fc8c-113">Por tanto, normalmente se validan los ViewModels en el código del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="8fc8c-113">Therefore, in client-side code you typically validate the ViewModels.</span></span> <span data-ttu-id="8fc8c-114">También puede validar los DTO o los comandos de salida del cliente antes de enviarlos a los servicios.</span><span class="sxs-lookup"><span data-stu-id="8fc8c-114">You could also validate the client output DTOs or commands before you send them to the services.</span></span>

<span data-ttu-id="8fc8c-115">La implementación de la validación del lado cliente depende del tipo de aplicación cliente que esté creando.</span><span class="sxs-lookup"><span data-stu-id="8fc8c-115">The implementation of client-side validation depends on what kind of client application you are building.</span></span> <span data-ttu-id="8fc8c-116">Será diferente si valida los datos en una aplicación web MVC con la mayor parte del código en .NET, una aplicación web SPA en la que la validación se codifique en JavaScript o TypeScript, o bien una aplicación móvil codificada con Xamarin y C#.</span><span class="sxs-lookup"><span data-stu-id="8fc8c-116">It will be different if you are validating data in a web MVC web application with most of the code in .NET, a SPA web application with that validation being coded in JavaScript or TypeScript, or a mobile app coded with Xamarin and C#.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8fc8c-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8fc8c-117">Additional resources</span></span>

### <a name="validation-in-xamarin-mobile-apps"></a><span data-ttu-id="8fc8c-118">Validación en aplicaciones móviles de Xamarin</span><span class="sxs-lookup"><span data-stu-id="8fc8c-118">Validation in Xamarin mobile apps</span></span>

- <span data-ttu-id="8fc8c-119">**Validar la entrada de texto y mostrar errores** </span><span class="sxs-lookup"><span data-stu-id="8fc8c-119">**Validate Text Input and Show Errors** </span></span>\
  [https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)

- <span data-ttu-id="8fc8c-120">**Devolución de llamada de validación** </span><span class="sxs-lookup"><span data-stu-id="8fc8c-120">**Validation Callback** </span></span>\
  <https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/>

### <a name="validation-in-aspnet-core-apps"></a><span data-ttu-id="8fc8c-121">Validación en aplicaciones ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8fc8c-121">Validation in ASP.NET Core apps</span></span>

- <span data-ttu-id="8fc8c-122">**Rick Anderson. Agregar validación a una aplicación ASP.NET Core MVC** </span><span class="sxs-lookup"><span data-stu-id="8fc8c-122">**Rick Anderson. Adding validation** </span></span>\
  <https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a><span data-ttu-id="8fc8c-123">Validación en aplicaciones SPA Web (Angular 2, TypeScript, JavaScript)</span><span class="sxs-lookup"><span data-stu-id="8fc8c-123">Validation in SPA Web apps (Angular 2, TypeScript, JavaScript)</span></span>

- <span data-ttu-id="8fc8c-124">**Ado Kukic. Validación de formularios de Angular 2** </span><span class="sxs-lookup"><span data-stu-id="8fc8c-124">**Ado Kukic. Angular 2 Form Validation** </span></span>\
  <https://scotch.io/tutorials/angular-2-form-validation>

- <span data-ttu-id="8fc8c-125">**Validación de formularios** </span><span class="sxs-lookup"><span data-stu-id="8fc8c-125">**Form Validation** </span></span>\
  <https://angular.io/guide/form-validation>

- <span data-ttu-id="8fc8c-126">**Validation (Validación).**</span><span class="sxs-lookup"><span data-stu-id="8fc8c-126">**Validation.**</span></span> <span data-ttu-id="8fc8c-127">Documentación de Breeze.</span><span class="sxs-lookup"><span data-stu-id="8fc8c-127">Breeze documentation.</span></span> \
  <https://breeze.github.io/doc-js/validation.html>

<span data-ttu-id="8fc8c-128">En resumen, estos son los conceptos más importantes en lo que respecta a la validación:</span><span class="sxs-lookup"><span data-stu-id="8fc8c-128">In summary, these are the most important concepts in regards to validation:</span></span>

- <span data-ttu-id="8fc8c-129">Las entidades y los agregados deben aplicar su propia coherencia y ser "siempre válidos".</span><span class="sxs-lookup"><span data-stu-id="8fc8c-129">Entities and aggregates should enforce their own consistency and be "always valid".</span></span> <span data-ttu-id="8fc8c-130">Las raíces agregadas son responsables de la coherencia de varias entidades dentro del mismo agregado.</span><span class="sxs-lookup"><span data-stu-id="8fc8c-130">Aggregate roots are responsible for multi-entity consistency within the same aggregate.</span></span>

- <span data-ttu-id="8fc8c-131">Si cree que una entidad debe entrar en un estado no válido, considere el uso de un modelo de objetos diferente: por ejemplo, usando un DTO temporal hasta que cree la entidad de dominio final.</span><span class="sxs-lookup"><span data-stu-id="8fc8c-131">If you think that an entity needs to enter an invalid state, consider using a different object model—for example, using a temporary DTO until you create the final domain entity.</span></span>

- <span data-ttu-id="8fc8c-132">Si necesita crear varios objetos relacionados, como un agregado, y solo son válidos una vez que todos ellos se han creado, considere la posibilidad de usar el patrón Factory.</span><span class="sxs-lookup"><span data-stu-id="8fc8c-132">If you need to create several related objects, such as an aggregate, and they are only valid once all of them have been created, consider using the Factory pattern.</span></span>

- <span data-ttu-id="8fc8c-133">En la mayoría de los casos, tener validación redundante en el lado cliente es adecuado, porque la aplicación puede ser proactiva.</span><span class="sxs-lookup"><span data-stu-id="8fc8c-133">In most of the cases, having redundant validation in the client side is good, because the application can be proactive.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8fc8c-134">[Anterior](domain-model-layer-validations.md)
>[Siguiente](domain-events-design-implementation.md)</span><span class="sxs-lookup"><span data-stu-id="8fc8c-134">[Previous](domain-model-layer-validations.md)
[Next](domain-events-design-implementation.md)</span></span>
