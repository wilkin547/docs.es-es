---
title: Nombres de espacios de nombres
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
ms.openlocfilehash: 0678f695e3ae7c40660031862c9073a21fd72491
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709236"
---
# <a name="names-of-namespaces"></a>Nombres de espacios de nombres
Como ocurre con otras directrices de nomenclatura, el objetivo de asignar nombres a los espacios de nombres es crear una claridad suficiente para que el programador use el marco de trabajo para saber inmediatamente cuál es el contenido del espacio de nombres. La plantilla siguiente especifica la regla general para asignar nombres a los espacios de nombres:  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 A continuación, se exponen algunos ejemplos:  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 **✓ DO** prefijos de espacios de nombres con un nombre de compañía para evitar que los espacios de nombres de distintas compañías que tengan el mismo nombre.  
  
 **✓ DO** utilizar un nombre de producto estable, independiente de la versión en el segundo nivel de un nombre de espacio de nombres.  
  
 **X DO NOT** usar jerarquías organizativas como base para los nombres en las jerarquías de espacio de nombres, porque los nombres de grupo dentro de las organizaciones tienden a ser de corta duración. Organice la jerarquía de espacios de nombres en torno a grupos de tecnologías relacionadas.  
  
 **✓ DO** usar Pascal y componentes del espacio de nombres independiente con puntos (por ejemplo, `Microsoft.Office.PowerPoint`). Si la marca emplea una grafía no tradicional, debe seguir las mayúsculas y minúsculas definidas por la marca, incluso si se desvía de la grafía normal del espacio de nombres.  
  
 **✓ CONSIDER** recurriendo plural espacios de nombres en su caso.  
  
 Por ejemplo, use `System.Collections` en lugar de `System.Collection`. Sin embargo, los nombres de marca y los acrónimos son excepciones a esta regla. Por ejemplo, use `System.IO` en lugar de `System.IOs`.  
  
 **X DO NOT** usar el mismo nombre para un espacio de nombres y un tipo en ese espacio de nombres.  
  
 Por ejemplo, no use `Debug` como nombre de espacio de nombres y, a continuación, proporcione también una clase denominada `Debug` en el mismo espacio de nombres. Varios compiladores requieren que estos tipos sean completos.  
  
### <a name="namespaces-and-type-name-conflicts"></a>Conflictos de nombres de tipos y espacios de nombres  
 **X DO NOT** introducir los nombres de tipos genéricos como `Element`, `Node`, `Log`, y `Message`.  
  
 Existe una probabilidad muy alta de que esto provocará conflictos de nombres de tipo en escenarios comunes. Debe calificar los nombres de tipo genérico (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).  
  
 Existen directrices específicas para evitar conflictos de nombres de tipo para distintas categorías de espacios de nombres.  
  
- **Espacios de nombres del modelo de aplicación**  
  
     Los espacios de nombres que pertenecen a un único modelo de aplicación suelen usarse juntos, pero casi nunca se usan con espacios de nombres de otros modelos de aplicación. Por ejemplo, el espacio de nombres <xref:System.Windows.Forms?displayProperty=nameWithType> se usa muy rara vez junto con el espacio de nombres <xref:System.Web.UI?displayProperty=nameWithType>. A continuación se muestra una lista de grupos de espacios de nombres del modelo de aplicación conocidos:  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     **X DO NOT** dar el mismo nombre a los tipos de espacios de nombres dentro de un único modelo de aplicación.  
  
     Por ejemplo, no agregue un tipo denominado `Page` al espacio de nombres <xref:System.Web.UI.Adapters?displayProperty=nameWithType>, porque el espacio de nombres <xref:System.Web.UI?displayProperty=nameWithType> ya contiene un tipo denominado `Page`.  
  
- **Espacios de nombres de infraestructura**  
  
     Este grupo contiene espacios de nombres que rara vez se importan durante el desarrollo de aplicaciones comunes. Por ejemplo, los espacios de nombres `.Design` se usan principalmente al desarrollar herramientas de programación. Evitar conflictos con tipos en estos espacios de nombres no es crítico.  
  
- **Espacios de nombres principales**  
  
     Los espacios de nombres principales incluyen todos los espacios de `System`, excluidos los espacios de nombres de los modelos de aplicación y los espacios de nombres de la infraestructura. Los espacios de nombres principales incluyen, entre otros, `System`, `System.IO`, `System.Xml`y `System.Net`.  
  
     **X DO NOT** ofrecen a tipos de nombres que entrarían en conflicto con ningún tipo en los espacios de nombres principal.  
  
     Por ejemplo, nunca use `Stream` como un nombre de tipo. Entraría en conflicto con <xref:System.IO.Stream?displayProperty=nameWithType>, un tipo de uso muy frecuente.  
  
- **Grupos de espacios de nombres de tecnología**  
  
     Esta categoría incluye todos los espacios de nombres con los mismos dos primeros nodos de espacio de nombres `(<Company>.<Technology>*`), como `Microsoft.Build.Utilities` y `Microsoft.Build.Tasks`. Es importante que los tipos que pertenecen a una sola tecnología no entren en conflicto entre sí.  
  
     **X DO NOT** asignar nombres de tipos que entrarían en conflicto con otros tipos de una sola tecnología.  
  
     **X DO NOT** presentan conflictos de nombre de tipo entre los tipos de espacios de nombres de tecnología y un espacio de nombres del modelo de aplicación (a menos que la tecnología no está diseñada para utilizarse con el modelo de aplicación).  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
