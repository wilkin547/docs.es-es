---
title: "Revisión de adaptabilidad"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- world-ready applications, localizability
- application development [.NET Framework], localization
- localizability [.NET Framework]
- international applications [.NET Framework], localizability
- globalization [.NET Framework], localizability
- culture, localizability
- localization [.NET Framework], localizability
- global applications, localizability
- localizing resources
ms.assetid: 3aee2fbb-de47-4e37-8fe4-ddebb9719247
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7633c7fe9e99bde96ee108460e983eff48f1c7f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="localizability-review"></a>Revisión de adaptabilidad
La revisión de localizabilidad es un paso intermedio en el desarrollo de una aplicación de uso internacional. Comprueba que una aplicación globalizada está preparada para la localización e identifica cualquier código o los aspectos de la interfaz de usuario que requieren un tratamiento especial. Este paso también ayuda a asegurarse de que el proceso de localización no introducirá defectos funcionales en la aplicación. Cuando se han abordado todos los problemas provocados por la revisión de localizabilidad, la aplicación está preparada para la localización. Si la revisión de localizabilidad es exhaustiva, no debe tener que modificar cualquier código fuente durante el proceso de localización.  
  
 La revisión de localizabilidad consta de las tres siguientes comprobaciones:  
  
-   [¿Se implementan las recomendaciones de globalización?](#global)  
  
-   [¿Se administran correctamente culturales características?](#culture)  
  
-   [¿Ha probado la aplicación con datos internacionales?](#test)  
  
<a name="global"></a>   
## <a name="implementing-globalization-recommendations"></a>Implementar recomendaciones de globalización  
 Si ha diseñado y desarrollado su aplicación con la localización en mente, y si ha seguido las recomendaciones se describen en el [globalización](../../../docs/standard/globalization-localization/globalization.md) artículo, la revisión de localizabilidad en gran medida será un paso de aseguramiento de calidad . De lo contrario, durante esta fase debe revisar e implementar las recomendaciones para [globalización](../../../docs/standard/globalization-localization/globalization.md)y corregir los errores en el código fuente que impiden la localización.  
  
<a name="culture"></a>   
## <a name="handling-culture-sensitive-features"></a>Controlar características que tienen en cuenta la referencia cultural  
 .NET Framework no proporciona soporte técnico de programación en un número de áreas que varían enormemente según la referencia cultural. En la mayoría de los casos, tendrá que escribir código personalizado para controlar las áreas de características como la siguiente:  
  
-   Direcciones.  
  
-   Números de teléfono.  
  
-   Tamaños de papel.  
  
-   Unidades de medida usada para las longitudes, pesos, área, volumen y temperaturas. Aunque .NET Framework no ofrece compatibilidad integrada para la conversión entre unidades de medida, puede utilizar el <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType> propiedad para determinar si un determinado país o región utiliza el sistema métrico, como se muestra en el ejemplo siguiente.  
  
     [!code-csharp[Conceptual.Localizability#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.localizability/cs/ismetric1.cs#1)]
     [!code-vb[Conceptual.Localizability#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.localizability/vb/ismetric1.vb#1)]  
  
<a name="test"></a>   
## <a name="testing-your-application"></a>Probar la aplicación  
 Para localizar la aplicación, debe probarla mediante el uso de datos internacionales en versiones internacionales del sistema operativo. Aunque la mayor parte de la interfaz de usuario no se traducirá en este momento, podrá detectar problemas como los siguientes:  
  
-   Datos serializados que deserializar correctamente en las versiones de sistema operativo.  
  
-   Datos numéricos que no reflejen las convenciones de la referencia cultural actual. Por ejemplo, pueden mostrarse números con separadores de grupos inexacto, separadores decimales ni símbolos de moneda.  
  
-   Datos de fecha y hora que no reflejen las convenciones de la referencia cultural actual. Por ejemplo, los números que representan el mes y día pueden aparecer en el orden equivocado, separadores de fecha sea incorrectos o información de zona horaria puede ser incorrecta.  
  
-   Recursos que no se puede encontrar porque no ha identificado una referencia cultural predeterminada para la aplicación.  
  
-   Cadenas que se muestran en un orden inusual para la referencia cultural específica.  
  
-   Cadena comparaciones o comparaciones de igualdad que devuelven resultados inesperados.  
  
 Si ha seguido las recomendaciones de globalización al desarrollar la aplicación, controla correctamente, características de la cuenta de la referencia cultural e identificado y hace referencia a los problemas de localización que se produjeron durante las pruebas, puede continuar con el paso siguiente, [Localización](../../../docs/standard/globalization-localization/localization.md).  
  
## <a name="see-also"></a>Vea también  
 [Globalización y localización](../../../docs/standard/globalization-localization/index.md)  
 [Localización](../../../docs/standard/globalization-localization/localization.md)  
 [Globalización](../../../docs/standard/globalization-localization/globalization.md)  
 [Recursos de aplicaciones de escritorio](../../../docs/framework/resources/index.md)
