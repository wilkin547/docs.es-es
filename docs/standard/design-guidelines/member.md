---
title: Instrucciones de diseño de miembros
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1598ac63af38f1ca3e11104bc8e1cd6323d35ed
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44190181"
---
# <a name="member-design-guidelines"></a>Instrucciones de diseño de miembros
Los métodos, propiedades, eventos, constructores y campos se conocen colectivamente como miembros. En última instancia, los miembros son el medio por el que se expone la funcionalidad del marco a los usuarios finales de un marco de trabajo.  
  
 Los miembros pueden ser virtual o no virtual, concreta o abstracto, estático o instancia y pueden tener varios ámbitos diferentes de accesibilidad. Toda esta variedad proporciona expresividad increíble, pero al mismo tiempo que requiere atención por parte del Diseñador de framework.  
  
 Este capítulo ofrece directrices básicas que se deben seguir al diseñar a los miembros de cualquier tipo.  
  
## <a name="in-this-section"></a>En esta sección  
 [Sobrecarga de miembro](../../../docs/standard/design-guidelines/member-overloading.md)  
 [Diseño de propiedades](../../../docs/standard/design-guidelines/property.md)  
 [Diseño de constructores](../../../docs/standard/design-guidelines/constructor.md)  
 [Diseño de eventos](../../../docs/standard/design-guidelines/event.md)  
 [Diseño de campos](../../../docs/standard/design-guidelines/field.md)  
 [Métodos de extensión](../../../docs/standard/design-guidelines/extension-methods.md)  
 [Sobrecargas de operador](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [Diseño de parámetros](../../../docs/standard/design-guidelines/parameter-design.md)  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
