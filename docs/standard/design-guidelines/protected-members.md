---
title: Miembros protegidos
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: KrzysztofCwalina
ms.openlocfilehash: 7d940f10799df2efc6c6d031781e1ef7cf777dd6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559351"
---
# <a name="protected-members"></a>Miembros protegidos
Miembros protegidos por sí solos no proporcionan ninguna extensibilidad, pero puede hacer más eficaz extensibilidad a través de la creación de subclases. Se puede usar para exponer las opciones de personalización avanzada sin complicar innecesariamente la principal interfaz pública.  
  
 Los diseñadores de Framework deben tener cuidado con los miembros protegidos porque el nombre "protegido" puede dar una falsa sensación de seguridad. Cualquier persona es capaz de subclase de una clase no sellada y los miembros acceso protegido y por lo que las mismas defensivas prácticas de codificación utilizadas para los miembros públicos se aplican a los miembros protegidos.  
  
 **✓ CONSIDER** con protegidos los miembros para la personalización avanzada.  
  
 **✓ DO** trate los miembros protegidos de clases no selladas como públicos con el fin de análisis de seguridad, documentación y compatibilidad.  
  
 Cualquier persona puede heredar de una clase y tener acceso a los miembros protegidos.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
