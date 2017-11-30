---
title: Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en matrices
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture-insensitive string operations, in arrays
- arrays [.NET Framework], culture-insensitive string operations
- comparer parameter
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1b4e040ed379cdbf43fbe8b2c4379fdd4dc781f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a>Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en matrices
Sobrecargas de la <xref:System.Array.Sort%2A?displayProperty=nameWithType> y <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> métodos realizan ordenaciones de cuenta de la referencia cultural predeterminada utilizando la <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> propiedad. Cuenta de la referencia cultural devuelta por estos métodos pueden variar según la referencia cultural debido a diferencias en los criterios de ordenación. Para eliminar el comportamiento de la cuenta de la referencia cultural, use una de las sobrecargas de este método que acepta un `comparer` parámetro. El `comparer` parámetro especifica el <xref:System.Collections.IComparer> implementación va a utilizar al comparar elementos de la matriz. Para el parámetro, especifique una clase comparadora invariable personalizada que utiliza <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Se proporciona un ejemplo de una clase comparadora invariable personalizada en el tema "Utilizar la clase SortedList" de la [realizar operaciones de cadena cuenta las referencias culturales en colecciones](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) tema.  
  
 **Tenga en cuenta** pasar **CultureInfo.InvariantCulture** a una comparación método lleva a cabo una comparación de la referencia cultural. Si embargo, no provoca una comparación no lingüística, por ejemplo, para las rutas de acceso de archivo, las claves del Registro y las variables de entorno. Tampoco admite las decisiones de seguridad basadas en el resultado de la comparación. Para una comparación no lingüística o soporte técnico para tomar decisiones de seguridad basada en el resultado, la aplicación debe utilizar un método de comparación que acepta un <xref:System.StringComparison> valor. A continuación, debe pasar la aplicación <xref:System.StringComparison.Ordinal>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>  
 <xref:System.Collections.IComparer>  
 [Realizar operaciones de cadenas que no distinguen entre referencias culturales](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
