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
ms.openlocfilehash: eae1c38c2383d13bfb4dab83f2fe9551970b39f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73120884"
---
# <a name="globalizing-and-localizing-net-applications"></a>Globalización y localización de aplicaciones .NET

El desarrollo de una aplicación de uso internacional, incluida una aplicación que se pueda localizar en uno o varios idiomas, implica tres pasos: globalización, revisión de localizabilidad y localización.

[Globalización](globalization.md)

Este paso conlleva diseñar y codificar una aplicación de referencias culturales e idiomáticas neutras que admita el uso de interfaces de usuario localizadas y datos regionales para todos los usuarios. Implica tomar decisiones de diseño y programación que no se basan en suposiciones específicas de la referencia cultural. Aunque una aplicación globalizada no está localizada, está diseñada y escrita para poder localizarla posteriormente en uno o varios idiomas con relativa facilidad.

[Revisión de localización](localizability-review.md)

Este paso implica revisar el código y el diseño de una aplicación para asegurarse de que puede localizarse fácilmente e identificar posibles obstáculos para la localización, además de comprobar que el código ejecutable de la aplicación está separado de los recursos. Si la fase de globalización ha sido efectiva, la revisión de localizabilidad confirmará las decisiones de diseño y codificación tomadas durante dicha fase. En la etapa de localizabilidad también puede identificarse cualquier problema pendiente, de forma que el código fuente de una aplicación no tenga que modificarse durante la fase de localización.

[Localización](localization.md)

Este paso implica personalizar una aplicación para referencias culturales o regiones específicas. Si los pasos de globalización y localizabilidad se han realizado correctamente, la localización consiste principalmente en traducir la interfaz de usuario.

La realización de estos tres pasos ofrece dos ventajas:

- No es necesario volver a plantear una aplicación ya diseñada para admitir una sola referencia cultural, por ejemplo inglés de EE. UU., de forma que admita otras referencias culturales.

- Da como resultado aplicaciones localizadas que son más estables y tienen menos errores.

En .NET se proporciona una extensa compatibilidad para desarrollar aplicaciones de uso internacional y localizadas. En concreto, muchos miembros de tipo de la biblioteca de clases de .NET contribuyen a la globalización mediante la devolución de valores que reflejan las convenciones de la referencia cultural del usuario actual o de una referencia cultural especificada. Además, .NET admite los ensamblados satélite, que facilitan el proceso de localización de una aplicación.

Para obtener más información, consulte [Globalization documentation](/globalization/) (Documentación de globalización).

## <a name="in-this-section"></a>En esta sección

[Globalización](globalization.md)

Analiza la primera fase de creación de una aplicación de uso internacional, que implica el diseño y la codificación de una aplicación con referencias culturales e idiomáticas neutras.

[Revisión de localización](localizability-review.md)

Analiza la segunda fase de creación de una aplicación localizada, que implica la identificación de obstáculos potenciales para la localización.

[Localización](localization.md)

Analiza la fase final de creación de una aplicación localizada, que implica la personalización de la interfaz de usuario de una aplicación para regiones o referencias culturales concretas.

[Operaciones de cadenas que no distinguen referencias culturales](culture-insensitive-string-operations.md)

Se describe cómo usar los métodos y clases de .NET que tienen en cuenta las referencias culturales de manera predeterminada para obtener resultados que no las tienen en cuenta.

[Prácticas recomendadas para desarrollar aplicaciones de uso internacional](best-practices-for-developing-world-ready-apps.md)

Describe los procedimientos recomendados que se deben seguir para la globalización, localización y desarrollo de aplicaciones de ASP.NET de uso internacional.

## <a name="reference"></a>Referencia

- Espacio de nombres <xref:System.Globalization?displayProperty=nameWithType>

   Contiene clases que definen datos relativos a la referencia cultural, tales como idioma, país o región, calendario, formatos de fecha, divisa y números, así como el criterio de ordenación para cadenas.

- Espacio de nombres <xref:System.Resources>

   Proporciona clases para la creación, control y utilización de recursos.

- Espacio de nombres <xref:System.Text>

   Contiene clases que representan ASCII, ANSI, Unicode y otras codificaciones de caracteres.

- [Resgen.exe (generador de archivos de recursos)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)

   Describe cómo utilizar la herramienta Resgen.exe para convertir archivos .txt y .resx (formato de recursos basados en XML) en archivos .resources binarios de Common Language Runtime.

- [Winres.exe (Editor de recursos de Windows Forms)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)

   Describe cómo usar Winres.exe para localizar formularios de Windows Forms.
