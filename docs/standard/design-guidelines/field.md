---
title: Diseño de campos
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
ms.openlocfilehash: d39c9b95d759902d6d523b028f3db8b8da954336
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709353"
---
# <a name="field-design"></a>Diseño de campos
El principio de encapsulación es una de las nociones más importantes del diseño orientado a objetos. Este principio indica que los datos almacenados dentro de un objeto solo deben ser accesibles para ese objeto.  
  
 Una manera útil de interpretar el principio es decir que se debe diseñar un tipo para que los cambios en los campos de ese tipo (nombre o tipo cambie) sin interrumpir el código que no sea para los miembros del tipo. Esta interpretación implica inmediatamente que todos los campos deben ser privados.  
  
 Se excluyen los campos de solo lectura constantes y estáticos de esta restricción estricta, ya que nunca es necesario cambiar estos campos, casi por definición.  
  
 **X DO NOT** incluyen campos de instancia que son públicos o protegidos.  
  
 Debe proporcionar propiedades para tener acceso a los campos en lugar de hacerlos públicos o protegidos.  
  
 **✓ DO** usar los campos constantes para las constantes que no cambia nunca.  
  
 El compilador graba los valores de los campos const directamente en el código de llamada. Por lo tanto, los valores const no se pueden cambiar nunca sin el riesgo de que se interrumpa la compatibilidad.  
  
 **✓ DO** usar estáticos públicos `readonly` campos para instancias de objetos predefinidas.  
  
 Si hay instancias predefinidas del tipo, declárela como campos estáticos de solo lectura públicos del propio tipo.  
  
 **X DO NOT** asignar instancias de tipos mutables a `readonly` campos.  
  
 Un tipo mutable es un tipo con instancias que se pueden modificar una vez creadas las instancias. Por ejemplo, las matrices, la mayoría de las colecciones y las secuencias son tipos mutables, pero <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>y <xref:System.String?displayProperty=nameWithType> son inmutables. El modificador de solo lectura de un campo de tipo de referencia impide que la instancia almacenada en el campo se reemplace, pero no impide que los datos de instancia del campo se modifiquen llamando a los miembros que cambian la instancia.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
