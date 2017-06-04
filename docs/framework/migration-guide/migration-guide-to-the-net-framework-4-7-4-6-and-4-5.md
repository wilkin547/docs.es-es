---
title: "Gu&#237;a de migraci&#243;n a .NET Framework 4.6 y 4.5  | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework, migrar aplicaciones a"
  - "migración, .NET Framework"
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
caps.latest.revision: 56
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
---
# Gu&#237;a de migraci&#243;n a .NET Framework 4.6 y 4.5 
Si creó la aplicación con una versión anterior de .NET Framework, normalmente puede actualizarla a .NET Framework 4.5 o 4.5.1 con facilidad. Abra el proyecto en Visual Studio. Si el proyecto se creó en una versión anterior, se abre automáticamente el cuadro de diálogo **Compatibilidad de proyectos**. Para obtener más información sobre cómo actualizar un proyecto en Visual Studio 2013, consulte [Cómo: actualizar proyectos creados en versiones anteriores de Visual Studio](http://msdn.microsoft.com/library/vstudio/ms185327\(v=vs.100\).aspx) y [Portar, migrar y actualizar proyectos de Visual Studio](../Topic/Porting,%20Migrating,%20and%20Upgrading%20Visual%20Studio%20Projects.md).  
  
 Sin embargo, como se han realizado ciertos cambios en .NET Framework, deberá modificar el código. Tal vez también quiera aprovechar las nuevas funciones de .NET Framework 4.5, sus versiones secundarias o .NET Framework 4.6. El proceso de realizar estos tipos de cambios en la aplicación para adaptarla a una nueva versión de .NET Framework se conoce normalmente como *migración*. Si no es necesario migrar la aplicación, puede ejecutarla en .NET Framework 4.5 o versiones posteriores sin recompilarla.  
  
## Recursos de migración  
 Consulte los documentos siguientes antes de migrar la aplicación de versiones anteriores de .NET Framework a las versiones 4.5, 4.5.1 o 4.5.2:  
  
-   Vea [Versiones y dependencias](../../../docs/framework/migration-guide/versions-and-dependencies.md) para conocer la versión de CLR subyacente a cada versión de .NET Framework y repasar las instrucciones sobre cómo establecer correctamente el destino de las aplicaciones.  
  
-   Vea [Compatibilidad de aplicaciones](../../../docs/framework/migration-guide/application-compatibility.md) para obtener información sobre el runtime y los cambios de destino que puedan afectar a la aplicación y cómo abordar estos cambios.  
  
-   Consulte [Lo obsoleto en la biblioteca de clases](../../../docs/framework/whats-new/whats-obsolete.md) para determinar los tipos o los miembros del código que han quedado obsoletos y las alternativas recomendadas.  
  
-   Vea [Novedades](../../../docs/framework/whats-new/index.md) para obtener descripciones sobre las nuevas características que tal vez desee agregar a la aplicación.  
  
## Vea también  
 [Compatibilidad de aplicaciones en 4.5.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)   
 [Compatibilidad de aplicaciones en 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Migrar de .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)   
 [Compatibilidad de versiones](../../../docs/framework/migration-guide/version-compatibility.md)   
 [Versiones y dependencias](../../../docs/framework/migration-guide/versions-and-dependencies.md)   
 [Cómo: Configurar una aplicación para admitir .NET Framework 4 o 4.5](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)   
 [Novedades](../../../docs/framework/whats-new/index.md)   
 [Lo obsoleto en la biblioteca de clases](../../../docs/framework/whats-new/whats-obsolete.md)   
 [Información sobre versión y ensamblado de .NET Framework](http://go.microsoft.com/fwlink/?LinkId=201701)   
 [Directiva de ciclo de vida de soporte técnico de Microsoft .NET Framework](http://go.microsoft.com/fwlink/?LinkId=196607)