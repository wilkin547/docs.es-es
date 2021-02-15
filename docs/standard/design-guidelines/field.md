---
description: 'Más información acerca de: Diseño de campos'
title: Diseño de campos
ms.date: 10/22/2008
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
ms.openlocfilehash: 88df60c3050035221dc65429bbd543c71d5d69b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642050"
---
# <a name="field-design"></a>Diseño de campos

El principio de encapsulación es una de las nociones más importantes del diseño orientado a objetos. Este principio indica que los datos almacenados dentro de un objeto solo deben ser accesibles para ese objeto.

 Una forma útil de interpretar el principio es decir que un tipo debe diseñarse de modo que los cambios en los campos de ese tipo (cambios de nombre o tipo) se puedan realizar sin romper el código que no sea para los miembros del tipo. Esta interpretación implica inmediatamente que todos los campos deben ser privados.

 Se excluyen los campos de solo lectura constantes y estáticos de esta restricción estricta, ya que estos campos, casi por definición, nunca tienen que cambiar.

 ❌ NO proporcione campos de instancia que sean públicos o estén protegidos.

 Debe proporcionar propiedades para tener acceso a los campos en lugar de convertirlos en públicos o protegidos.

 ✔️ DEBE usar campos constantes para las constantes que nunca cambiarán.

 El compilador graba los valores de los campos const directamente en el código de llamada. Por lo tanto, los valores const no se pueden cambiar nunca sin el riesgo de que se rompa la compatibilidad.

 ✔️ DEBE usar campos `readonly` estáticos públicos para instancias de objeto predefinidas.

 Si hay instancias predefinidas del tipo, declárelas como campos estáticos de solo lectura públicos del propio tipo.

 ❌ NO asigne instancias de tipos mutables a los campos `readonly`.

 Un tipo mutable es un tipo con instancias que se pueden modificar una vez creadas las instancias. Por ejemplo, las matrices, la mayoría de las colecciones y las secuencias son tipos mutables, pero <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType> y <xref:System.String?displayProperty=nameWithType> son inmutables. El modificador de solo lectura de un campo de tipo de referencia impide que la instancia almacenada en el campo se reemplace, pero no impide que los datos de instancia del campo se modifiquen mediante llamadas a los miembros que cambian la instancia.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](member.md)
- [Instrucciones de diseño de .NET Framework](index.md)
