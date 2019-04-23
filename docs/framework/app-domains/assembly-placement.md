---
title: Colocación de ensamblados
ms.date: 03/30/2017
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9b8357be5b9f49569114cbc1c2942eea03696eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180185"
---
# <a name="assembly-placement"></a>Colocación de ensamblados
En la mayoría de las aplicaciones .NET Framework, los ensamblados que componen una aplicación se colocan en el directorio de la aplicación, en un subdirectorio de este último o en la caché global de ensamblados (si el ensamblado está compartido). Para reemplazar la ubicación en la que Common Language Runtime busca un ensamblado, use el [elemento \<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) en un archivo de configuración. Si el ensamblado no tiene un nombre seguro, la ubicación especificada mediante el [elemento \<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) se limita al directorio de la aplicación o a un subdirectorio de este. Si el ensamblado tiene un nombre seguro, el [elemento \<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) puede especificar cualquier ubicación en el equipo o en una red.  
  
 Se aplican reglas similares a la búsqueda de ensamblados cuando se trabaja con código no administrado o aplicaciones de interoperabilidad COM: si el ensamblado va a compartirse entre varias aplicaciones, debe instalarse en la caché global de ensamblados. Los ensamblados que se utilizan con código no administrado deben exportarse como biblioteca de tipos y registrarse. Los ensamblados utilizados por la interoperabilidad COM deben registrarse en el catálogo, aunque, en algunos casos, este registro es automático.  
  
## <a name="see-also"></a>Vea también

- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Configurar aplicaciones](../../../docs/framework/configure-apps/index.md)
- [Interoperar con código no administrado](../../../docs/framework/interop/index.md)
- [Ensamblados en Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
