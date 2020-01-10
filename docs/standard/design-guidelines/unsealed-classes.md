---
title: Clases no selladas
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
ms.openlocfilehash: 8a5f1142674f83b5ef77f9f7e7e3518afd475e7d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709015"
---
# <a name="unsealed-classes"></a>Clases no selladas
Las clases selladas no se pueden heredar de e impiden la extensibilidad. Por el contrario, las clases que se pueden heredar de se denominan clases no selladas.  
  
 **✓ CONSIDER** usar clases no selladas con no agrega los miembros virtuales o protegidos como una excelente manera de proporcionar económicos pero muy valiosa extensibilidad para un marco de trabajo.  
  
 A menudo, los desarrolladores quieren heredar de clases no selladas para agregar a miembros prácticos como constructores personalizados, métodos nuevos o sobrecargas de métodos. Por ejemplo, `System.Messaging.MessageQueue` no está sellado y, por lo tanto, permite a los usuarios crear colas personalizadas que tienen como valor predeterminado una ruta de acceso de cola determinada o agregar métodos personalizados que simplifican la API en escenarios específicos.  
  
 De forma predeterminada, las clases no están selladas en la mayoría de los lenguajes de programación, y también es el valor predeterminado recomendado para la mayoría de las clases de Marcos. La extensibilidad que ofrecen los tipos no sellados es muy apreciada por los usuarios del marco de trabajo y es bastante barata de proporcionar debido a costos de pruebas relativamente bajos asociados a tipos no sellados.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [Sellado](../../../docs/standard/design-guidelines/sealing.md)
