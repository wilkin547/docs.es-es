---
title: Instrucciones de diseño de miembros
description: Obtenga información sobre las directrices de diseño de miembros en .NET. Los miembros incluyen métodos, propiedades, eventos, constructores y campos.
ms.date: 10/22/2008
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
ms.openlocfilehash: 5070f45beccd89d6f051f1b1d8345390e915d471
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706598"
---
# <a name="member-design-guidelines"></a>Instrucciones de diseño de miembros

Los métodos, propiedades, eventos, constructores y campos se conocen colectivamente como miembros. Los miembros son en última instancia los medios por los que se expone la funcionalidad del marco de trabajo a los usuarios finales de un marco de trabajo.  
  
 Los miembros pueden ser virtuales o no virtuales, concretos o abstractos, estáticos o de instancia, y pueden tener distintos ámbitos de accesibilidad. Toda esta variedad proporciona una expresividad increíble, pero al mismo tiempo requiere atención en la parte del diseñador de Framework.  
  
 En este capítulo se ofrecen instrucciones básicas que deben seguirse al diseñar miembros de cualquier tipo.  
  
## <a name="in-this-section"></a>En esta sección  

 [Sobrecarga de miembros](member-overloading.md)  
 [Diseño de propiedades](property.md)  
 [Diseño del constructor](constructor.md)  
 [Diseño de eventos](event.md)  
 [Diseño de campos](field.md)  
 [Métodos de extensión](extension-methods.md)  
 [Sobrecargas de operador](operator-overloads.md)  
 [Diseño de parámetros](parameter-design.md)  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Consulte también

- [Directrices de diseño de marco](index.md)
