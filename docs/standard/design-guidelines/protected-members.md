---
title: Miembros protegidos
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d4d334d9809f374442e19807d3b249a17a1d9df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571090"
---
# <a name="protected-members"></a>Miembros protegidos
Miembros protegidos por sí mismos no proporcionan ninguna extensibilidad, pero puede hacer más eficaz extensibilidad a través de la creación de subclases. Puede utilizar para exponer las opciones de personalización avanzada sin complicar innecesariamente la principal interfaz pública.  
  
 Diseñadores de Framework hay que tener cuidado con los miembros protegidos porque el nombre "protegido" puede dar una falsa sensación de seguridad. Cualquier persona es capaz de subclase de una clase no sellada y protegidos de obtener acceso a miembros y, por lo que las mismas estable prácticas de codificación utilizadas para los miembros públicos se aplican a los miembros protegidos.  
  
 **✓ Considere la posibilidad de** con protegidos los miembros para la personalización avanzada.  
  
 **✓ HACER** trate los miembros protegidos de clases no selladas como públicos con el fin de análisis de seguridad, documentación y compatibilidad.  
  
 Cualquiera puede heredar de una clase y tener acceso a los miembros protegidos.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
