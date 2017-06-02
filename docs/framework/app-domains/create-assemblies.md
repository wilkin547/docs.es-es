---
title: "Crear ensamblados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ensamblados [.NET Framework], crear"
  - "ensamblados [.NET Framework], de múltiples archivos"
  - "ensamblados de múltiples archivos"
  - "ensamblados de un solo archivo"
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Crear ensamblados
Se pueden crear ensamblados de un único archivo o de varios archivos mediante un IDE, como [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] o mediante los compiladores y herramientas proporcionados en [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].  El ensamblado más sencillo es un único archivo que tiene un nombre sencillo y se carga en un solo dominio de aplicación.  A este ensamblado no pueden hacer referencia otros ensamblados de fuera del directorio de la aplicación. En este ensamblado no se pueden comprobar las versiones.  Para desinstalar la aplicación que forma el ensamblado, no hay más que eliminar el directorio en que reside.  Muchos programadores no necesitan más que un ensamblado con estas características para implementar una aplicación.  
  
 Se puede crear un ensamblado con varios archivos a partir de varios módulos de código y archivos de recursos.  También se puede crear un ensamblado que puedan compartir varias aplicaciones.  Un ensamblado compartido debe tener un nombre seguro y se puede implementar en la caché global de ensamblados.  
  
 Existen varias opciones para agrupar módulos de código y recursos en ensamblados, dependiendo de los siguientes factores:  
  
-   Control de versiones  
  
     Agrupe módulos que deban tener la misma información de versión.  
  
-   Implementación  
  
     Agrupe módulos de código y recursos compatibles con el modelo de implementación.  
  
-   Reutilización  
  
     Agrupe módulos si se pueden utilizar juntos de forma lógica con la misma finalidad.  Por ejemplo, un ensamblado formado por tipos y clases que se usan raramente en el mantenimiento de programas se pueden poner en el mismo ensamblado.  Además, los tipos que se vayan a compartir entre varias aplicaciones se deben agrupar en un ensamblado, que se debe firmar con un nombre seguro.  
  
-   Seguridad  
  
     Agrupe módulos que contengan tipos que requieran los mismos permisos de seguridad.  
  
-   Ámbito  
  
     Agrupe módulos que contengan tipos que sólo pueda ver el mismo ensamblado.  
  
 Si los ensamblados de Common Language Runtime van a estar disponibles para aplicaciones COM no administradas hay que tener en cuenta factores especiales.  Para obtener más información sobre cómo trabajar con código no administrado, vea [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).  
  
## Vea también  
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)   
 [Versiones de los ensamblados](../../../docs/framework/app-domains/assembly-versioning.md)   
 [Cómo: Compilar un ensamblado de un solo archivo](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)   
 [Cómo: Compilar un ensamblado de varios archivos](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)   
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Ensamblados de varios archivos](../../../docs/framework/app-domains/multifile-assemblies.md)