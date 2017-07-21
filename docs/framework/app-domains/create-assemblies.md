---
title: Crear ensamblados | Microsoft Docs
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
- assemblies [.NET Framework], multifile
- single-file assemblies
- assemblies [.NET Framework], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c131e82e2312e2c1b7fe1b6b2b6d0a6dfb626209
ms.contentlocale: es-es
ms.lasthandoff: 06/02/2017

---
# <a name="creating-assemblies"></a>Crear ensamblados
Para crear ensamblados de un solo archivo o de varios archivos, se puede usar un IDE, como [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], o los compiladores y las herramientas que proporciona el [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]. El ensamblado más sencillo es un solo archivo que tiene un nombre simple y se carga en un solo dominio de aplicación. Este ensamblado no se somete a la comprobación de versión y no pueden hacer referencia a él otros ensamblados fuera del directorio de la aplicación. Para desinstalar la aplicación que se compone del ensamblado, basta con eliminar el directorio en el que reside. Muchos desarrolladores solo necesitan un ensamblado de estas características para implementar una aplicación.  
  
 Puede crear un ensamblado de varios archivos a partir de varios módulos de código y archivos de recursos. También puede crear un ensamblado que compartan varias aplicaciones. Un ensamblado compartido debe tener un nombre seguro y puede implementarse en la caché global de ensamblados.  
  
 Existen varias opciones al agrupar módulos de código y recursos en ensamblados, en función de los factores siguientes:  
  
-   Control de versiones  
  
     Agrupar módulos con la misma información de versión.  
  
-   Implementación  
  
     Agrupar módulos de código y recursos compatibles con el modelo de implementación.  
  
-   Reutilización  
  
     Agrupar módulos si se pueden usar juntos lógicamente con el mismo fin. Por ejemplo, un ensamblado formado por tipos y clases que se usan con poca frecuencia para el mantenimiento de programas puede colocarse en el mismo ensamblado. Además, los tipos que está previsto compartir con varias aplicaciones deben agruparse en un ensamblado y el ensamblado debe firmarse con un nombre seguro.  
  
-   Seguridad  
  
     Agrupar módulos que contienen tipos que requieren los mismos permisos de seguridad.  
  
-   Ámbito  
  
     Agrupar módulos que contienen tipos cuya visibilidad se debe restringir al mismo ensamblado.  
  
 Deben tenerse en cuenta consideraciones especiales cuando los ensamblados de Common Language Runtime se ponen a disposición de aplicaciones COM no administradas. Para obtener más información sobre cómo trabajar con código no administrado, vea [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md) (Exponer componentes de .NET Framework en COM).  
  
## <a name="see-also"></a>Vea también  
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)   
 [Versiones de los ensamblados](../../../docs/framework/app-domains/assembly-versioning.md)   
 [Cómo: Compilar un ensamblado de un solo archivo](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)   
 [Cómo: Compilar un ensamblado de varios archivos](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)   
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Ensamblados de múltiples archivos](../../../docs/framework/app-domains/multifile-assemblies.md)
