---
title: Miembros protegidos
ms.date: 10/22/2008
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
ms.openlocfilehash: 3cc2ab3e605cfb5382f107dead0c95495858fc6b
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828730"
---
# <a name="protected-members"></a>Miembros protegidos
Los miembros protegidos por sí mismos no proporcionan ninguna extensibilidad, pero pueden realizar la extensibilidad mediante subclases más eficaces. Se pueden usar para exponer opciones de personalización avanzadas sin complicar innecesariamente la interfaz pública principal.

 Los diseñadores de Marcos deben tener cuidado con los miembros protegidos porque el nombre "protegido" puede dar una sensación falsa de seguridad. Cualquier persona puede subclase de una clase no sellada y tener acceso a miembros protegidos, por lo que todas las mismas prácticas de codificación defensivas que se usan para los miembros públicos se aplican a los miembros protegidos.

 ✔️ considere la posibilidad de usar miembros protegidos para la personalización avanzada.

 ✔️ tratar los miembros protegidos de clases no selladas como públicos con el fin de la seguridad, la documentación y el análisis de compatibilidad.

 Cualquier persona puede heredar de una clase y obtener acceso a los miembros protegidos.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Directrices de diseño de marco](index.md)
- [Diseñar extensibilidad](designing-for-extensibility.md)
