---
title: "Mitigación: Compatibilidad con formato largo de ruta de acceso| Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cbe2d77-6e2c-4665-a6c5-7000b9ad6890
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 40b4b94ac3058dda88b44c82110d4c749566e2b2
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-long-path-support"></a>Mitigación: Compatibilidad con formato largo de ruta de acceso
A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)],  los métodos de E/S del sistema de archivos ya no muestran automáticamente un elemento <xref:System.IO.PathTooLongException> si la ruta de acceso o el nombre de archivo completo supera los 260 (o `MAX_PATH`) caracteres. En su lugar, son compatibles las rutas de acceso con formato largo de hasta 32 000 caracteres.  
  
## <a name="impact"></a>Impacto  
 Las aplicaciones recompiladas que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] y que mostraban anteriormente <xref:System.IO.PathTooLongException> automáticamente porque la ruta de acceso superaba los 260 caracteres mostraran ahora <xref:System.IO.PathTooLongException> solo si se cumplen las siguientes condiciones:  
  
-   La longitud de la ruta de acceso es superior a <xref:System.Int16.MaxValue?displayProperty=fullName> (32 767) caracteres.  
  
-   El sistema operativo devuelve `COR_E_PATHTOOLONG` o su equivalente.  
  
 El comportamiento heredado para las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y versiones anteriores es que el tiempo de ejecución muestra automáticamente un elemento < xref:System.IO.PathTooLongException > cada vez que una ruta de acceso supera los 260 caracteres.  
  
## <a name="mitigation"></a>Mitigación  
 Para las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], puede rechazar la compatibilidad con el formato largo de ruta de acceso si no la desea agregando lo siguiente a la sección [ \<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo app.config:  
  
```xml  
  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />   
</runtime>  
  
```  
  
 Para las aplicaciones que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o versiones posteriores, puede incluir la compatibilidad con el formato largo de ruta de acceso agregando lo siguiente a la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo app.config:  
  
```xml  
  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />   
</runtime>  
  
```  
  
## <a name="see-also"></a>Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
