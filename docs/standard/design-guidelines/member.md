---
title: Instrucciones de diseño de miembros
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
ms.openlocfilehash: cf4f1d2fee73e3e65dc4d92ea97a62f4a7e4c4e5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709275"
---
# <a name="member-design-guidelines"></a>Instrucciones de diseño de miembros
Los métodos, propiedades, eventos, constructores y campos se conocen colectivamente como miembros. Los miembros son en última instancia los medios por los que se expone la funcionalidad del marco de trabajo a los usuarios finales de un marco de trabajo.  
  
 Los miembros pueden ser virtuales o no virtuales, concretos o abstractos, estáticos o de instancia, y pueden tener distintos ámbitos de accesibilidad. Toda esta variedad proporciona una expresividad increíble, pero al mismo tiempo requiere atención en la parte del diseñador de Framework.  
  
 En este capítulo se ofrecen instrucciones básicas que deben seguirse al diseñar miembros de cualquier tipo.  
  
## <a name="in-this-section"></a>Esta sección  
 [Sobrecarga de miembro](../../../docs/standard/design-guidelines/member-overloading.md)  
 [Diseño de propiedades](../../../docs/standard/design-guidelines/property.md)  
 [Diseño de constructores](../../../docs/standard/design-guidelines/constructor.md)  
 [Diseño de eventos](../../../docs/standard/design-guidelines/event.md)  
 [Diseño de campos](../../../docs/standard/design-guidelines/field.md)  
 [Métodos de extensión](../../../docs/standard/design-guidelines/extension-methods.md)  
 [Sobrecargas de operador](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [Diseño de parámetros](../../../docs/standard/design-guidelines/parameter-design.md)  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
