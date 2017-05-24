---
title: "Mitigación: Normalización de la ruta de acceso | Microsoft Docs"
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
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0579bb975a62e512062b10d39c2967cdcd23438f
ms.contentlocale: es-es
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-path-normalization"></a>Mitigación: Normalización de la ruta de acceso
A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], la normalización de la ruta de acceso en .NET Framework ha cambiado.  
  
## <a name="what-is-path-normalization"></a>¿Qué es la normalización de la ruta de acceso?  
 La normalización de una ruta de acceso implica la modificación de la cadena que identifica a una ruta de acceso o archivo de manera que sea conforme con una ruta de acceso válida en el sistema operativo de destino. La normalización implica normalmente:  
  
-   La canonicalización del componente y los separadores de directorios.  
  
-   La aplicación del directorio actual en una ruta de acceso relativa.  
  
-   La evaluación del directorio relativo (`.`) o el directorio principal (`..`) en una ruta de acceso.  
  
-   El recorte de caracteres especificados.  
  
## <a name="the-changes"></a>Cambios  
 A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], la normalización de la ruta de acceso ha cambiado de las siguientes maneras:  
  
-   El tiempo de ejecución se aplaza para la función [GetFullPathName](https://msdn.microsoft.com/library/windows/desktop/aa364963\(v=vs.85\).aspx) del sistema operativo con el objetivo de normalizar las rutas de acceso.  
  
-   La normalización ya no implica el recorte del final de los segmentos de directorio (como el espacio al final de un nombre de directorio).  
  
-   Compatibilidad de la sintaxis de la ruta de acceso del dispositivo con plena confianza ( incluido `\\.\`) y, para las API de E/S del archivo en mscorlib.dll, `\\?\`.  
  
-   El tiempo de ejecución o valida las rutas de acceso de la sintaxis del dispositivo.  
  
-   Es compatible el uso de la sintaxis del dispositivo para obtener acceso a los flujos de datos alternativos.  
  
## <a name="impact"></a>Impacto  
 Para aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o posterior, estos cambios están activados de forma predeterminada. Deben mejorar el rendimiento a la vez que permiten a los métodos obtener acceso a las rutas de acceso a las que no se podía obtener acceso anteriormente.  
  
 Las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y versiones anteriores, pero que se ejecutan en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o posterior, no se ven afectadas por este cambio.  
  
## <a name="mitigation"></a>Mitigación  
 Las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o posterior pueden rechazar este cambio y utilizar la normalización heredada agregando lo siguiente a la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
```  
  
 Las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] o versiones anteriores, pero que se ejecutan en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o versiones posteriores pueden habilitar los cambios en la normalización de rutas de acceso agregando la siguiente línea a la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo .configuration de la aplicación:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
```  
  
## <a name="see-also"></a>Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

