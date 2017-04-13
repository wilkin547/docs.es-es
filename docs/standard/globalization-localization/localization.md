---
title: "Localizaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "desarrollo de aplicaciones [.NET Framework], adaptación"
  - "bloques de código"
  - "referencia cultural, adaptación"
  - "aplicaciones globales, adaptación"
  - "globalización [.NET Framework], adaptación"
  - "aplicaciones internacionales [.NET Framework], adaptación"
  - "localización [.NET Framework], acerca de la localización"
  - "adaptar recursos"
  - "bloques de la interfaz de usuario"
  - "aplicaciones de uso internacional, adaptación"
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Localizaci&#243;n
La localización es el proceso de traducción de los recursos de una aplicación en versiones locales para cada referencia cultural que admita la aplicación.  Únicamente debe proceder al paso de localización después de completar el paso de [Revisión de adaptabilidad](../../../docs/standard/globalization-localization/localizability-review.md) para comprobar si la aplicación globalizada está preparada para la localización.  
  
 Una aplicación que está preparada para la localización se divide en dos bloques conceptuales: uno contiene todos los elementos de la interfaz de usuario y el otro contiene el código ejecutable.  El bloque de la interfaz de usuario sólo incluye los elementos de la interfaz de usuario localizables, como cadenas, mensajes de error, cuadros de diálogo, menús o recursos de objetos incrustados, entre otros, para la referencia cultural neutra.  El bloque de código sólo contiene el código de la aplicación que van a utilizar todas las referencias culturales admitidas.  Common Language Runtime admite el uso de un modelo de recursos de ensamblado satélite que independiza el código ejecutable de la aplicación de los recursos.  Para obtener más información sobre cómo implementar este modelo, vea [Recursos de aplicaciones de escritorio](../../../docs/framework/resources/index.md).  
  
 Por cada versión localizada de la aplicación hay que agregar un ensamblado satélite que contenga el bloque localizado de la interfaz de usuario traducida al idioma apropiado para la referencia cultural de destino.  El bloque de código debe ser el mismo para todas las referencias culturales.  La combinación de una versión localizada del bloque de la interfaz de usuario con el bloque de código produce una versión localizada de la aplicación.  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] proporciona la herramienta Editor de recursos de Windows Forms \(Winres.exe\), que permite localizar rápidamente Windows Forms en las referencias culturales de destino.  Para obtener información sobre cómo utilizar esta herramienta, vea [Winres.exe \(Windows Forms Resource Editor\)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).  
  
## Vea también  
 [Globalización y localización](../../../docs/standard/globalization-localization/index.md)   
 [Revisión de adaptabilidad](../../../docs/standard/globalization-localization/localizability-review.md)   
 [Globalización](../../../docs/standard/globalization-localization/globalization.md)   
 [Recursos de aplicaciones de escritorio](../../../docs/framework/resources/index.md)