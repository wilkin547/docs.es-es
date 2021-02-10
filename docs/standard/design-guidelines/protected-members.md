---
description: 'Más información acerca de: Miembros protegidos'
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
ms.openlocfilehash: 5860828a5a469c77fbee001d01460a488fda4edf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731765"
---
# <a name="protected-members"></a>Miembros protegidos

Los miembros protegidos por sí mismos no proporcionan ninguna extensibilidad, pero pueden aumentar la eficacia de la extensibilidad a través de la creación de subclases. Se pueden usar para exponer opciones de personalización avanzadas sin complicar innecesariamente la interfaz pública principal.

 Los diseñadores de marcos deben tener cuidado con los miembros protegidos, ya que el nombre "protegido" puede dar una falsa sensación de seguridad. Cualquier persona puede crear subclases de una clase no sellada y tener acceso a miembros protegidos, por lo que todas las mismas prácticas de codificación defensivas que se usan para los miembros públicos se aplican a los miembros protegidos.

 ✔️ CONSIDERE la posibilidad de usar miembros protegidos para la personalización avanzada.

 ✔️ TRATE los miembros protegidos de clases no selladas como públicos con fines de análisis de compatibilidad, documentación y seguridad.

 Cualquier persona puede heredar de una clase y obtener acceso a los miembros protegidos.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](index.md)
- [Diseñar extensibilidad](designing-for-extensibility.md)
