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
# <a name="client-side-validation-validation-in-the-presentation-layers"></a>Validación del lado cliente (validación de los niveles de presentación)

Incluso cuando el origen de verdad es el modelo de dominio y en última instancia debe tener validación en el nivel de modelo de dominio, validación todavía puede controlarse en el nivel de modelo de dominio (servidor) y el lado del cliente.

Validación del lado cliente es una gran ventaja para los usuarios. Ahorra tiempo en caso contrario, se gastan esperando de ida y vuelta al servidor que se produzcan errores de validación. En términos comerciales, incluso unos fracciones de segundos multiplicados cientos de veces que cada día se agrega a una gran cantidad de tiempo y gastos, frustración. La validación inmediata y sencilla permite a los usuarios trabajar de forma más eficiente y generar una mejor calidad de entrada y salida.

Al igual que el modelo de vista y el modelo de dominio diferentes, podrían ser similar validación del modelo de vista y la validación del modelo de dominio, pero se sirven para un propósito diferente. Si le preocupa sobre SECA (no repitas principio), tenga en cuenta que en este caso la reutilización del código también puede indicar el acoplamiento y en aplicaciones empresariales es más importante no acoplar el lado del servidor al cliente que al seguir el principio seco.

Incluso cuando se utiliza la validación del lado cliente, siempre debería validar sus comandos o dto de entrada en el código de servidor, ya que las API de servidor son un vector de ataque posibles. Normalmente, usan ambos es la mejor opción porque si tiene una aplicación de cliente, desde una perspectiva UX, es mejor ser proactivo y no permitir que el usuario escriba información no válida.

Por lo tanto, en el código de cliente suelen validar el ViewModels. También puede validar el cliente dto o comandos de salida antes de enviarlos a los servicios.

La implementación de la validación del lado cliente depende de qué tipo de aplicación cliente que está creando. Será diferente si va a validar datos en una aplicación web MVC de web con la mayor parte del código de. NET, una aplicación web SPA con que la validación que se está codificada en JavaScript o TypeScript, o codificada de una aplicación móvil con Xamarin y C\#.

## <a name="additional-resources"></a>Recursos adicionales

### <a name="validation-in-xamarin-mobile-apps"></a>Validación de aplicaciones móviles de Xamarin

-   **Validar entrada de texto y mostrar errores**
    [*https://developer.xamarin.com/recipes/ios/standard\_controles o texto\_campo/validar\_entrada /*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)

-   **Devolución de llamada de validación**
    [*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)

### <a name="validation-in-aspnet-core-apps"></a>Validación en aplicaciones ASP.NET Core

-   **Rick Anderson. Agregar validación**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a>Validación de SPA Web aplicaciones (Angular 2, TypeScript, JavaScript)

-   **Kukic de ADO. 2 angular forman validación** **
     ** [ *https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)

-   **Validación de formulario**
    [*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)

-   **Validación.** Documentación de es sencilla.
    [*http://BREEZE.github.IO/doc-js/Validation.HTML*](http://breeze.github.io/doc-js/validation.html)

En resumen, estos son los conceptos más importantes en lo que respecta a la validación:

-   Las entidades y agregados deben aplicar su propios coherencia y estar "siempre válido". Las raíces agregadas son responsables de coherencia de varias entidades en el agregado de la mismo.

-   Si cree que una entidad debe entrar en un estado no válido, considere el uso de un modelo de objetos diferentes: por ejemplo, utilizando un DTO temporal hasta que se cree la entidad de dominio final.

-   Si necesita crear varios objetos relacionados, como un agregado, y solo son válidos una vez que todos ellos se han creado, considere la posibilidad de utilizar el patrón de fábrica.

-   Marcos de trabajo de validación son útiles en capas específicas, como la capa de presentación o la capa de aplicación o un servicio, pero normalmente no está en el nivel de modelo de dominio, ya que es necesario tomar una dependencia fuerte en un marco de trabajo de infraestructura.

-   En la mayoría de los casos, con validación redundante en el lado del cliente es correcta, porque la aplicación puede ser automático.


>[!div class="step-by-step"]
[Anterior] (dominio-modelo-layer-validations.md) [siguiente] (dominio eventos-diseño implementation.md)
