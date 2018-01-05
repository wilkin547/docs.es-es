---
title: "Diseño de campos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ccced2c9e816122d770f43056c36ab4a6d510fde
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="field-design"></a>Diseño de campos
El principio de encapsulación es uno de los conceptos más importantes en el diseño orientado a objetos. Este principio indica que los datos almacenados dentro de un objeto deben estar accesibles sólo para ese objeto.  
  
 Una forma útil de interpretar el principio consiste en indicar que un tipo debe diseñarse de modo que se pueden realizar cambios en los campos de ese tipo (cambios de nombre o tipo) sin interrumpir el código distinto para los miembros del tipo. Esta interpretación inmediatamente implica que todos los campos deben ser privados.  
  
 Campos de solo lectura de constantes y estáticas se excluirán de esta restricción estricta, porque esos campos, casi por definición, nunca deben cambiar.  
  
 **X DO NOT** incluyen campos de instancia que son públicos o protegidos.  
  
 Debe proporcionar propiedades para tener acceso a campos en lugar de hacerlos público o protegido.  
  
 **✓ HACER** usar los campos constantes para las constantes que no cambia nunca.  
  
 El compilador lo grabe los valores de los campos const directamente en el código de llamada. Por lo tanto, los valores constantes nunca se pueden cambiar sin el riesgo de interrumpir la compatibilidad.  
  
 **✓ HACER** usar estáticos públicos `readonly` campos para instancias de objetos predefinidas.  
  
 Si no hay instancias predefinidas del tipo, declárelos como public campos estáticos de sólo lectura del tipo en Sí.  
  
 **X DO NOT** asignar instancias de tipos mutables a `readonly` campos.  
  
 Un tipo que mutable es un tipo con instancias que pueden modificarse después de que se crean instancias. Por ejemplo, secuencias, mayoría de las colecciones y matrices son tipos mutables, pero <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, y <xref:System.String?displayProperty=nameWithType> todos son inmutables. El modificador de solo lectura en un campo de tipo de referencia impide que la instancia almacenada en el campo se reemplace, pero no impide que los datos de instancia del campo que se está modificando los miembros que realiza la llamada del cambio de la instancia.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
