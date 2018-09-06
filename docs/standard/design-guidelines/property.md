---
title: Diseño de propiedades
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e6bc0230afe2dfc03b1aeeae46a3ba54599c8da
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43875452"
---
# <a name="property-design"></a>Diseño de propiedades
Aunque las propiedades son técnicamente muy similares a los métodos, son bastante diferentes en cuanto a sus escenarios de uso. Deben considerarse como campos inteligentes. Tienen la sintaxis de llamada de campos y la flexibilidad de los métodos.  
  
 **✓ DO** crear propiedades get-only si el llamador no debe estar autorizado cambiar el valor de la propiedad.  
  
 Tenga en cuenta que, si el tipo de la propiedad es un tipo de referencia mutable, se puede cambiar el valor de propiedad incluso si la propiedad es get-only.  
  
 **X DO NOT** proporcionan solo para establecer propiedades o propiedades con el establecedor tener accesibilidad más amplio que el captador.  
  
 Por ejemplo, no utilice las propiedades con un establecedor público y un captador protegido.  
  
 Si no se puede proporcionar el captador de propiedad, implemente la funcionalidad que un método en su lugar. Considere la posibilidad de iniciar con el nombre del método `Set` y seguir con lo que habría denominado la propiedad. Por ejemplo, <xref:System.AppDomain> tiene un método llamado `SetCachePath` en lugar de tener una propiedad de solo establecer denominada `CachePath`.  
  
 **✓ DO** proporcionan valores predeterminados razonables para todas las propiedades, garantizando que los valores predeterminados no producen una vulnerabilidad de seguridad o un código muy ineficaz.  
  
 **✓ DO** permite que las propiedades que se establecerán en cualquier orden, incluso si esto da como resultado un estado temporal no válido del objeto.  
  
 Es común para dos o más propiedades que se va a ser interrelacionados a un punto donde algunos valores de una propiedad pueden no ser válidos, dados los valores de otras propiedades en el mismo objeto. En tales casos, las excepciones resultantes de un estado no válido deben posponerse hasta que las propiedades interrelacionadas realmente son utilizadas juntos por el objeto.  
  
 **✓ DO** conservar el valor anterior si un establecedor de propiedad inicia una excepción.  
  
 **X AVOID** iniciar excepciones desde los captadores de propiedades.  
  
 Captadores de propiedades deberían ser operaciones simples y no deben tener las condiciones previas. Si un captador puede producir una excepción, probablemente debería modificarse para que sea un método. Tenga en cuenta que esta regla no es aplicable a los indizadores, donde se espera que las excepciones como resultado de la validación de los argumentos.  
  
### <a name="indexed-property-design"></a>Diseño de propiedades indizadas  
 Una propiedad indizada es una propiedad especial que puede tener parámetros y se puede llamar con una sintaxis especial similar a la indización de matrices.  
  
 Propiedades indizadas se conocen normalmente como indizadores. Los indizadores deben usarse solo en las API que proporcionan acceso a los elementos de una colección lógica. Por ejemplo, una cadena es una colección de caracteres y el indizador en <xref:System.String?displayProperty=nameWithType> se agregó para tener acceso a sus caracteres.  
  
 **✓ CONSIDER** utilizar indizadores para proporcionar acceso a los datos almacenados en una matriz interna.  
  
 **✓ CONSIDER** proporcionar indizadores en los tipos que representan colecciones de elementos.  
  
 **X AVOID** utilizando las propiedades con más de un parámetro indizadas.  
  
 Si el diseño requiere varios parámetros, reconsidere si la propiedad realmente representa un descriptor de acceso a una colección lógica. Si no es así, use los métodos en su lugar. Considere la posibilidad de iniciar con el nombre del método `Get` o `Set`.  
  
 **X AVOID** indizadores con tipos de parámetro distinto de <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, o una enumeración.  
  
 Si el diseño requiere otros tipos de parámetros, fuertemente vuelva a evaluar si la API realmente representa un descriptor de acceso a una colección lógica. Si no es así, utilice un método. Considere la posibilidad de iniciar con el nombre del método `Get` o `Set`.  
  
 **✓ DO** utilizar el nombre `Item` para propiedades indizadas a menos que haya nombre obviamente mejor (p. ej., vea el <xref:System.String.Chars%2A> propiedad `System.String`).  
  
 En C#, los indizadores son de forma predeterminada, denominado "Item". El <xref:System.Runtime.CompilerServices.IndexerNameAttribute> puede usarse para personalizar este nombre.  
  
 **X DO NOT** proporciona un indizador y métodos que son semánticamente equivalentes.  
  
 **X DO NOT** proporcionar más de una familia de indizadores sobrecargados en un tipo.  
  
 Esto se aplica por el compilador de C#.  
  
 **X DO NOT** no predeterminado de usar las propiedades indizadas.  
  
 Esto se aplica por el compilador de C#.  
  
### <a name="property-change-notification-events"></a>Eventos de notificación de cambio de propiedad  
 A veces resulta útil proporcionar un evento notificando al usuario de los cambios en un valor de propiedad. Por ejemplo, `System.Windows.Forms.Control` provoca un `TextChanged` eventos después del valor de su `Text` propiedad ha cambiado.  
  
 **✓ CONSIDER** cuando se genera cambiar eventos de notificación cuando se modifican los valores de propiedad en las API de alto nivel (normalmente componentes de diseñador).  
  
 Si hay un buen escenario para un usuario saber cuando cambia una propiedad de un objeto, el objeto debe generar un evento de notificación de cambio para la propiedad.  
  
 Sin embargo, es probable que tenga que vale la pena la sobrecarga de generar dichos eventos para la API de bajo nivel como tipos base o colecciones. Por ejemplo, <xref:System.Collections.Generic.List%601> no generaría dichos eventos cuando se agrega un nuevo elemento a la lista y el `Count` los cambios de propiedad.  
  
 **✓ CONSIDER** cuando se genera los eventos de notificación cuando cambia el valor de una propiedad a través de fuerzas externas cambio.  
  
 Si cambia un valor de propiedad a través de algún factor externo (de forma distinta al llamar a métodos en el objeto), generar eventos que indican al desarrollador de la que el valor está cambiando y ha cambiado. Un buen ejemplo es el `Text` propiedad de un control de cuadro de texto. Cuando el usuario escribe texto en un `TextBox`, cambia automáticamente el valor de propiedad.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)  
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
