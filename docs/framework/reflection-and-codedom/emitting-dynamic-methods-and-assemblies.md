---
title: "Emitir métodos y ensamblados dinámicos | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
ms.assetid: 8e8e2631-62fd-40e7-a8ee-0039b06749bc
caps.latest.revision: 18
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d8e4c5bb677be7e20f6571ea6eb53831027ade27
ms.contentlocale: es-es
ms.lasthandoff: 06/02/2017

---
# <a name="emitting-dynamic-methods-and-assemblies"></a>Emitir métodos y ensamblados dinámicos
En esta sección se describe un conjunto de tipos administrados del espacio de nombres <xref:System.Reflection.Emit> que permite a un compilador o una herramienta emitir metadatos y el Lenguaje Intermedio de Microsoft (MSIL) en tiempo de ejecución y, opcionalmente, generar un archivo portable ejecutable (PE) en el disco. Los motores de scripts y los compiladores son los principales usuarios de este espacio de nombres. En esta sección, la funcionalidad proporcionada por el espacio de nombres <xref:System.Reflection.Emit> se conoce como emisión de la reflexión.  
  
 La emisión de la reflexión permite lo siguiente:  
  
-   Definir métodos globales ligeros en tiempo de ejecución, usando la clase <xref:System.Reflection.Emit.DynamicMethod>, y ejecutarlos usando delegados.  
  
-   Definir ensamblados en tiempo de ejecución y, después, ejecutarlos o guardarlos en el disco.  
  
-   Definir ensamblados en tiempo de ejecución, ejecutarlos y, después, descargarlos y permitir la recolección de elementos no utilizados para reclamar sus recursos.  
  
-   Definir módulos en nuevos ensamblados en tiempo de ejecución y, después, ejecutarlos o guardarlos en el disco.  
  
-   Definir tipos en módulos en tiempo de ejecución, crear instancias de estos tipos y llamar a sus métodos.  
  
-   Definir información simbólica para módulos definidos que puedan usar herramientas como depuradores y generadores de perfiles de código.  
  
 Además de los tipos administrados del espacio de nombres <xref:System.Reflection.Emit>, hay interfaces de metadatos no administradas que se describen en la documentación de referencia [Interfaces de metadatos](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md). La emisión de reflexión administrada proporciona una comprobación más estricta de los errores semánticos y un mayor nivel de abstracción de los metadatos que las interfaces de metadatos no administradas.  
  
 Otro recurso útil para trabajar con metadatos y MSIL es la documentación de Common Language Infrastructure (CLI), especialmente la sección II sobre la definición y la semántica de los metadatos y la partición III sobre el conjunto de instrucciones de CIL. La documentación está disponible en línea en [MSDN](http://go.microsoft.com/fwlink/?LinkID=65555) y en el [sitio web de Ecma](http://go.microsoft.com/fwlink/?LinkId=116487).  
  
## <a name="in-this-section"></a>En esta sección  
 [Problemas de seguridad en la emisión de la reflexión](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)  
 Describe los problemas de seguridad relacionados con la creación de ensamblados dinámicos mediante emisión de la reflexión.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Reflection.Emit.OpCodes>  
 Cataloga los códigos de instrucción de MSIL que puede usar para compilar cuerpos de método.  
  
 <xref:System.Reflection.Emit>  
 Contiene clases administradas usadas para emitir ensamblados, tipos y métodos dinámicos.  
  
 <xref:System.Type>  
 Describe la clase <xref:System.Type>, que representa los tipos en reflexión administrada y emisión de la reflexión, y que es clave para el uso de estas tecnologías.  
  
 <xref:System.Reflection>  
 Contiene clases administradas usadas para explorar metadatos y código administrado.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Reflexión](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Explica cómo explorar metadatos y código administrado.  
  
 [Ensamblados en Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Proporciona información general de los ensamblados de .NET Framework.
