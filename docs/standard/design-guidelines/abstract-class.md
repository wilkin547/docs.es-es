---
title: Diseño de clases abstractas
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
author: KrzysztofCwalina
ms.openlocfilehash: 6eec3bb4575b89c6476e6c3410050c705141777f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785559"
---
# <a name="abstract-class-design"></a>Diseño de clases abstractas
**X DO NOT** definir constructores internos públicos o protegidos en tipos abstractos.  
  
 Los constructores deberían ser públicos solo si los usuarios tendrán que crear instancias del tipo. Dado que no se puede crear instancias de un tipo abstracto, un tipo abstracto con un constructor público está incorrectamente diseñado y puede inducir a error a los usuarios.  
  
 **✓ DO** definir un constructor interno o protegidos en las clases abstractas.  
  
 Un constructor protegido es más común y simplemente permite que la clase base para realizar su propia inicialización cuando se crean subtipos.  
  
 Un constructor interno puede utilizarse para limitar las implementaciones concretas de la clase abstracta para el ensamblado que define la clase.  
  
 **✓ DO** proporcionar al menos un tipo concreto que herede de cada clase abstracta que realiza el envío.  
  
 Si hace esto ayuda a validar el diseño de la clase abstracta. Por ejemplo, <xref:System.IO.FileStream?displayProperty=nameWithType> es una implementación de la <xref:System.IO.Stream?displayProperty=nameWithType> clase abstracta.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
