---
title: 'Mitigación: separador de ruta de acceso ZipArchiveEntry.FullName'
ms.date: 03/30/2017
helpviewer_keywords:
- application compatibility
- ',NET Framework application compatibility'
- .NET Framework 4.6.1
- .NET Framework 4.6.1 retargeting changes
- retargeting changes
ms.assetid: 8d575722-4fb6-49a2-8a06-f72d62dc3766
ms.openlocfilehash: 3f6c7f258fd5dbf01db4d79b73b88ddd7484f9b2
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102624"
---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a>Mitigación: separador de ruta de acceso ZipArchiveEntry.FullName

A partir de las aplicaciones que tienen como destino .NET Framework 4.6.1, el separador de ruta de acceso utilizado en la propiedad <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> ha cambiado de la barra diagonal inversa ("\\") utilizada en versiones anteriores de .NET Framework a una barra diagonal ("/"). Los objetos <xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType> se crean al llamar a una de las sobrecargas del método <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType>.  
  
## <a name="impact"></a>Impacto  
 El cambio trae la implementación de .NET en conformidad con la sección 4.4.17.1 de la [Especificación de formato de archivo .ZIP](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) y permite que los archivos ZIP se descompriman en sistemas distintos de Windows.  
  
 Al descomprimir un archivo ZIP creado por una aplicación que tiene como destino una versión anterior de .NET Framework en sistemas operativos que no son de Windows, como MacOS, no se puede conservar la estructura de directorios. Por ejemplo, en MacOS, crea un conjunto de archivos cuyo nombre de archivo concatena la ruta de acceso del directorio, junto con cualquier carácter de barra diagonal inversa ("\\") y el nombre de archivo. Como resultado, no se conserva la estructura de directorios de archivos descomprimidos.  
  
 El impacto de este cambio en los archivos ZIP que se descomprimen en el sistema operativo Windows mediante interfaces API en el espacio de nombres <xref:System.IO> de .NET Framework debe ser mínimo, ya que estas API pueden controlar sin problemas una barra diagonal ("/") o una barra diagonal inversa ("\\") como carácter separador de la ruta de acceso.  
  
## <a name="mitigation"></a>Mitigación  
 Si no desea este comportamiento, puede rechazar la adición de un valor de configuración para la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación. A continuación se muestra la sección `<runtime>` y el conmutador de rechazo.  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
```  
  
 Además, las aplicaciones que tienen como destino versiones anteriores de .NET Framework pero que se ejecutan en .NET Framework 4.6.1 y versiones posteriores pueden participar en este comportamiento si se agrega una opción de configuración a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación. A continuación se muestra la sección `<runtime>` y el conmutador de inclusión.  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
```  
  
## <a name="see-also"></a>Vea también

- [Compatibilidad de aplicaciones](application-compatibility.md)
