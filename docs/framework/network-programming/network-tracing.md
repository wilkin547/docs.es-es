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
ms.openlocfilehash: afb9c3a04258b543e373b6973e576f71f90d7003
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71047591"
---
# <a name="network-tracing-in-the-net-framework"></a>Traza de la red en .NET Framework
El seguimiento de red de .NET Framework proporciona acceso a información sobre las invocaciones de métodos y el tráfico de red generado por una aplicación administrada. Esta característica es útil para depurar las aplicaciones en desarrollo y para analizar las aplicaciones implementadas. El resultado proporcionado por la traza de la red se puede personalizar para admitir diferentes escenarios de uso en tiempo de desarrollo y en un entorno de producción.  
  
 Para habilitar el seguimiento de red en .NET Framework, debe seleccionar un destino para el resultado del seguimiento y agregar opciones de configuración de seguimiento de la red al archivo de configuración de la aplicación o del equipo. Para obtener descripciones de los archivos de configuración y de cómo se usan, vea [Archivos de configuración](../configure-apps/index.md). Para obtener información sobre cómo habilitar el seguimiento de red, vea [Habilitación del seguimiento de red](enabling-network-tracing.md). Para obtener información sobre los valores que se deben agregar al archivo de configuración, vea [Cómo: Configurar el seguimiento de red](how-to-configure-network-tracing.md).  
  
 Cuando se habilita el seguimiento, puede capturar la información de seguimiento generada por las clases de **System.Net**. Los miembros de la clase de red que generan información de seguimiento incluyen la siguiente nota en la sección Comentarios de la documentación de la biblioteca de clases de .NET Framework:  
  
> [!NOTE]
> Este miembro genera información de seguimiento cuando se habilita el seguimiento de red en la aplicación. Para obtener más información, vea Seguimiento de red.  
  
## <a name="see-also"></a>Vea también

- [Habilitar el seguimiento de red](enabling-network-tracing.md)
- [Cómo: Configurar el seguimiento de red](how-to-configure-network-tracing.md)
- [Interpretación del seguimiento de red](interpreting-network-tracing.md)
- [Seguimiento e instrumentación de aplicaciones](../debug-trace-profile/tracing-and-instrumenting-applications.md)
