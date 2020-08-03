---
title: Diseñar las validaciones en el nivel de modelo de dominio
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Información sobre conceptos clave de las validaciones de modelo de dominio.
ms.date: 10/08/2018
ms.openlocfilehash: f1e2d7430c642ad47f79cdd34d3a65e2cc70e239
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164279"
---
# <a name="design-validations-in-the-domain-model-layer"></a>Diseño de validaciones en el nivel de modelo de dominio

En el diseño guiado por el dominio (DDD), las reglas de validación se pueden considerar invariables. La responsabilidad principal de un agregado es aplicar invariables en todos los cambios de estado para todas las entidades de ese agregado.

Las entidades de dominio siempre deben ser entidades válidas. Hay un número determinado de invariables para un objeto que siempre deben ser verdaderas. Por ejemplo, un objeto de un elemento de pedido siempre debe tener una cantidad que debe constar de un entero positivo, un nombre de artículo y un precio. Por lo tanto, la aplicación de invariables es responsabilidad de las entidades de dominio (en especial de la raíz agregada) y un objeto de entidad no debería poder existir si no es válido. Las reglas invariables se expresan como contratos y, si se infringen, se generan excepciones o notificaciones.

El razonamiento es que se producen muchos errores porque los objetos tienen un estado que no deberían tener nunca. Encontrará una buena explicación de Greg Young en este [debate en línea](http://codebetter.com/gregyoung/2009/05/22/always-valid/).

Ahora imaginémonos que tenemos un SendUserCreationEmailService que toma un UserProfile… ¿Cómo podemos justificar en ese servicio que Name no es nulo? ¿Lo volvemos a comprobar? O lo que es más probable: no se molesta en comprobarlo y "espera lo mejor" (espera que alguien se haya molestado en validarlo antes de enviárselo). Por supuesto, si usamos TDD, una de las primeras pruebas que deberíamos escribir es que si, al enviar un cliente con un nombre nulo, se generaría un error. Pero, una vez que empezamos a escribir estos tipos de pruebas una y otra vez, nos damos cuenta de que… "Espera, si no hubiéramos dejado que Name fuera nulo, no tendríamos todas estas pruebas".

## <a name="implement-validations-in-the-domain-model-layer"></a>Implementación de validaciones en el nivel de modelo de dominio

Las validaciones se suelen implementar en constructores de entidad de dominio o en métodos que pueden actualizar la entidad. Hay varias maneras de implementar las validaciones, como la comprobación de los datos y la generación de excepciones si se produce un error en la validación. También hay patrones más avanzados, como el uso del patrón de especificación para las validaciones y el patrón de notificación para devolver una colección de errores en lugar de devolver una excepción para cada validación mientras se produce.

### <a name="validate-conditions-and-throw-exceptions"></a>Validación de condiciones y generación de excepciones

En el siguiente ejemplo de código se muestra el método de validación más sencillo en una entidad de dominio mediante la generación de una excepción. En la tabla de referencias que encontrará al final de esta sección puede ver vínculos a implementaciones más avanzadas según los patrones que hemos analizado anteriormente.

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

Un ejemplo mejor demostraría la necesidad de garantizar que el estado interno no varió o que se produjeron todas las mutaciones de un método. Por ejemplo, la siguiente implementación dejaría el objeto en un estado no válido:

```csharp
public void SetAddress(string line1, string line2,
    string city, string state, int zip)
{
    _shippingAddress.line1 = line1 ?? throw new ...
    _shippingAddress.line2 = line2;
    _shippingAddress.city = city ?? throw new ...
    _shippingAddress.state = (IsValid(state) ? state : throw new …);
}
```

Si el valor del estado no es válido, la primera línea de dirección y la ciudad ya se han cambiado, lo cual podría invalidar la dirección.

Se puede aplicar un enfoque similar en el constructor de la entidad, generando una excepción para garantizar que la entidad sea válida una vez creada.

### <a name="use-validation-attributes-in-the-model-based-on-data-annotations"></a>Uso de atributos de validación en el modelo en función de las anotaciones de datos

Las anotaciones de datos, como los atributos MaxLength o Required, se pueden usar para configurar las propiedades de campo de base de datos de EF Core, como se explica en detalle en la sección [Asignación de tabla](infrastructure-persistence-layer-implementation-entity-framework-core.md#table-mapping), pero [ya no funcionan para la validación de entidades en EF Core](https://github.com/dotnet/efcore/issues/3680) (tampoco funciona el método <xref:System.ComponentModel.DataAnnotations.IValidatableObject.Validate%2A?displayProperty=nameWithType>), tal y como lo han hecho desde EF 4.x en .NET Framework.

Las anotaciones de datos y la interfaz <xref:System.ComponentModel.DataAnnotations.IValidatableObject> todavía se pueden usar para la validación del modelo durante el enlace de modelos, antes de la invocación de acciones del controlador como de costumbre, pero ese modelo está pensado para ser un ViewModel o DTO, y eso atañe a MVC o la API, no al modelo de dominio.

Después de tener la diferencia conceptual clara, todavía puede usar anotaciones de datos y `IValidatableObject` en la clase de entidad para la validación, si las acciones reciben un parámetro de objeto de clase de entidad, lo que no se recomienda. En ese caso, la validación se producirá durante el enlace de modelos, justo antes de invocar la acción y se puede comprobar la propiedad ModelState.IsValid del controlador para comprobar el resultado, pero nuevamente, ocurre en el controlador, no antes de guardar el objeto de entidad en el DbContext, tal como se había llevado a cabo desde EF 4.x.

Todavía puede implementar la validación personalizada en la clase de entidad con las anotaciones de datos y el método `IValidatableObject.Validate` invalidando el método SaveChanges de DbContext.

Puede ver un ejemplo de implementación de la validación de entidades de `IValidatableObject` en [este comentario en GitHub](https://github.com/dotnet/efcore/issues/3680#issuecomment-155502539). Ese ejemplo no realiza validaciones basadas en atributos, pero deberían ser fáciles de implementar mediante la reflexión en el mismo reemplazo.

Aunque, desde la óptica del DDD, el modelo de dominio se ajusta mejor con el uso de excepciones en los métodos de comportamiento de la entidad o con la implementación de los patrones de especificación y notificación para aplicar reglas de validación.

Puede resultar lógico usar anotaciones de datos en el nivel de aplicación en las clases ViewModel (en lugar de hacerlo en las entidades de dominio) que aceptarán la entrada a fin de permitirlas para la validación del modelo en la capa de la interfaz de usuario, pero no se debería hacer en la exclusión de validación dentro del modelo de dominio.

### <a name="validate-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a>Validación de entidades implementando el patrón de especificación y el patrón de notificación

Por último, un enfoque más elaborado para implementar validaciones en el modelo de dominio consiste en implementar el patrón de especificación junto con el patrón de notificación, como se explica en algunos de los recursos adicionales que se muestran más adelante.

Merece la pena mencionar que también se puede usar solo uno de estos patrones (por ejemplo, validándolo manualmente con instrucciones de control, pero usando el patrón de notificación para apilar y devolver una lista de errores de validación).

### <a name="use-deferred-validation-in-the-domain"></a>Uso de la validación diferida en el dominio

Hay varios métodos para tratar las validaciones diferidas en el dominio. En su libro [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577) (Implementación del diseño guiado por el dominio), Vaughn Vernon habla de ellos en la sección sobre la validación.

### <a name="two-step-validation"></a>Validación en dos pasos

Plantéese también usar la validación en dos pasos. Use la validación de nivel de campo en los objetos de transferencia de datos (DTO) de comandos y la validación de nivel de dominio dentro de las entidades. Para ello, puede devolver un objeto de resultado en vez de excepciones para que resulte más fácil tratar los errores de validación.

Si usa la validación de campos con anotaciones de datos, por ejemplo, no se duplica la definición de validación. Pero la ejecución puede ser del lado servidor y del lado cliente en el caso de los DTO (comandos y ViewModels, por ejemplo).

## <a name="additional-resources"></a>Recursos adicionales

- **Rachel Appel. Validación de modelos en ASP.NET Core MVC** \
  <https://docs.microsoft.com/aspnet/core/mvc/models/validation>

- **Rick Anderson. Agregar validación a una aplicación ASP.NET Core MVC** \
  <https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation>

- **Martin Fowler. Replacing Throwing Exceptions with Notification in Validations** \ (Reemplazo del inicio de excepciones por notificaciones en validaciones)\
  <https://martinfowler.com/articles/replaceThrowWithNotification.html>

- **Specification and Notification Patterns** \ (Patrones de especificación y notificación)\
  <https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns>

- **Lev Gorodinski. Validation in Domain-Driven Design (DDD)**  \ (Validación en diseños guiados por dominio)\
  <http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/>

- **Colin Jack. Domain Model Validation** \ (Validación de modelos de dominio)\
  <https://colinjack.blogspot.com/2008/03/domain-model-validation.html>

- **Jimmy Bogard. Validation in a DDD world** \ (Validación en un mundo de diseños guiados por dominio)\
  <https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/>

> [!div class="step-by-step"]
> [Anterior](enumeration-classes-over-enum-types.md)
> [Siguiente](client-side-validation.md)
