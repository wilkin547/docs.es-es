---
title: Clases no selladas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f950d8de2681868fe28e09e4b51bd8156cd12e94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="unsealed-classes"></a>Clases no selladas
No se puede heredar clases selladas de e impiden que extensibilidad. En cambio, las clases que se pueden heredar de se denominan clases no selladas.  
  
 **✓ Considere la posibilidad de** usar clases no selladas con no agrega los miembros virtuales o protegidos como una excelente manera de proporcionar económicos pero muy valiosa extensibilidad para un marco de trabajo.  
  
 Los desarrolladores a menudo desean heredar de clases no selladas con el fin de agregar a miembros de comodidad como constructores personalizados, nuevos métodos o las sobrecargas del método. Por ejemplo, `System.Messaging.MessageQueue` no está sellado y, por tanto, permite a los usuarios para crear colas personalizadas este comportamiento predeterminado para una ruta de acceso de cola determinado o para agregar métodos personalizados que simplifican la API de escenarios concretos.  
  
 Las clases están selladas de forma predeterminada en los lenguajes de programación más y también es el valor predeterminado recomendado para la mayoría de las clases en marcos de trabajo. La extensibilidad ofrecida por los tipos no sellados se valora mucho por los usuarios de framework y bastante económica proporcionar debido a los costos de prueba relativamente baja asociados con tipos no sellados.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Diseñar para la extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [Sellar](../../../docs/standard/design-guidelines/sealing.md)
