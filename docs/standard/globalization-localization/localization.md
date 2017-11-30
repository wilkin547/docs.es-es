---
title: "Localización"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture, localization
- application development [.NET Framework], localization
- globalization [.NET Framework], localization
- code blocks
- international applications [.NET Framework], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET Framework], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4aaf2da77a1fab55cbebd6bfa05a2b1c74e5cbbd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="localization"></a>Localización
Localización es el proceso de traducción de los recursos de la aplicación en las versiones localizadas de cada referencia cultural que admita la aplicación. Debe continuar con el paso de localización después de completar la [revisión de adaptabilidad](../../../docs/standard/globalization-localization/localizability-review.md) paso para comprobar que la aplicación globalizada está preparada para la localización.  
  
 Una aplicación que está lista para la localización se divide en dos bloques conceptuales, un bloque que contiene todos los elementos de la interfaz de usuario y un bloque que contiene código ejecutable. El bloque de la interfaz de usuario contiene solo los elementos de interfaz de usuario localizables, como cadenas, mensajes de error, cuadros de diálogo, menús, recursos de objetos incrustados, y así sucesivamente para la referencia cultural neutra. El bloque de código contiene solo el código de la aplicación que va a usar todas las referencias culturales admitidas. Common language runtime admite un modelo de recursos de ensamblado satélite que separa el código ejecutable de una aplicación de sus recursos. Para obtener más información acerca de cómo implementar este modelo, vea [recursos en aplicaciones de escritorio](../../../docs/framework/resources/index.md).  
  
 Para cada versión localizada de la aplicación, agregue un nuevo ensamblado satélite que contiene el bloque de la interfaz de usuario localizada traducida en el idioma apropiado para la referencia cultural de destino. El bloque de código para todas las referencias culturales debe permanecer igual. La combinación de una versión localizada del bloque de interfaz de usuario con el bloque de código produce una versión localizada de la aplicación.  
  
 El [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] proporciona el Editor de recursos Windows Forms (Winres.exe) que permite localizar rápidamente formularios Windows Forms para las referencias culturales de destino. Para obtener información sobre el uso de esta herramienta, consulte [Winres.exe (Editor de recursos de Windows Forms)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).  
  
## <a name="see-also"></a>Vea también  
 [Globalización y localización](../../../docs/standard/globalization-localization/index.md)  
 [Revisión de localizabilidad](../../../docs/standard/globalization-localization/localizability-review.md)  
 [Globalización](../../../docs/standard/globalization-localization/globalization.md)  
 [Recursos de aplicaciones de escritorio](../../../docs/framework/resources/index.md)
