---
description: 'Más información acerca de: Diseño de propiedades'
title: Diseño de propiedades
ms.date: 10/22/2008
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
ms.openlocfilehash: b2f776a5fb651f8b2e61b750a556704fa6c8c366
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731804"
---
# <a name="property-design"></a>Diseño de propiedades

Aunque las propiedades son técnicamente muy similares a los métodos, son bastante diferentes en cuanto a sus escenarios de uso. Deberían verse como campos inteligentes. Tienen la sintaxis de llamada de los campos y la flexibilidad de los métodos.

 ✔️ CREE solo propiedades get si no debe permitirse que el llamador cambie el valor de la propiedad.

 Tenga en cuenta que si el tipo de la propiedad es un tipo de referencia mutable, el valor de propiedad se puede cambiar incluso si la propiedad solo es get.

 ❌ NO proporcione solo propiedades set o propiedades en las que el establecedor tenga una accesibilidad más amplia que el captador.

 Por ejemplo, no use propiedades con un establecedor público y un captador protegido.

 Si no se puede proporcionar el captador de propiedades, implemente la funcionalidad como método en su lugar. Considere la posibilidad de empezar el nombre del método por `Set` y siga con el nombre que le habría dado a la propiedad. Por ejemplo, <xref:System.AppDomain> tiene un método llamado `SetCachePath` en lugar de tener solo una propiedad set denominada `CachePath`.

 ✔️ PROPORCIONE valores predeterminados razonables de todas las propiedades, asegurándose de que los valores predeterminados no dan lugar a una vulnerabilidad de seguridad ni a un código tremendamente ineficaz.

 ✔️ PERMITA que las propiedades se establezcan en cualquier orden, incluso si el resultado es un estado no válido temporal del objeto.

 Es común que dos o más propiedades estén interrelacionadas con un punto en el que algunos valores de una propiedad podrían no ser válidos dados los valores de otras propiedades en el mismo objeto. En tales casos, las excepciones resultantes del estado no válido se deben posponer hasta que el objeto utilice realmente las propiedades interrelacionadas de forma conjunta.

 ✔️ CONSERVE el valor anterior si un establecedor de propiedades inicia una excepción.

 ❌ EVITE iniciar excepciones desde captadores de propiedades.

 Los captadores de propiedades deben ser operaciones simples y no deben tener ninguna condición previa. Si un captador puede iniciar una excepción, es probable que haya que rediseñarlo para que sea un método. Tenga en cuenta que esta regla no se aplica a los indizadores, donde esperamos excepciones como resultado de la validación de los argumentos.

### <a name="indexed-property-design"></a>Diseño de propiedades indizadas

 Una propiedad indizada es una propiedad especial que puede tener parámetros y a la que se puede llamar con una sintaxis especial similar a la indexación de matrices.

 Las propiedades indexadas se conocen normalmente como indizadores. Los indizadores deben usarse solo en las API que proporcionan acceso a los elementos de una colección lógica. Por ejemplo, una cadena es una colección de caracteres y el indizador de <xref:System.String?displayProperty=nameWithType> se agregó para tener acceso a sus caracteres.

 ✔️ CONSIDERE la posibilidad de usar indizadores para proporcionar acceso a los datos almacenados en una matriz interna.

 ✔️ CONSIDERE la posibilidad de proporcionar indizadores en tipos que representan colecciones de elementos.

 ❌ EVITE usar propiedades indexadas con más de un parámetro.

 Si el diseño requiere varios parámetros, reconsidere si la propiedad realmente representa un descriptor de acceso a una colección lógica. Si no es así, use los métodos en su lugar. Considere la posibilidad de empezar el nombre del método por `Get` o `Set`.

 ❌ EVITE los indizadores con tipos de parámetros distintos de <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> o una enumeración.

 Si el diseño requiere otros tipos de parámetros, vuelva a evaluar con firmeza si la API representa realmente un descriptor de acceso a una colección lógica. En caso contrario, use un método. Considere la posibilidad de empezar el nombre del método por `Get` o `Set`.

 ✔️ USE el nombre `Item` de las propiedades indexadas, a menos que haya un nombre claramente mejor (p. ej., consulte la propiedad <xref:System.String.Chars%2A> en `System.String`).

 En C#, a los indizadores se les llama, de forma predeterminada, Elemento. <xref:System.Runtime.CompilerServices.IndexerNameAttribute> se puede usar para personalizar este nombre.

 ❌ NO proporcione un indizador ni métodos que sean semánticamente equivalentes.

 ❌ NO proporcione más de una familia de indizadores sobrecargados en un tipo.

 El compilador de C# aplica esto.

 ❌ NO use propiedades indexadas no predeterminadas.

 El compilador de C# aplica esto.

### <a name="property-change-notification-events"></a>Eventos de notificación de cambio de propiedad

 A veces resulta útil proporcionar un evento que notifique al usuario los cambios en un valor de propiedad. Por ejemplo, `System.Windows.Forms.Control` genera un evento `TextChanged` después de que el valor de su propiedad `Text` haya cambiado.

 ✔️ CONSIDERE la posibilidad de generar eventos de notificación de cambios cuando se modifiquen los valores de propiedad en las API de alto nivel (normalmente los componentes del diseñador).

 Si hay un buen escenario para que un usuario sepa cuándo cambia una propiedad de un objeto, el objeto debe generar un evento de notificación de cambio para la propiedad.

 Sin embargo, es improbable que merezca la pena la sobrecarga de generar tales eventos para las API de bajo nivel, como los tipos base o las colecciones. Por ejemplo, <xref:System.Collections.Generic.List%601> no generaría estos eventos cuando se agrega un nuevo elemento a la lista y cambia la propiedad `Count`.

 ✔️ CONSIDERE la posibilidad de generar eventos de notificación de cambio cuando el valor de una propiedad cambie a través de fuerzas externas.

 Si un valor de propiedad cambia a través de una fuerza externa (de forma distinta que llamando a los métodos en el objeto), los eventos de generación indican al desarrollador que el valor cambia y ha cambiado. Un buen ejemplo es la propiedad `Text` de un control de cuadro de texto. Cuando el usuario escribe texto en un `TextBox`, el valor de propiedad cambia automáticamente.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](member.md)
- [Instrucciones de diseño de .NET Framework](index.md)
