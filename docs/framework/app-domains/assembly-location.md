---
title: "Ubicación del ensamblado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96b3105dcd1eaf6d95269d05518e6892b42a638f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
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
