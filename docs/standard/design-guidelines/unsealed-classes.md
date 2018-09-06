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
ms.openlocfilehash: ef0f1c4c9b2d1928d6f96d62ab12df9786756498
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891382"
---
# <a name="unsealed-classes"></a>Clases no selladas
Clases selladas no se puede heredar de y evitar la extensibilidad. En cambio, las clases que se pueden heredar se denominan clases no selladas.  
  
 **✓ CONSIDER** usar clases no selladas con no agrega los miembros virtuales o protegidos como una excelente manera de proporcionar económicos pero muy valiosa extensibilidad para un marco de trabajo.  
  
 Los desarrolladores a menudo desean heredar de clases no selladas con el fin de agregar a miembros de conveniencia como constructores personalizados, nuevos métodos o las sobrecargas del método. Por ejemplo, `System.Messaging.MessageQueue` está sellado y, por tanto, permite a los usuarios para crear colas personalizadas el valor predeterminado para una ruta de acceso de cola determinada o para agregar métodos personalizados que simplifican la API para escenarios específicos.  
  
 Las clases están sellados o sin sellar de forma predeterminada en los lenguajes de programación más y esto también es el valor predeterminado recomendado para la mayoría de las clases de marcos de trabajo. La extensibilidad ofrecida por los tipos no sellados es mucho más valorados por los usuarios de plataformas y bastante económica proporcionar debido a los costos de prueba relativamente baja asociados con tipos no sellados.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [Sellado](../../../docs/standard/design-guidelines/sealing.md)
