---
title: Compatibilidad de aplicaciones en .NET Framework 4.6 | Microsoft Docs
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
- application compatibility, .NET Framework
- application compatibility. NET Framework 4.6
ms.assetid: 7a3fd352-a8ba-4f9a-8250-951f2c994248
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 32bbbf7cb9acd71f5b8e28b7b12aab706221fab9
ms.lasthandoff: 04/18/2017

---
# <a name="application-compatibility-in-the-net-framework-46"></a>Compatibilidad de aplicaciones en .NET Framework 4.6
En este tema se proporcionan vínculos a información sobre problemas de compatibilidad de aplicaciones entre .NET Framework 4.5.2 y 4.6. Los problemas se dividen en dos categorías:  
  
 [Cambios en el runtime](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)  
 Los cambios en tiempo de ejecución a todas las aplicaciones que se ejecutan en [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] y que usan una característica determinada.  
  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)  
 Los cambios de redestinación afectan a las aplicaciones que se vuelven a compilar para .NET Framework 4.5, 4.5.1, 4.5.2 o 4.6. Son los siguientes:  
  
-   Cambios en el entorno en tiempo de diseño. Por ejemplo, las herramientas de compilación pueden emitir advertencias cuando antes no lo hacían.  
  
-   Cambios en el entorno en tiempo de ejecución. Estos solo afectan a las aplicaciones compiladas específicamente para [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. Las aplicaciones compiladas para versiones anteriores de .NET Framework se comportan de la misma manera que cuando se ejecutan en esas versiones.  
  
 En los temas que describen cambios en tiempo de ejecución y de redestinación, hemos ordenado los elementos individuales por su impacto esperado, como sigue:  
  
 Major  
 Se trata de un cambio significativo que afecta a un gran número de aplicaciones o que requiere una modificación sustancial del código.  
  
 Minor  
 Se trata de un cambio que afecta a un pequeño número de aplicaciones o que requiere ligeras modificaciones en el código.  
  
 Caso avanzado  
 Se trata de un cambio que afecta a aplicaciones de escenarios muy concretos que no son frecuentes.  
  
 Transparente  
 Se trata de un cambio que no tiene ningún efecto apreciable en el programador o el usuario de la aplicación. No es necesario modificar la aplicación debido a este cambio.  
  
## <a name="see-also"></a>Vea también  
 [Versiones y dependencias](../../../docs/framework/migration-guide/versions-and-dependencies.md)   
 [Compatibilidad de aplicaciones](../../../docs/framework/migration-guide/application-compatibility.md)   
 [Compatibilidad de aplicaciones en 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Compatibilidad de aplicaciones en 4.5.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)   
 [Compatibilidad de aplicaciones en 4.5.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)
