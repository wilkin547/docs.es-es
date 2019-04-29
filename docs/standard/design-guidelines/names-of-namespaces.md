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
author: KrzysztofCwalina
ms.openlocfilehash: 0099c5c8a863023099b377e139461606de3e1e1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940990"
---
# <a name="names-of-namespaces"></a>Nombres de espacios de nombres
Como con otras directrices de nomenclatura, el objetivo al asignar nombres a los espacios de nombres está creando una mayor claridad suficiente para los programadores que utilizan el marco de trabajo saber inmediatamente lo que es probable que sea el contenido del espacio de nombres. La plantilla siguiente especifica la regla general para asignar nombres a los espacios de nombres:  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 Estos son algunos ejemplos:  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 **✓ DO** prefijos de espacios de nombres con un nombre de compañía para evitar que los espacios de nombres de distintas compañías que tengan el mismo nombre.  
  
 **✓ DO** utilizar un nombre de producto estable, independiente de la versión en el segundo nivel de un nombre de espacio de nombres.  
  
 **X DO NOT** usar jerarquías organizativas como base para los nombres en las jerarquías de espacio de nombres, porque los nombres de grupo dentro de las organizaciones tienden a ser de corta duración. Organizar la jerarquía de espacios de nombres en torno a grupos de tecnologías relacionadas.  
  
 **✓ DO** usar Pascal y componentes del espacio de nombres independiente con puntos (por ejemplo, `Microsoft.Office.PowerPoint`). Si su marca utiliza una grafía no tradicional, debe seguir las mayúsculas y minúsculas definida por su marca, incluso si se desvían de espacio de nombres normal de mayúsculas y minúsculas.  
  
 **✓ CONSIDER** recurriendo plural espacios de nombres en su caso.  
  
 Por ejemplo, use `System.Collections` en lugar de `System.Collection`. Nombres y acrónimos son excepciones a esta regla, sin embargo. Por ejemplo, use `System.IO` en lugar de `System.IOs`.  
  
 **X DO NOT** usar el mismo nombre para un espacio de nombres y un tipo en ese espacio de nombres.  
  
 Por ejemplo, no use `Debug` como un espacio de nombres que asigne un nombre y, a continuación, proporcione también una clase denominada `Debug` en el mismo espacio de nombres. Algunos compiladores requieren ser un nombre completo de dichos tipos.  
  
### <a name="namespaces-and-type-name-conflicts"></a>Espacios de nombres y los conflictos de nombre de tipo  
 **X DO NOT** introducir los nombres de tipos genéricos como `Element`, `Node`, `Log`, y `Message`.  
  
 Hay una probabilidad muy alta de que al hacerlo, por lo que dará lugar a que se escriba el nombre entra en conflicto en común los escenarios. Se deben calificar los nombres de tipo genérico (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).  
  
 Hay instrucciones específicas para evitar conflictos de nombre de tipo para las diferentes categorías de espacios de nombres.  
  
- **Espacios de nombres del modelo de aplicación**  
  
     Los espacios de nombres que pertenecen a un único modelo de aplicación muy a menudo se usan juntos, pero casi nunca se usan con espacios de nombres de otros modelos de aplicación. Por ejemplo, el <xref:System.Windows.Forms?displayProperty=nameWithType> muy rara vez se utiliza el espacio de nombres junto con el <xref:System.Web.UI?displayProperty=nameWithType> espacio de nombres. La siguiente es una lista de grupos de espacio de nombres del modelo de aplicación conocida:  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     **X DO NOT** dar el mismo nombre a los tipos de espacios de nombres dentro de un único modelo de aplicación.  
  
     Por ejemplo, no agregue un tipo denominado `Page` a la <xref:System.Web.UI.Adapters?displayProperty=nameWithType> espacio de nombres, porque el <xref:System.Web.UI?displayProperty=nameWithType> espacio de nombres ya contiene un tipo denominado `Page`.  
  
- **Espacios de nombres de la infraestructura**  
  
     Este grupo contiene los espacios de nombres que se importan rara vez durante el desarrollo de aplicaciones comunes. Por ejemplo, `.Design` espacios de nombres se utilizan principalmente al desarrollo de programación de las herramientas. Evitar conflictos con los tipos de estos espacios de nombres no es fundamental.  
  
- **Espacios de nombres básicos**  
  
     Espacios de nombres básicos incluyen todos `System` espacios de nombres, excepto los espacios de nombres de los modelos de aplicación y los espacios de nombres de la infraestructura. Espacios de nombres básicos se incluyen, entre otros, `System`, `System.IO`, `System.Xml`, y `System.Net`.  
  
     **X DO NOT** ofrecen a tipos de nombres que entrarían en conflicto con ningún tipo en los espacios de nombres principal.  
  
     Por ejemplo, nunca use `Stream` como un nombre de tipo. Entraría en conflicto con <xref:System.IO.Stream?displayProperty=nameWithType>, un tipo muy frecuente.  
  
- **Grupos de espacio de nombres de tecnología**  
  
     Esta categoría incluye todos los espacios de nombres con los dos primeros nodos de espacio de nombres mismo `(<Company>.<Technology>*`), como `Microsoft.Build.Utilities` y `Microsoft.Build.Tasks`. Es importante que los tipos que pertenecen a una única tecnología no entran en conflicto entre sí.  
  
     **X DO NOT** asignar nombres de tipos que entrarían en conflicto con otros tipos de una sola tecnología.  
  
     **X DO NOT** presentan conflictos de nombre de tipo entre los tipos de espacios de nombres de tecnología y un espacio de nombres del modelo de aplicación (a menos que la tecnología no está diseñada para utilizarse con el modelo de aplicación).  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
