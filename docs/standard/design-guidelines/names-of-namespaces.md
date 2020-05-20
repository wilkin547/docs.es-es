---
title: Nombres de espacios de nombres
description: Siga estas instrucciones para asignar nombres a los espacios de nombres como parte de las instrucciones para diseñar bibliotecas que extienden e interactúan con las bibliotecas de .NET.
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
ms.openlocfilehash: 0ad98af240cf8d1041d6a8b64ab71a56e763f76f
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419062"
---
# <a name="names-of-namespaces"></a>Nombres de espacios de nombres
Como ocurre con otras directrices de nomenclatura, el objetivo de asignar nombres a los espacios de nombres es crear una claridad suficiente para que el programador use el marco de trabajo para saber inmediatamente cuál es el contenido del espacio de nombres. La plantilla siguiente especifica la regla general para asignar nombres a los espacios de nombres:

 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`

 A continuación, se muestran algunos ejemplos:

 `Fabrikam.Math` `Litware.Security`

 ✔️ prefijar los nombres de los espacios de nombres con un nombre de compañía para evitar que los espacios de nombres de distintas empresas tengan el mismo nombre.

 ✔️ usar un nombre de producto estable y independiente de la versión en el segundo nivel de un nombre de espacio de nombres.

 ❌No utilice jerarquías organizativas como base para los nombres de las jerarquías de espacio de nombres, ya que los nombres de grupo dentro de las organizaciones tienden a ser de corta duración. Organice la jerarquía de espacios de nombres en torno a grupos de tecnologías relacionadas.

 ✔️ usar PascalCasing y separar los componentes de los espacios de nombres con puntos (por ejemplo, `Microsoft.Office.PowerPoint` ). Si la marca emplea una grafía no tradicional, debe seguir las mayúsculas y minúsculas definidas por la marca, incluso si se desvía de la grafía normal del espacio de nombres.

 ✔️ CONSIDERE el uso de nombres de espacios de nombres plurales cuando corresponda.

 Por ejemplo, use `System.Collections` en lugar de `System.Collection`. Sin embargo, los nombres de marca y los acrónimos son excepciones a esta regla. Por ejemplo, use `System.IO` en lugar de `System.IOs`.

 ❌No use el mismo nombre para un espacio de nombres y un tipo en dicho espacio de nombres.

 Por ejemplo, no use `Debug` como nombre de espacio de nombres y, a continuación, proporcione también una clase denominada `Debug` en el mismo espacio de nombres. Varios compiladores requieren que estos tipos sean completos.

### <a name="namespaces-and-type-name-conflicts"></a>Conflictos de nombres de tipos y espacios de nombres
 ❌No introduzca nombres de tipo genéricos como `Element` , `Node` , `Log` y `Message` .

 Existe una probabilidad muy alta de que esto provocará conflictos de nombres de tipo en escenarios comunes. Debe calificar los nombres de tipos genéricos ( `FormElement` , `XmlNode` , `EventLog` , `SoapMessage` ).

 Existen directrices específicas para evitar conflictos de nombres de tipo para distintas categorías de espacios de nombres.

- **Espacios de nombres del modelo de aplicación**

     Los espacios de nombres que pertenecen a un único modelo de aplicación suelen usarse juntos, pero casi nunca se usan con espacios de nombres de otros modelos de aplicación. Por ejemplo, el <xref:System.Windows.Forms?displayProperty=nameWithType> espacio de nombres se suele usar junto con el <xref:System.Web.UI?displayProperty=nameWithType> espacio de nombres. A continuación se muestra una lista de grupos de espacios de nombres del modelo de aplicación conocidos:

     `System.Windows*` `System.Web.UI*`

     ❌NO asigne el mismo nombre a los tipos de los espacios de nombres dentro de un único modelo de aplicación.

     Por ejemplo, no agregue un tipo denominado `Page` al espacio de <xref:System.Web.UI.Adapters?displayProperty=nameWithType> nombres, ya que el <xref:System.Web.UI?displayProperty=nameWithType> espacio de nombres ya contiene un tipo denominado `Page` .

- **Espacios de nombres de infraestructura**

     Este grupo contiene espacios de nombres que rara vez se importan durante el desarrollo de aplicaciones comunes. Por ejemplo, los `.Design` espacios de nombres se utilizan principalmente al desarrollar herramientas de programación. Evitar conflictos con tipos en estos espacios de nombres no es crítico.

- **Espacios de nombres principales**

     Los espacios de nombres principales incluyen todos los `System` espacios de nombres, excluidos los espacios de nombres de los modelos de aplicación y los espacios de nombres de la infraestructura. Los espacios de nombres principales incluyen, entre otros, `System` ,, `System.IO` `System.Xml` y `System.Net` .

     ❌NO proporcione nombres de tipos que entren en conflicto con cualquier tipo de los espacios de nombres principales.

     Por ejemplo, nunca use `Stream` como nombre de tipo. Entraría en conflicto con <xref:System.IO.Stream?displayProperty=nameWithType> , un tipo de uso muy común.

- **Grupos de espacios de nombres de tecnología**

     Esta categoría incluye todos los espacios de nombres con los mismos dos primeros nodos de espacio `(<Company>.<Technology>*` de nombres), como `Microsoft.Build.Utilities` y `Microsoft.Build.Tasks` . Es importante que los tipos que pertenecen a una sola tecnología no entren en conflicto entre sí.

     ❌NO asigne nombres de tipo que entren en conflicto con otros tipos dentro de una sola tecnología.

     ❌No introduzca conflictos de nombres de tipo entre los tipos de los espacios de nombres de tecnología y un espacio de nombres del modelo de aplicación (a menos que la tecnología no esté pensada para usarse con el modelo de aplicación).

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Directrices de diseño de marco](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
