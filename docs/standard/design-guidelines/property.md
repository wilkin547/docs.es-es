---
title: Diseño de propiedades
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
ms.openlocfilehash: 8b6570b1b7c292729b78f2fe52f24f73319efe6c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743655"
---
# <a name="property-design"></a>Diseño de propiedades
Aunque las propiedades son técnicamente muy similares a los métodos, son bastante diferentes en cuanto a sus escenarios de uso. Deberían aparecer como campos inteligentes. Tienen la sintaxis de llamada de los campos y la flexibilidad de los métodos.

 ✔️ crear propiedades Get-only Si el autor de la llamada no debe ser capaz de cambiar el valor de la propiedad.

 Tenga en cuenta que si el tipo de la propiedad es un tipo de referencia mutable, el valor de la propiedad se puede cambiar aunque la propiedad sea de solo lectura.

 ❌ no proporcionan propiedades o propiedades solo de conjunto con el establecedor con una accesibilidad más amplia que el captador.

 Por ejemplo, no utilice propiedades con un establecedor público y un captador protegido.

 Si no se puede proporcionar el captador de propiedad, implemente la funcionalidad como un método en su lugar. Considere la posibilidad de iniciar el nombre del método con `Set` y siga con lo que hubiera llamado a la propiedad. Por ejemplo, <xref:System.AppDomain> tiene un método denominado `SetCachePath` en lugar de tener una propiedad de solo establecimiento denominada `CachePath`.

 ✔️ proporcionan valores predeterminados razonables para todas las propiedades, asegurándose de que los valores predeterminados no dan lugar a un agujero de seguridad ni a un código ineficaz.

 ✔️ permitir que las propiedades se establezcan en cualquier orden, incluso si el resultado es un estado no válido temporal del objeto.

 Es común que dos o más propiedades se interrelacionan con un punto en el que algunos valores de una propiedad podrían no ser válidos dados los valores de otras propiedades en el mismo objeto. En tales casos, las excepciones resultantes del estado no válido se deben posponer hasta que el objeto utilice realmente las propiedades interrelacionadas.

 ✔️ conservar el valor anterior si un establecedor de propiedad produce una excepción.

 ❌ Evite iniciar excepciones a partir de captadores de propiedad.

 Los captadores de propiedad deben ser operaciones simples y no deben tener ninguna condición previa. Si un captador puede producir una excepción, probablemente se debe volver a diseñar para que sea un método. Tenga en cuenta que esta regla no se aplica a los indexadores, donde se esperan excepciones como resultado de la validación de los argumentos.

### <a name="indexed-property-design"></a>Diseño de propiedades indizadas
 Una propiedad indizada es una propiedad especial que puede tener parámetros y se puede llamar con una sintaxis especial similar a la indización de matrices.

 Las propiedades indizadas se conocen normalmente como indexadores. Los indizadores deben usarse solo en las API que proporcionan acceso a los elementos de una colección lógica. Por ejemplo, una cadena es una colección de caracteres y se ha agregado el indizador en <xref:System.String?displayProperty=nameWithType> para tener acceso a sus caracteres.

 ✔️ considere la posibilidad de usar indizadores para proporcionar acceso a los datos almacenados en una matriz interna.

 ✔️ considere la posibilidad de proporcionar indexadores en tipos que representan colecciones de elementos.

 ❌ evitar el uso de propiedades indizadas con más de un parámetro.

 Si el diseño requiere varios parámetros, reconsidere si la propiedad realmente representa un descriptor de acceso a una colección lógica. Si no es así, use los métodos en su lugar. Considere la posibilidad de iniciar el nombre del método con `Get` o `Set`.

 ❌ evitar indizadores con tipos de parámetros distintos de <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>o una enumeración.

 Si el diseño requiere otros tipos de parámetros, vuelva a evaluar de forma segura si la API representa realmente un descriptor de acceso a una colección lógica. En caso contrario, utilice un método. Considere la posibilidad de iniciar el nombre del método con `Get` o `Set`.

 ✔️ usar el nombre `Item` para las propiedades indizadas, a menos que haya un nombre claramente mejor (por ejemplo, vea la propiedad <xref:System.String.Chars%2A> en `System.String`).

 En C#, los indizadores se llaman de forma predeterminada Item. El <xref:System.Runtime.CompilerServices.IndexerNameAttribute> se puede usar para personalizar este nombre.

 ❌ no proporcionan un indexador y métodos que sean semánticamente equivalentes.

 ❌ no proporcionan más de una familia de indexadores sobrecargados en un tipo.

 Lo exige el C# compilador.

 ❌ no utilizan propiedades indizadas no predeterminadas.

 Lo exige el C# compilador.

### <a name="property-change-notification-events"></a>Eventos de notificación de cambio de propiedad
 A veces resulta útil proporcionar un evento que notifique al usuario los cambios en un valor de propiedad. Por ejemplo, `System.Windows.Forms.Control` genera un evento `TextChanged` después de que el valor de su propiedad `Text` haya cambiado.

 ✔️ considere la posibilidad de generar eventos de notificación de cambios cuando se modifiquen los valores de propiedad en las API de alto nivel (normalmente los componentes del diseñador).

 Si hay un buen escenario para que un usuario sepa cuándo está cambiando una propiedad de un objeto, el objeto debe generar un evento de notificación de cambios para la propiedad.

 Sin embargo, no es probable que merezca la pena la sobrecarga de generar tales eventos para las API de bajo nivel, como los tipos base o las colecciones. Por ejemplo, <xref:System.Collections.Generic.List%601> no generaría estos eventos cuando se agrega un nuevo elemento a la lista y cambia la propiedad `Count`.

 ✔️ considere la posibilidad de generar eventos de notificación de cambios cuando el valor de una propiedad cambia a través de fuerzas externas.

 Si un valor de propiedad cambia a través de una fuerza externa (de forma distinta a llamando a los métodos del objeto), los eventos de generación indican al desarrollador que el valor está cambiando y ha cambiado. Un buen ejemplo es la `Text` propiedad de un control de cuadro de texto. Cuando el usuario escribe texto en un `TextBox`, el valor de la propiedad cambia automáticamente.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
