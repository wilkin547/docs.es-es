---
title: Diseño de enumeraciones
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
ms.openlocfilehash: 3b24bfefd3edb0585e9c6369e9b8151b17151661
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741712"
---
# <a name="enum-design"></a>Diseño de enumeraciones

Las enumeraciones son una clase especial de tipo de valor. Hay dos tipos de enumeraciones: enumeraciones simples y enumeraciones de marcas.

Las enumeraciones simples representan pequeños conjuntos cerrados de opciones. Un ejemplo común de la enumeración simple es un conjunto de colores.

Las enumeraciones de marca están diseñadas para admitir las operaciones bit a bit en los valores de enumeración. Un ejemplo común de la enumeración Flags es una lista de opciones.

✔️ usar una enumeración para escribir de un tipo seguro parámetros, propiedades y valores devueltos que representen conjuntos de valores.

✔️ favorecer el uso de una enumeración en lugar de constantes estáticas.

❌ no usar una enumeración para los conjuntos abiertos (como la versión del sistema operativo, los nombres de sus amigos, etc.).

❌ no proporcionan valores de enumeración reservados que están pensados para un uso futuro.

Siempre puede simplemente agregar valores a la enumeración existente en una fase posterior. Vea [Agregar valores a enumeraciones](#add_value) para obtener más información sobre cómo agregar valores a las enumeraciones. Los valores reservados solo contaminan el conjunto de valores reales y tienden a provocar errores de usuario.

❌ evitar exponer públicamente las enumeraciones con un solo valor.

Una práctica común para garantizar la extensibilidad futura de las API de C es agregar parámetros reservados a las firmas de método. Estos parámetros reservados se pueden expresar como enumeraciones con un único valor predeterminado. Esto no se debe hacer en las API administradas. La sobrecarga de métodos permite agregar parámetros en futuras versiones.

❌ no incluyen valores de centinela en las enumeraciones.

Aunque a veces son útiles para los desarrolladores de Framework, los valores de centinela son confusos para los usuarios del marco. Se utilizan para realizar un seguimiento del estado de la enumeración en lugar de ser uno de los valores del conjunto representado por la enumeración.

✔️ proporcione el valor cero en las enumeraciones simples.

Considere la posibilidad de llamar a un valor similar a "ninguno". Si este valor no es adecuado para esta enumeración concreta, se debe asignar el valor subyacente de cero al valor predeterminado más común para la enumeración.

✔️ considere la posibilidad de usar <xref:System.Int32> (el valor predeterminado en la mayoría de los lenguajes de programación) como el tipo subyacente de una enumeración, a menos que se cumpla alguna de las siguientes condiciones:

- La enumeración es una enumeración flags y tiene más de 32 marcas, o espera tener más en el futuro.

- El tipo subyacente debe ser diferente de <xref:System.Int32> para facilitar la interoperabilidad con código no administrado que espera enumeraciones de tamaño diferente.

- Un tipo subyacente más pequeño produciría un ahorro sustancial en el espacio. Si espera que la enumeración se use principalmente como un argumento para el flujo de control, el tamaño tiene poca diferencia. El ahorro de tamaño puede ser importante si:

  - Se espera que la enumeración se use como un campo en una estructura o clase con instancias muy frecuentes.

  - Espera que los usuarios creen matrices de gran tamaño o colecciones de las instancias de enumeración.

  - Espera un gran número de instancias de la enumeración que se van a serializar.

Para el uso en memoria, tenga en cuenta que los objetos administrados siempre están alineados `DWORD`, por lo que necesita de forma eficaz varias enumeraciones u otras estructuras pequeñas en una instancia para empaquetar una enumeración más pequeña con para crear una diferencia, ya que el tamaño total de la instancia se va a redondear siempre a un `DWORD`.

✔️ HACER que las enumeraciones de marcas de nombre tengan sustantivos plural o sintagmas nominales y simples de enumeración con nombres singulares o sintagmas nominales.

❌ no extienden <xref:System.Enum?displayProperty=nameWithType> directamente.

<xref:System.Enum?displayProperty=nameWithType> es un tipo especial que CLR usa para crear enumeraciones definidas por el usuario. La mayoría de los lenguajes de programación proporcionan un elemento de programación que proporciona acceso a esta funcionalidad. Por ejemplo, en C# la palabra clave `enum` se usa para definir una enumeración.

<a name="design"></a>

### <a name="designing-flag-enums"></a>Diseño de enumeraciones de marcas

✔️ aplicar el <xref:System.FlagsAttribute?displayProperty=nameWithType> para marcar enumeraciones. No aplique este atributo a las enumeraciones simples.

✔️ usar las potencias de dos para los valores de enumeración de marca para que se puedan combinar libremente mediante la operación OR bit a bit.

✔️ considere la posibilidad de proporcionar valores de enumeración especiales para combinaciones de marcas de uso frecuente.

Las operaciones bit a bit son un concepto avanzado y no deben ser necesarias para tareas sencillas. <xref:System.IO.FileAccess.ReadWrite> es un ejemplo de este tipo de valor especial.

❌ evitar la creación de enumeraciones de marca en las que determinadas combinaciones de valores no son válidas.

❌ evitar el uso de valores de enumeración de marca de cero, a menos que el valor represente "todas las marcas se borren" y se denomine adecuadamente, como se indica en la siguiente instrucción.

✔️ nombre el valor cero de las enumeraciones de marcas `None`. En el caso de una enumeración de marca, el valor siempre debe significar "se borran todas las marcas".

<a name="add_value"></a>

### <a name="adding-value-to-enums"></a>Agregar valor a las enumeraciones

Es muy habitual detectar que es necesario agregar valores a una enumeración después de que ya se haya enviado. Existe un posible problema de compatibilidad de aplicaciones cuando el valor recién agregado se devuelve de una API existente, ya que es posible que las aplicaciones mal escritas no controlen correctamente el nuevo valor.

✔️ considere la posibilidad de agregar valores a las enumeraciones, a pesar de un pequeño riesgo de compatibilidad.

Si tiene datos reales sobre las incompatibilidades de aplicaciones producidas por adiciones a una enumeración, considere la posibilidad de agregar una nueva API que devuelva los valores nuevos y antiguos, y dejar de usar la API anterior, que debería seguir devolviendo solo los valores anteriores. Esto garantizará que las aplicaciones existentes sigan siendo compatibles.

*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
