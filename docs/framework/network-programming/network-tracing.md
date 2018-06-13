---
title: Traza de la red en .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- debugging [.NET Framework], network tracing
- methods, network tracing
- Networking
- trace enabled debugging
- network tracing, about network tracing
- network tracing
- network, network tracing
- traffic tracing
- tracing [.NET Framework], network
- deploying applications [.NET Framework], network traffic
- capturing network traffic
- Internet, network tracing
- Network Resources
- output, network tracing
- method invocations
ms.assetid: e993b7c3-087f-45d8-9c02-9dded936d804
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 505c5f39890f7f362c5f5d8525a65f8c3d05624a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33398045"
---
# <a name="network-tracing-in-the-net-framework"></a>Traza de la red en .NET Framework
El seguimiento de red de .NET Framework proporciona acceso a información sobre las invocaciones de métodos y el tráfico de red generado por una aplicación administrada. Esta característica es útil para depurar las aplicaciones en desarrollo y para analizar las aplicaciones implementadas. El resultado proporcionado por la traza de la red se puede personalizar para admitir diferentes escenarios de uso en tiempo de desarrollo y en un entorno de producción.  
  
 Para habilitar el seguimiento de red en .NET Framework, debe seleccionar un destino para el resultado del seguimiento y agregar opciones de configuración de seguimiento de la red al archivo de configuración de la aplicación o del equipo. Para obtener descripciones de los archivos de configuración y de cómo se usan, vea [Configuration Files](../../../docs/framework/configure-apps/index.md) (Archivos de configuración). Para obtener información sobre cómo habilitar el seguimiento de red, vea [Enabling Network Tracing](../../../docs/framework/network-programming/enabling-network-tracing.md) (Habilitar el seguimiento de red). Para obtener información sobre los valores que se deben agregar al archivo de configuración, vea [How to: Configure Network Tracing](../../../docs/framework/network-programming/how-to-configure-network-tracing.md) (Cómo: configurar el seguimiento de red).  
  
 Cuando se habilita el seguimiento, puede capturar la información de seguimiento generada por las clases de **System.Net**. Los miembros de la clase de red que generan información de seguimiento incluyen la siguiente nota en la sección Comentarios de la documentación de la biblioteca de clases de .NET Framework:  
  
> [!NOTE]
>  Este miembro genera información de seguimiento cuando se habilita el seguimiento de red en la aplicación. Para obtener más información, vea Seguimiento de red.  
  
## <a name="see-also"></a>Vea también  
 [Habilitar el seguimiento de red](../../../docs/framework/network-programming/enabling-network-tracing.md)  
 [Cómo: configurar el seguimiento de red](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)  
 [Interpretación del seguimiento de red](../../../docs/framework/network-programming/interpreting-network-tracing.md)  
 [Introducción a la instrumentación y el seguimiento](http://msdn.microsoft.com/library/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)
