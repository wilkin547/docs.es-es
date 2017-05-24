---
title: Compatibilidad de aplicaciones en .NET Framework 4.5.1 | Microsoft Docs
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
- application compatibility,.NET Framework 4.5.1
- application compatibility,.NET Framework
ms.assetid: 2b07b729-e2bf-4925-8b83-9c9ee6c48612
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9f90929c7181e5a615b9c7fb757c49367f40bc85
ms.lasthandoff: 04/18/2017

---
# <a name="application-compatibility-in-the-net-framework-451"></a>Compatibilidad de aplicaciones en .NET Framework 4.5.1
En este tema se proporcionan vínculos a información sobre problemas de compatibilidad de aplicaciones entre .NET Framework 4.5 y 4.5.1. Los problemas se dividen en dos categorías:  
  
 [Cambios en el runtime](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)  
 Los cambios en tiempo de ejecución a todas las aplicaciones que se ejecutan en [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] y que usan una característica determinada.  
  
 [Cambios de redestinación](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-1.md)  
 Los cambios de redestinación afectan a las aplicaciones que se vuelven a compilar para [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]. Son los siguientes:  
  
-   Cambios en el entorno en tiempo de diseño. Por ejemplo, las herramientas de compilación pueden emitir advertencias cuando antes no lo hacían.  
  
-   Cambios en el entorno en tiempo de ejecución. Estos solo afectan a las aplicaciones compiladas específicamente para [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]. Las aplicaciones compiladas para versiones anteriores de .NET Framework se comportan de la misma manera que cuando se ejecutan en esas versiones.  
  
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
 [Compatibilidad de aplicaciones en 4.5.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)
