---
description: 'Más información acerca de: Clases no selladas'
title: Clases no selladas
ms.date: 10/22/2008
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
ms.openlocfilehash: 6fe30c3a2ef8df6b983d857b9502805e90ab83dc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641829"
---
# <a name="unsealed-classes"></a>Clases no selladas

No se puede heredar de clases e impiden la extensibilidad. Por el contrario, las clases de las que se puede heredar se denominan clases no selladas.

 ✔️ PLANTÉESE la posibilidad de usar clases no selladas sin miembros virtuales o protegidos agregados como una excelente manera de proporcionar extensibilidad económica pero mucho más apreciada a un marco.

 A menudo, los desarrolladores quieren heredar de clases no selladas para agregar a miembros prácticos, como constructores personalizados, métodos nuevos o sobrecargas de métodos. Por ejemplo, `System.Messaging.MessageQueue` no está sellado y, por lo tanto, permite a los usuarios crear colas personalizadas que tienen como valor predeterminado una ruta de acceso de cola determinada o agregar métodos personalizados que simplifican la API en escenarios específicos.

 De forma predeterminada, las clases no están selladas en la mayoría de los lenguajes de programación y esta es también la situación predeterminada recomendada para la mayoría de las clases de los marcos. La extensibilidad que ofrecen los tipos no sellados es muy apreciada por los usuarios del marco y es bastante barata de proporcionar debido a costos de pruebas relativamente bajos asociados a tipos no sellados.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](index.md)
- [Diseñar extensibilidad](designing-for-extensibility.md)
- [Sellar](sealing.md)
