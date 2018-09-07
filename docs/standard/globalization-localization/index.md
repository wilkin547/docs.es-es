---
title: Globalización y localización de aplicaciones .NET
ms.date: 06/08/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- international applications [.NET]
- globalization [.NET], encoding
- global applications
- internationalization
- world-ready applications
- application development [.NET], globalization
- multilingual application development
ms.assetid: 9a59696b-d89b-45bd-946d-c75da4732d02
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 653a39d1e217d0478ff7c9b01c6ac146fe6b5fac
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43873752"
---
# <a name="globalizing-and-localizing-net-applications"></a>Globalización y localización de aplicaciones .NET
El desarrollo de una [aplicación de uso internacional](https://msdn.microsoft.com/goglobal/bb978433.aspx), incluida una aplicación que se pueda localizar en uno o varios idiomas, implica tres pasos: globalización, revisión de localizabilidad y localización.  
  
 [Globalización](../../../docs/standard/globalization-localization/globalization.md)  
 Este paso conlleva diseñar y codificar una aplicación de referencias culturales e idiomáticas neutras que admita el uso de interfaces de usuario localizadas y datos regionales para todos los usuarios. Implica tomar decisiones de diseño y programación que no se basan en suposiciones específicas de la referencia cultural. Aunque una aplicación globalizada no está localizada, está diseñada y escrita para poder localizarla posteriormente en uno o varios idiomas con relativa facilidad.  
  
 [Revisión de localización](../../../docs/standard/globalization-localization/localizability-review.md)  
 Este paso implica revisar el código y el diseño de una aplicación para asegurarse de que puede localizarse fácilmente e identificar posibles obstáculos para la localización, además de comprobar que el código ejecutable de la aplicación está separado de los recursos. Si la fase de globalización ha sido efectiva, la revisión de localizabilidad confirmará las decisiones de diseño y codificación tomadas durante dicha fase. En la etapa de localizabilidad también puede identificarse cualquier problema pendiente, de forma que el código fuente de una aplicación no tenga que modificarse durante la fase de localización.  
  
 [Localización](../../../docs/standard/globalization-localization/localization.md)  
 Este paso implica personalizar una aplicación para referencias culturales o regiones específicas. Si los pasos de globalización y localizabilidad se han realizado correctamente, la localización consiste principalmente en traducir la interfaz de usuario.  
  
 La realización de estos tres pasos ofrece dos ventajas:  
  
-   No es necesario volver a plantear una aplicación ya diseñada para admitir una sola referencia cultural, por ejemplo inglés de EE. UU., de forma que admita otras referencias culturales.  
  
-   Da como resultado aplicaciones localizadas que son más estables y tienen menos errores.  
  
 En .NET se proporciona una extensa compatibilidad para desarrollar aplicaciones de uso internacional y localizadas. En concreto, muchos miembros de tipo de la biblioteca de clases de .NET contribuyen a la globalización mediante la devolución de valores que reflejan las convenciones de la referencia cultural del usuario actual o de una referencia cultural especificada. Además, .NET admite los ensamblados satélite, que facilitan el proceso de localización de una aplicación.  
  
 Para obtener más información, consulte [Globalization documentation](/globalization/) (Documentación de globalización).  
  
## <a name="in-this-section"></a>En esta sección  
 [Globalización](../../../docs/standard/globalization-localization/globalization.md)  
 Analiza la primera fase de creación de una aplicación de uso internacional, que implica el diseño y la codificación de una aplicación con referencias culturales e idiomáticas neutras.  
  
 [Revisión de localización](../../../docs/standard/globalization-localization/localizability-review.md)  
 Analiza la segunda fase de creación de una aplicación localizada, que implica la identificación de obstáculos potenciales para la localización.  
  
 [Localización](../../../docs/standard/globalization-localization/localization.md)  
 Analiza la fase final de creación de una aplicación localizada, que implica la personalización de la interfaz de usuario de una aplicación para regiones o referencias culturales concretas.  
  
 [Operaciones de cadenas que no distinguen referencias culturales](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 Se describe cómo usar los métodos y clases de .NET que tienen en cuenta las referencias culturales de manera predeterminada para obtener resultados que no las tienen en cuenta.  
  
 [Prácticas recomendadas para desarrollar aplicaciones de uso internacional](../../../docs/standard/globalization-localization/best-practices-for-developing-world-ready-apps.md)  
 Describe los procedimientos recomendados que se deben seguir para la globalización, localización y desarrollo de aplicaciones de ASP.NET de uso internacional.  
  
## <a name="reference"></a>Referencia  
 Espacio de nombres <xref:System.Globalization?displayProperty=nameWithType>  
 Contiene clases que definen datos relativos a la referencia cultural, tales como idioma, país o región, calendario, formatos de fecha, divisa y números, así como el criterio de ordenación para cadenas.  
  
 Espacio de nombres <xref:System.Resources>  
 Proporciona clases para la creación, control y utilización de recursos.  
  
 Espacio de nombres <xref:System.Text>  
 Contiene clases que representan ASCII, ANSI, Unicode y otras codificaciones de caracteres.  
  
 [Resgen.exe (generador de archivos de recursos)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)  
 Describe cómo utilizar la herramienta Resgen.exe para convertir archivos .txt y .resx (formato de recursos basados en XML) en archivos .resources binarios de Common Language Runtime.  
  
 [Winres.exe (Editor de recursos de Windows Forms)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)  
 Describe cómo usar Winres.exe para localizar formularios de Windows Forms.
