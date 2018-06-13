---
title: Contenido de los ensamblados
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- single-file assemblies
- multifile assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38c0081e5677ca65e8c730c7199ebac5d4c86261
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741833"
---
# <a name="assembly-contents"></a>Contenido de los ensamblados
En general, un ensamblado estático está formado por cuatro elementos:  
  
-   El [manifiesto del ensamblado](../../../docs/framework/app-domains/assembly-manifest.md), que contiene los metadatos del ensamblado.  
  
-   Los metadatos de tipos.  
  
-   El código de lenguaje intermedio de Microsoft (MSIL) que implementa los tipos.  
  
-   Un conjunto de recursos.  
  
 El manifiesto del ensamblado es el único elemento obligatorio, pero se necesitan o bien los tipos o bien los recursos para proporcionar al ensamblado una funcionalidad significativa.  
  
 Estos elementos se pueden agrupar en un ensamblado de varias formas. Se puede agrupar todos los elementos en un solo archivo físico, como se observa en la ilustración siguiente.  
  
 ![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover1.gif "assemblyover1")  
Ensamblado de único archivo  
  
 Alternativamente, los elementos de un ensamblado se pueden incluir en varios archivos. Estos archivos pueden ser módulos de código compilado (.netmodule), de recursos (como archivos .bmp o .jpg) u otros archivos necesarios para la aplicación. Puede crear un ensamblado de múltiples archivos para combinar módulos escritos en idiomas diferentes y optimizar la descarga de una aplicación al colocar los tipos que rara vez se utilizan en un módulo que se descargue sólo cuando sea necesario.  
  
 En la siguiente ilustración, el programador de una aplicación hipotética ha decidido separar el código de alguna utilidad en un módulo diferente y mantener un archivo de recursos grande (en este caso, una imagen .bmp) en su archivo original. .NET Framework descarga un archivo sólo cuando se hace referencia al mismo, por lo que la descarga de código se ve optimizada cuando se mantiene el código al que no se hace referencia frecuentemente en un archivo aparte de la aplicación.  
  
 ![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover2.gif "assemblyover2")  
Ensamblado de múltiples archivos  
  
> [!NOTE]
>  El sistema de archivos no vincula físicamente los archivos que forman un ensamblado de múltiples archivos. En su lugar, se vinculan a través del manifiesto del ensamblado y Common Language Runtime los administra como una unidad.  
  
 En esta ilustración, los tres archivos pertenecen a un ensamblado, como se describe en el manifiesto del ensamblado contenido en MyAssembly.dll. Para el sistema de archivos, se trata de tres archivos diferentes. Tenga en cuenta que el archivo Util.netmodule se compiló como módulo porque no contiene información de ensamblado. Cuando se creó el ensamblado, el manifiesto del ensamblado se agregó a MyAssembly.dll, lo que indica su relación con Util.netmodule y Graphic.bmp.  
  
 Actualmente, al diseñar el código fuente, se toman decisiones explícitas sobre cómo repartir la funcionalidad de una aplicación entre uno o más archivos. Al diseñar el código de .NET Framework, tomará decisiones similares sobre cómo dividir la funcionalidad en uno o más ensamblados.  
  
## <a name="see-also"></a>Vea también  
 [Ensamblados en Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [Manifiesto del ensamblado](../../../docs/framework/app-domains/assembly-manifest.md)  
 [Consideraciones de seguridad sobre ensamblados](../../../docs/framework/app-domains/assembly-security-considerations.md)
