---
title: Clases no selladas
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: KrzysztofCwalina
ms.openlocfilehash: d7174de7ddf062b829672e04952c1010fcb74058
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616943"
---
# <a name="unsealed-classes"></a>Clases no selladas
Clases selladas no se puede heredar de y evitar la extensibilidad. En cambio, las clases que se pueden heredar se denominan clases no selladas.  
  
 **✓ CONSIDER** usar clases no selladas con no agrega los miembros virtuales o protegidos como una excelente manera de proporcionar económicos pero muy valiosa extensibilidad para un marco de trabajo.  
  
 Los desarrolladores a menudo desean heredar de clases no selladas con el fin de agregar a miembros de conveniencia como constructores personalizados, nuevos métodos o las sobrecargas del método. Por ejemplo, `System.Messaging.MessageQueue` está sellado y, por tanto, permite a los usuarios para crear colas personalizadas el valor predeterminado para una ruta de acceso de cola determinada o para agregar métodos personalizados que simplifican la API para escenarios específicos.  
  
 Las clases están sellados o sin sellar de forma predeterminada en los lenguajes de programación más y esto también es el valor predeterminado recomendado para la mayoría de las clases de marcos de trabajo. La extensibilidad ofrecida por los tipos no sellados es mucho más valorados por los usuarios de plataformas y bastante económica proporcionar debido a los costos de prueba relativamente baja asociados con tipos no sellados.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Diseño de extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [Sellado](../../../docs/standard/design-guidelines/sealing.md)
