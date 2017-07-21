---
title: "Ensamblados y ejecución en paralelo | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- side-by-side execution [.NET Framework]
- assemblies [.NET Framework], side-by-side execution
ms.assetid: e42036ee-7590-47d1-b884-cc856e39bd5d
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3b78c82937c78286302adef532c451c24987da39
ms.contentlocale: es-es
ms.lasthandoff: 06/12/2017

---
# <a name="assemblies-and-side-by-side-execution"></a>ensamblados y ejecución simultánea
La ejecución en paralelo es la capacidad de almacenar y ejecutar varias versiones de una aplicación o un componente en el mismo equipo. Esto significa que puede tener varias versiones del motor en tiempo de ejecución y varias versiones de aplicaciones y componentes que utilizan una misma versión del motor en tiempo de ejecución en el mismo equipo y a la vez. La ejecución en paralelo ofrece un mayor control sobre las versiones de un componente a las que se enlaza una aplicación, y sobre la versión del motor en tiempo de ejecución que utiliza una aplicación.  
  
 El hecho de que se admita el almacenamiento y la ejecución en paralelo de distintas versiones del mismo ensamblado es una parte integral de la creación de nombres seguros incluida en la infraestructura del motor en tiempo de ejecución. Debido a que el número de versión del ensamblado con nombre seguro forma parte de su identidad, el motor en tiempo de ejecución puede almacenar múltiples versiones del mismo ensamblado en la caché global de ensamblados y cargar esos ensamblados en tiempo de ejecución.  
  
 Aunque el motor en tiempo de ejecución permite crear aplicaciones en paralelos, la ejecución en paralelo no es automática. Para más información sobre la creación de aplicaciones para ejecución en paralelo, vea [Instrucciones para crear componentes para la ejecución en paralelo](../../../docs/framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Ensamblados en Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
