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
ms.openlocfilehash: 19482199648a8fb9c4b2c796fb1ab5d62c896abc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709600"
---
# <a name="abstract-class-design"></a>Diseño de clases abstractas
**X DO NOT** definir constructores internos públicos o protegidos en tipos abstractos.  
  
 Los constructores solo deben ser públicos si los usuarios deben crear instancias del tipo. Dado que no se pueden crear instancias de un tipo abstracto, un tipo abstracto con un constructor público se ha diseñado incorrectamente y puede inducir a error a los usuarios.  
  
 **✓ DO** definir un constructor interno o protegidos en las clases abstractas.  
  
 Un constructor protegido es más común y simplemente permite que la clase base realice su propia inicialización cuando se creen subtipos.  
  
 Se puede usar un constructor interno para limitar las implementaciones concretas de la clase abstracta al ensamblado que define la clase.  
  
 **✓ DO** proporcionar al menos un tipo concreto que herede de cada clase abstracta que realiza el envío.  
  
 Esto ayuda a validar el diseño de la clase abstracta. Por ejemplo, <xref:System.IO.FileStream?displayProperty=nameWithType> es una implementación de la clase abstracta <xref:System.IO.Stream?displayProperty=nameWithType>.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
