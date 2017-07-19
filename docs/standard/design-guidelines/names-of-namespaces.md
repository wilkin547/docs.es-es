---
title: "Nombres de espacios de nombres | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "nombres [.NET Framework], conflictos"
  - "nombres [.NET Framework], espacios de nombres"
  - "nombres de tipo de conflictos"
  - "espacios de nombres [.NET Framework], nombres"
  - "nombres [.NET Framework], nombres de tipo"
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Nombres de espacios de nombres
Como con otras directrices de nomenclaturas, el objetivo al asignar nombres a espacios de nombres es crear suficiente claridad para los programadores que utilizan el marco de trabajo inmediatamente saber lo que es probable que sea el contenido del espacio de nombres. La plantilla siguiente especifica la regla general para asignar nombres a espacios de nombres:  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 Éstos son algunos ejemplos:  
  
 `Fabrikam.Math`   
 `Litware.Security`  
  
 **✓ hacer** prefijos de espacios de nombres con un nombre de compañía para evitar que los espacios de nombres de distintas compañías tengan el mismo nombre.  
  
 **✓ hacer** utilizar un nombre de producto estable, independiente de la versión en el segundo nivel de un espacio de nombres.  
  
 **X no** usar jerarquías de organización como base para los nombres en las jerarquías del espacio de nombres, nombres de grupo dentro de las organizaciones tienden a ser de corta duración. Organizar la jerarquía de espacios de nombres en torno a grupos de tecnologías relacionadas.  
  
 **✓ hacer** usar Pascal y componentes del espacio de nombres independiente con puntos \(por ejemplo, `Microsoft.Office.PowerPoint`\). Si su marca utiliza una grafía no tradicional, debería seguir la grafía definida por su marca, incluso si se desvían de los espacios de nombres normal.  
  
 **✓, considere la posibilidad de** mediante plural espacios de nombres en su caso.  
  
 Por ejemplo, utilice `System.Collections` en lugar de `System.Collection`. Nombres de marcas y acrónimos son excepciones a esta regla, sin embargo. Por ejemplo, utilice `System.IO` en lugar de `System.IOs`.  
  
 **X no** utilizar el mismo nombre para un espacio de nombres y un tipo en ese espacio de nombres.  
  
 Por ejemplo, no use `Debug` como un espacio de nombres nombre y, a continuación, proporcionar también una clase denominada `Debug` en el mismo espacio de nombres. Algunos compiladores requieren estos tipos estén completos.  
  
### Espacios de nombres y conflictos de nombre de tipo  
 **X no** incluir nombres de tipo genérico como `Element`, `Node`, `Log`, y `Message`.  
  
 Hay una probabilidad muy alta de que si se hace, dará lugar a que se escriba el nombre está en conflicto en común los escenarios. Debe calificar los nombres de tipo genérico \(`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`\).  
  
 Hay directrices específicas para evitar conflictos de nombre de tipo para las diferentes categorías de espacios de nombres.  
  
-   **Espacios de nombres del modelo de aplicación**  
  
     Espacios de nombres que pertenecen a un único modelo de aplicación muy a menudo se usan juntas, pero casi nunca se usan con los espacios de nombres de otros modelos de la aplicación. Por ejemplo, el <xref:System.Windows.Forms?displayProperty=fullName> rara vez se usa junto con el <xref:System.Web.UI?displayProperty=fullName> espacio de nombres. La siguiente es una lista de grupos de espacio de nombres del modelo de aplicación conocida:  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     **X no** dar el mismo nombre a los tipos de espacios de nombres dentro de un único modelo de aplicación.  
  
     Por ejemplo, no agregue un tipo denominado `Page` a la <xref:System.Web.UI.Adapters?displayProperty=fullName> espacio de nombres, porque el <xref:System.Web.UI?displayProperty=fullName> espacio de nombres ya contiene un tipo denominado `Page`.  
  
-   **Espacios de nombres de infraestructura**  
  
     Este grupo contiene los espacios de nombres que se importan rara vez durante el desarrollo de aplicaciones comunes. Por ejemplo, `.Design` los espacios de nombres se utilizan principalmente al desarrollo de programación de las herramientas. Evitar conflictos con los tipos de estos espacios de nombres no es crítica.  
  
-   **Espacios de nombres básicos**  
  
     Espacios de nombres básicos incluyen todos `System` espacios de nombres, excluidos los espacios de nombres de los modelos de aplicación y los espacios de nombres de la infraestructura. Espacios de nombres básicos incluyen, entre otros, `System`, `System.IO`, `System.Xml`, y `System.Net`.  
  
     **X no** asigne tipos de nombres que entren en conflicto con ningún tipo en los espacios de nombres básicos.  
  
     Por ejemplo, nunca use `Stream` como nombre de tipo. Entraría en conflicto con <xref:System.IO.Stream?displayProperty=fullName>, un tipo muy frecuente.  
  
-   **Grupos de espacio de nombres de tecnología**  
  
     Esta categoría incluye todos los espacios de nombres con los dos primeros nodos de espacio de nombres mismo `(<Company>.<Technology>*`\), como `Microsoft.Build.Utilities` y `Microsoft.Build.Tasks`. Es importante que los tipos que pertenecen a una única tecnología no entren en conflicto entre sí.  
  
     **X no** asignar nombres de tipos que entrarían en conflicto con otros tipos de una sola tecnología.  
  
     **X no** introducir conflictos de nombre de tipo entre los tipos de espacios de nombres de tecnología y un espacio de nombres del modelo de aplicación \(a menos que la tecnología no está diseñada para utilizarse con el modelo de aplicación\).  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)