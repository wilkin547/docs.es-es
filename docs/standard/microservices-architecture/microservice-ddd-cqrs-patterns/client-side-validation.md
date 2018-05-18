---
title: Validación del lado cliente (validación de los niveles de presentación)
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Validación del lado cliente (validación de los niveles de presentación)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 2adce39561dd2b97910155ebed595a2df7785c11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a>Validación del lado cliente (validación de los niveles de presentación)

Incluso cuando el origen de verdad es el modelo del dominio y, en última instancia, debe tener validación en el nivel de modelo de dominio, la validación todavía puede controlarse en el nivel de modelo de dominio (servidor) y en el lado cliente.

La validación del lado cliente es una gran ventaja para los usuarios. Les permite ahorrar un tiempo que, de otro modo, pasarían esperando un viaje de ida y vuelta al servidor que podría devolver errores de validación. En términos comerciales, incluso unas pocas fracciones de segundos multiplicadas por cientos de veces al día suman una gran cantidad de tiempo, gastos y frustración. La validación inmediata y sencilla permite a los usuarios trabajar de forma más eficiente y generar una entrada y salida de datos de mayor calidad.

Al igual que el modelo de vista y el modelo de dominio son diferentes, la validación del modelo de vista y la validación del modelo de dominio podrían ser similares, pero servir para un propósito diferente. Si le preocupa DRY (el principio de No repetirse), tenga en cuenta que en este caso la reutilización del código también puede indicar el acoplamiento y en las aplicaciones empresariales es más importante no acoplar el lado servidor al lado cliente que seguir el principio DRY.

Incluso cuando se usa la validación del lado cliente, siempre debe validar sus comandos o DTO de entrada en el código de servidor, ya que las API de servidor son un posible vector de ataque. Normalmente, la mejor opción es hacer ambas cosas porque, si tiene una aplicación cliente, desde la perspectiva de la experiencia del usuario es mejor anticiparse y no permitir que el usuario escriba información no válida.

Por tanto, normalmente se validan los ViewModels en el código del lado cliente. También puede validar los DTO o los comandos de salida del cliente antes de enviarlos a los servicios.

La implementación de la validación del lado cliente depende del tipo de aplicación cliente que esté creando. Será diferente si valida los datos en una aplicación web de web MVC con la mayor parte del código en .NET, una aplicación web SPA en que la validación se codifique en JavaScript o TypeScript o una aplicación móvil codificada con Xamarin y C\#.

## <a name="additional-resources"></a>Recursos adicionales

### <a name="validation-in-xamarin-mobile-apps"></a>Validación en aplicaciones móviles de Xamarin

-   **Validate Text Input and Show Errors (Validar la entrada de texto y mostrar errores)**
    [*https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)

-   **Validation Callback (Devolución de llamada de validación)**
    [*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)

### <a name="validation-in-aspnet-core-apps"></a>Validación en aplicaciones ASP.NET Core

-   **Rick Anderson. Adding validation (Adición de validación)**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a>Validación en aplicaciones SPA Web (Angular 2, TypeScript, JavaScript)

-   **Ado Kukic. Angular 2 Form Validation (Validación de formularios de Angular 2)** **
    **[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)

-   **Form Validation (Validación de formularios)**
    [*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)

-   **Validation (Validación).** Documentación de Breeze.
    [*https://breeze.github.io/doc-js/validation.html*](https://breeze.github.io/doc-js/validation.html)

En resumen, estos son los conceptos más importantes en lo que respecta a la validación:

-   Las entidades y los agregados deben aplicar su propia coherencia y ser "siempre válidos". Las raíces agregadas son responsables de la coherencia de varias entidades dentro del mismo agregado.

-   Si cree que una entidad debe entrar en un estado no válido, considere el uso de un modelo de objetos diferente: por ejemplo, usando un DTO temporal hasta que cree la entidad de dominio final.

-   Si necesita crear varios objetos relacionados, como un agregado, y solo son válidos una vez que todos ellos se han creado, considere la posibilidad de usar el patrón Factory.

-   Los marcos de validación son más útiles en niveles específicos, como el nivel de presentación o el nivel de aplicación/servicio, pero normalmente no en el nivel de modelo de dominio, ya que es necesario tomar una dependencia fuerte en un marco de infraestructura.

-   En la mayoría de los casos, tener validación redundante en el lado cliente es adecuado, porque la aplicación puede ser proactiva.


>[!div class="step-by-step"]
[Previous] (domain-model-layer-validations.md) [Next] (domain-events-design-implementation.md)
