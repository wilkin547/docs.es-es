---
title: "Guía de migración a .NET Framework 4.7, 4.6 y 4.5 "
ms.custom: updateeachrelease
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- .NET Framework, migrating applications to
- migration, .NET Framework
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae193819b191e6a3a09f0556ff221960c1aeb7b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="migration-guide-to-the-net-framework-47-46-and-45"></a>Guía de migración a .NET Framework 4.7, 4.6 y 4.5 
Si ha creado la aplicación con una versión anterior de .NET Framework, normalmente puede actualizarla con facilidad a .NET Framework 4.5 y sus versiones secundarias (4.5.1 y 4.5.2), .NET Framework 4.6 y sus versiones secundarias (4.6.1 y 4.6.2) o .NET Framework 4.7 y su versión secundaria (.NET Framework 4.7.1). Abra el proyecto en Visual Studio. Si el proyecto se creó en una versión anterior de Visual Studio, se abre automáticamente el cuadro de diálogo **Compatibilidad de proyectos**. Para más información sobre cómo actualizar un proyecto en Visual Studio, consulte [Portar, migrar y actualizar proyectos de Visual Studio](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) y [Compatibilidad y destinatarios de la plataforma de Visual Studio 2017](https://www.visualstudio.com/en-us/productinfo/vs2017-compatibility-vs).  
  
 Sin embargo, como se han realizado ciertos cambios en .NET Framework, deberá modificar el código. Puede que también quiera aprovechar las nuevas funcionalidades de .NET Framework 4.5 y sus versiones secundarias, .NET Framework 4.6 y sus versiones secundarias o .NET Framework 4.7 y su versión secundaria (.NET Framework 4.7.1). El proceso de realizar estos tipos de cambios en la aplicación para adaptarla a una nueva versión de .NET Framework se conoce normalmente como *migración*. Si no es necesario migrar la aplicación, puede ejecutarla en .NET Framework 4.5 o en una versión posterior sin tener que recompilarla.  
  
## <a name="migration-resources"></a>Recursos de migración  
 Consulte los documentos siguientes antes de migrar la aplicación de versiones anteriores de .NET Framework a las versiones 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7 o 4.7.1:  
  
-   Consulte [Versiones y dependencias](../../../docs/framework/migration-guide/versions-and-dependencies.md) para conocer la versión de CLR subyacente a cada versión de .NET Framework y obtener instrucciones sobre cómo establecer correctamente el destino de sus aplicaciones.  
  
-   Consulte [Compatibilidad de aplicaciones](../../../docs/framework/migration-guide/application-compatibility.md) para información sobre el tiempo de ejecución y los cambios de destino que puedan afectar a la aplicación y cómo abordar estos cambios.  
  
-   Consulte [Lo obsoleto en la biblioteca de clases](../../../docs/framework/whats-new/whats-obsolete.md) para determinar los tipos o miembros del código que quedaron obsoletos y las alternativas recomendadas.  
  
-   Consulte [Novedades](../../../docs/framework/whats-new/index.md) para obtener descripciones sobre las nuevas características que tal vez desee agregar a la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Compatibilidad de aplicaciones](../../../docs/framework/migration-guide/application-compatibility.md)  
 [Migración desde .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)  
 [Compatibilidad de versiones](../../../docs/framework/migration-guide/version-compatibility.md)  
 [Versiones y dependencias](../../../docs/framework/migration-guide/versions-and-dependencies.md)  
 [Configurar una aplicación para que admita .NET Framework 4 o 4.5](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)  
 [Novedades](../../../docs/framework/whats-new/index.md)  
 [Lo obsoleto en la biblioteca de clases](../../../docs/framework/whats-new/whats-obsolete.md)  
 [Información sobre versión y ensamblado de .NET Framework](http://go.microsoft.com/fwlink/?LinkId=201701)  
 [Directiva de ciclo de vida de soporte técnico de Microsoft .NET Framework](http://go.microsoft.com/fwlink/?LinkId=196607) [Problemas de migración de .NET Framework 4](net-framework-4-migration-issues.md)
