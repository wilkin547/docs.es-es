---
title: "Mitigación: separador de ruta de acceso ZipArchiveEntry.FullName | Microsoft Docs"
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
helpviewer_keywords:
- application compatibility
- ',NET Framework application compatibility'
- .NET Framework 4.6.1
- .NET Framework 4.6.1 retargeting changes
- retargeting changes
ms.assetid: 8d575722-4fb6-49a2-8a06-f72d62dc3766
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 747c98e0fd9db95c52531b398aa33161decac294
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a>Mitigación: separador de ruta de acceso ZipArchiveEntry.FullName
A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], ha cambiado el separador de ruta de acceso utilizado en la propiedad <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=fullName> de la barra diagonal inversa ("\\") utilizada en versiones anteriores de .NET Framework a una barra diagonal ("/").   Los objetos <xref:System.IO.Compression.ZipArchiveEntry?displayProperty=fullName> se crean mediante una llamada a una de las sobrecargas del método <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=fullName>.  
  
## <a name="impact"></a>Impacto  
 El cambio trae la implementación de .NET en conformidad con la sección 4.4.17.1 de la [Especificación de formato de archivo .ZIP](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) y permite que los archivos ZIP se descompriman en sistemas distintos de Windows.  
  
 Al descomprimir un archivo zip creado por una aplicación que tiene como destino una versión anterior de .NET Framework en sistemas operativos que no son de Window,s como Macintosh, no se puede conservar la estructura de directorios. Por ejemplo, en Macintosh, crea un conjunto de archivos cuyo nombre de archivo concatena la ruta de acceso del directorio, junto con cualquier carácter de barra diagonal inversa ("\\") y el nombre de archivo. Como resultado, no se conserva la estructura de directorios de archivos descomprimidos.  
  
 El impacto de este cambio en los archivos .zip que se descomprimen en el sistema operativo Windows por las API en el espacio de nombres de .NET Framework <xref:System.IO> debe ser mínimo, ya que estas API pueden controlar sin problemas una barra diagonal ("/") o una barra diagonal inversa ("\\") como carácter separador de la ruta de acceso.  
  
## <a name="mitigation"></a>Mitigación  
 Si no desea este comportamiento, puede rechazar la adición de un valor de configuración para la sección [ \<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación. A continuación se muestra la sección `<runtime>` y el conmutador de rechazo.  
  
```  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
```  
  
 Además, las aplicaciones que tienen como destino versiones anteriores de .NET Framework pero que se ejecutan en [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y versiones posteriores pueden incluirse en este comportamiento agregando un ajuste de configuración a la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación. A continuación se muestra la sección `<runtime>` y el conmutador de inclusión.  
  
```  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
```  
  
## <a name="see-also"></a>Vea también  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)   
 [Compatibilidad de aplicaciones en 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)

