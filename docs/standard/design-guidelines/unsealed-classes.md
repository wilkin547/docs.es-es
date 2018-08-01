---
title: Clases no selladas
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 672d36c6b888ee9a89a76d5d417a7a7e92dd8f36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571666"
---
# <a name="unsealed-classes"></a>Clases no selladas
No se puede heredar clases selladas de e impiden que extensibilidad. En cambio, las clases que se pueden heredar de se denominan clases no selladas.  
  
 **✓ CONSIDER** usar clases no selladas con no agrega los miembros virtuales o protegidos como una excelente manera de proporcionar económicos pero muy valiosa extensibilidad para un marco de trabajo.  
  
 Los desarrolladores a menudo desean heredar de clases no selladas con el fin de agregar a miembros de comodidad como constructores personalizados, nuevos métodos o las sobrecargas del método. Por ejemplo, `System.Messaging.MessageQueue` no está sellado y, por tanto, permite a los usuarios para crear colas personalizadas este comportamiento predeterminado para una ruta de acceso de cola determinado o para agregar métodos personalizados que simplifican la API de escenarios concretos.  
  
 Las clases están selladas de forma predeterminada en los lenguajes de programación más y también es el valor predeterminado recomendado para la mayoría de las clases en marcos de trabajo. La extensibilidad ofrecida por los tipos no sellados se valora mucho por los usuarios de framework y bastante económica proporcionar debido a los costos de prueba relativamente baja asociados con tipos no sellados.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [Sellado](../../../docs/standard/design-guidelines/sealing.md)
