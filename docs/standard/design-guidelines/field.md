---
title: Diseño de campos
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
author: KrzysztofCwalina
ms.openlocfilehash: 34c5a163e545b78c188f37b2819962b4c7c56f80
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144356"
---
# <a name="field-design"></a>Diseño de campos
El principio de encapsulación es una de las nociones más importantes en el diseño orientado a objetos. Este principio afirma que los datos almacenados dentro de un objeto deben ser accesibles solo a ese objeto.  
  
 Una manera útil para interpretar el principio es decir que un tipo debe diseñarse para que se pueden realizar cambios a los campos de ese tipo (cambios de nombre o tipo) sin interrumpir el código que no sea para los miembros del tipo. Esta interpretación inmediatamente implica que todos los campos deben ser privados.  
  
 Campos de solo lectura estáticos y constantes se excluyen de esta restricción estricta, porque esos campos, casi por definición, nunca deben cambiar.  
  
 **X DO NOT** incluyen campos de instancia que son públicos o protegidos.  
  
 Debe proporcionar propiedades para tener acceso a los campos en lugar de hacerlos públicos o protegidos.  
  
 **✓ DO** usar los campos constantes para las constantes que no cambia nunca.  
  
 El compilador quema los valores de campos constantes directamente en el código de llamada. Por lo tanto, los valores const nunca pueden cambiarse sin correr el riesgo de interrumpir la compatibilidad.  
  
 **✓ DO** usar estáticos públicos `readonly` campos para instancias de objetos predefinidas.  
  
 Si no hay instancias predefinidas del tipo, declarar campos estáticos de sólo lectura como públicos del tipo en Sí.  
  
 **X DO NOT** asignar instancias de tipos mutables a `readonly` campos.  
  
 Un tipo mutable es un tipo con instancias que puede modificarse una vez que se crean instancias. Por ejemplo, secuencias, mayoría de las colecciones y matrices son tipos mutables, pero <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, y <xref:System.String?displayProperty=nameWithType> todos son inmutables. El modificador de solo lectura en un campo de tipo de referencia impide que la instancia almacenada en el campo que se reemplace, pero no impide que los datos de instancia del campo que se va a modificar llamando a los miembros que cambiar la instancia.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)  
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
