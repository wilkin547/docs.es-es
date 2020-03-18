---
title: Validación del lado cliente (validación de los niveles de presentación)
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Explore los conceptos clave de las validaciones del lado del cliente.
ms.date: 10/08/2018
ms.openlocfilehash: 4e72dcafafc3144a75afe1fd23a4a779f5667459
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "68674362"
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a>Validación del lado cliente (validación de los niveles de presentación)

Incluso cuando el origen de verdad es el modelo del dominio y, en última instancia, debe tener validación en el nivel de modelo de dominio, la validación todavía puede controlarse en el nivel de modelo de dominio (servidor) y la IU (lado cliente).

La validación del lado cliente es una gran ventaja para los usuarios. Les permite ahorrar un tiempo que, de otro modo, pasarían esperando un viaje de ida y vuelta al servidor que podría devolver errores de validación. En términos comerciales, incluso unas pocas fracciones de segundos multiplicadas por cientos de veces al día suman una gran cantidad de tiempo, gastos y frustración. La validación inmediata y sencilla permite a los usuarios trabajar de forma más eficiente y generar una entrada y salida de datos de mayor calidad.

Al igual que el modelo de vista y el modelo de dominio son diferentes, la validación del modelo de vista y la validación del modelo de dominio podrían ser similares, pero servir para un propósito diferente. Si le preocupa DRY (el principio de No repetirse), tenga en cuenta que en este caso la reutilización del código también puede indicar el acoplamiento y en las aplicaciones empresariales es más importante no acoplar el lado servidor al lado cliente que seguir el principio DRY.

Incluso cuando se usa la validación del lado cliente, siempre debe validar sus comandos o DTO de entrada en el código de servidor, ya que las API de servidor son un posible vector de ataque. Normalmente, la mejor opción es hacer ambas cosas porque, si tiene una aplicación cliente, desde la perspectiva de la experiencia del usuario es mejor anticiparse y no permitir que el usuario escriba información no válida.

Por tanto, normalmente se validan los ViewModels en el código del lado cliente. También puede validar los DTO o los comandos de salida del cliente antes de enviarlos a los servicios.

La implementación de la validación del lado cliente depende del tipo de aplicación cliente que esté creando. Será diferente si valida los datos en una aplicación web MVC con la mayor parte del código en .NET, una aplicación web SPA en la que la validación se codifique en JavaScript o TypeScript, o bien una aplicación móvil codificada con Xamarin y C#.

## <a name="additional-resources"></a>Recursos adicionales

### <a name="validation-in-xamarin-mobile-apps"></a>Validación en aplicaciones móviles de Xamarin

- **Validar la entrada de texto y mostrar errores** \
  [https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)

- **Devolución de llamada de validación** \
  <https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/>

### <a name="validation-in-aspnet-core-apps"></a>Validación en aplicaciones ASP.NET Core

- **Rick Anderson. Agregar validación a una aplicación ASP.NET Core MVC** \
  <https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a>Validación en aplicaciones SPA Web (Angular 2, TypeScript, JavaScript)

- **Ado Kukic. Validación de formularios de Angular 2** \
  <https://scotch.io/tutorials/angular-2-form-validation>

- **Validación de formularios** \
  <https://angular.io/guide/form-validation>

- **Validation (Validación).** Documentación de Breeze. \
  <https://breeze.github.io/doc-js/validation.html>

En resumen, estos son los conceptos más importantes en lo que respecta a la validación:

- Las entidades y los agregados deben aplicar su propia coherencia y ser "siempre válidos". Las raíces agregadas son responsables de la coherencia de varias entidades dentro del mismo agregado.

- Si cree que una entidad debe entrar en un estado no válido, considere el uso de un modelo de objetos diferente: por ejemplo, usando un DTO temporal hasta que cree la entidad de dominio final.

- Si necesita crear varios objetos relacionados, como un agregado, y solo son válidos una vez que todos ellos se han creado, considere la posibilidad de usar el patrón Factory.

- En la mayoría de los casos, tener validación redundante en el lado cliente es adecuado, porque la aplicación puede ser proactiva.

>[!div class="step-by-step"]
>[Anterior](domain-model-layer-validations.md)
>[Siguiente](domain-events-design-implementation.md)
