---
title: Esquema de configuración del inicio
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
ms.openlocfilehash: e5f9c9af64ff38e7c0f1f26ccab039261b052e30
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "61701520"
---
# <a name="startup-settings-schema"></a>Esquema de configuración del inicio

La configuración de inicio especifica la versión de Common Language Runtime que debe ejecutar la aplicación.  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<requiredRuntime>](requiredruntime-element.md)|Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime. Las aplicaciones compiladas con la versión de tiempo de ejecución 1,1 deben usar el **\<supportedRuntime>** elemento.|  
|[\<supportedRuntime>](supportedruntime-element.md)|Especifica qué versiones de Common Language Runtime admite la aplicación.|  
|[\<startup>](startup-element.md)|Contiene los **\<requiredRuntime>** **\<supportedRuntime>** elementos y.|  
  
## <a name="see-also"></a>Vea también

- [Esquema de los archivos de configuración](../index.md)
- [Cómo: Configurar una aplicación para que admita .NET Framework 4 o versiones posteriores](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
