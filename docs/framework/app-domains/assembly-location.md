---
title: Ubicación del ensamblado
ms.date: 03/30/2017
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91fc7cf6ea66952fa5770ce73ecb1a8c129a9a2d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="assembly-location"></a>Ubicación del ensamblado
La ubicación de un ensamblado determina si Common Language Runtime lo encontrará cuando se haga referencia a él y también puede determinar si el ensamblado se puede compartir con otros ensamblados. Puede implementar un ensamblado en las ubicaciones siguientes:  
  
-   El directorio de la aplicación o subdirectorios de este.  
  
     Esta es la ubicación más común para implementar un ensamblado. Los subdirectorios del directorio raíz de la aplicación pueden basarse en un idioma o referencia cultural. Si un ensamblado tiene información en el atributo de referencia cultural, debe estar en un subdirectorio bajo el directorio de la aplicación con el nombre de esa referencia cultural.  
  
-   La caché global de ensamblados.  
  
     Se trata de una caché de código del equipo que se instala donde está instalado Common Language Runtime. En la mayoría de los casos, si se piensa compartir un ensamblado entre varias aplicaciones, debe implementarse en la caché global de ensamblados.  
  
-   Un servidor HTTP.  
  
     Un ensamblado implementado en un servidor HTTP debe tener un nombre seguro. Debe apuntar al ensamblado en la sección de código base del archivo de configuración de la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Creación de ensamblados](../../../docs/framework/app-domains/create-assemblies.md)  
 [Caché global de ensamblados](../../../docs/framework/app-domains/gac.md)  
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)
