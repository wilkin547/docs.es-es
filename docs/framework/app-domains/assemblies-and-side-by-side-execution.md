---
title: ensamblados y ejecución simultánea
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution [.NET Framework]
- assemblies [.NET Framework], side-by-side execution
ms.assetid: e42036ee-7590-47d1-b884-cc856e39bd5d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b635dcbbb3a78948a2d1d1e9d4feca6f4d2ee76
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658005"
---
# <a name="assemblies-and-side-by-side-execution"></a>ensamblados y ejecución simultánea
La ejecución en paralelo es la capacidad de almacenar y ejecutar varias versiones de una aplicación o un componente en el mismo equipo. Esto significa que puede tener varias versiones del motor en tiempo de ejecución y varias versiones de aplicaciones y componentes que utilizan una misma versión del motor en tiempo de ejecución en el mismo equipo y a la vez. La ejecución en paralelo ofrece un mayor control sobre las versiones de un componente a las que se enlaza una aplicación, y sobre la versión del motor en tiempo de ejecución que utiliza una aplicación.  
  
 El hecho de que se admita el almacenamiento y la ejecución en paralelo de distintas versiones del mismo ensamblado es una parte integral de la creación de nombres seguros incluida en la infraestructura del motor en tiempo de ejecución. Debido a que el número de versión del ensamblado con nombre seguro forma parte de su identidad, el motor en tiempo de ejecución puede almacenar múltiples versiones del mismo ensamblado en la caché global de ensamblados y cargar esos ensamblados en tiempo de ejecución.  
  
 Aunque el motor en tiempo de ejecución permite crear aplicaciones en paralelos, la ejecución en paralelo no es automática. Para más información sobre la creación de aplicaciones para ejecución en paralelo, vea [Instrucciones para crear componentes para la ejecución en paralelo](../../../docs/framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).  
  
## <a name="see-also"></a>Vea también
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Ensamblados en Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
