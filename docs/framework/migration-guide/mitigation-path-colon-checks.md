---
title: 'Mitigación: comprobaciones de dos puntos en las rutas de acceso'
description: Obtenga información sobre los cambios realizados en .NET Framework 4.6.2 para admitir comprobaciones de la sintaxis correcta de los separadores de unidad (los dos puntos).
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
ms.openlocfilehash: 03f1c7249549aae7e3bef986c97fb5f320fbeb2f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283463"
---
# <a name="mitigation-path-colon-checks"></a>Mitigación: comprobaciones de dos puntos en las rutas de acceso

A partir de las aplicaciones que tienen como destino .NET Framework 4.6.2, se han realizado una serie de cambios para admitir rutas de acceso que anteriormente no se admitían (en términos de longitud y formato). En concreto, las comprobaciones de la sintaxis de separador de la unidad correspondiente (dos puntos) se realizan de manera más correcta.  
  
## <a name="impact"></a>Impacto  

 Estos cambios bloquean algunas rutas del identificador URI que los métodos <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> y <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> admitían anteriormente.  
  
## <a name="mitigation"></a>Mitigación  

 Para solucionar el problema de una ruta de acceso anteriormente aceptable que ya no es compatible con los métodos <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> y <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>, puede llevar a cabo el procedimiento siguiente:  
  
- Quitar manualmente el esquema de una dirección URL. Por ejemplo, quitar `file://` de una dirección URL.  
  
- Pasar el identificador URI al constructor <xref:System.Uri> y recuperar el valor de la propiedad <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType>.  
  
- Rechazar la nueva normalización de la ruta de acceso mediante el establecimiento del conmutador `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> en `true`.  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
    </runtime>  
    ```  
  
## <a name="see-also"></a>Vea también

- [Compatibilidad de aplicaciones](application-compatibility.md)
