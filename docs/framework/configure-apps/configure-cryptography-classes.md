---
title: Configurar clases de criptografía
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: ba11eed316e227ceae4cb5acecb2b081fa8868f2
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2019
ms.locfileid: "55084411"
---
# <a name="configuring-cryptography-classes"></a>Configurar clases de criptografía
El [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] permite a los administradores de equipo configurar los algoritmos criptográficos predeterminados y las implementaciones de algoritmos que usan .NET Framework y aplicaciones escritas de forma adecuada.  Por ejemplo, una empresa que tiene su propia implementación de un algoritmo criptográfico puede hacer que la implementación el valor predeterminado en lugar de la implementación se incluye en el [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]. Aunque siempre pueden elegir las aplicaciones administradas que utilizan criptografía enlazar explícitamente una implementación determinada, se recomienda que creen objetos criptográficos mediante el sistema de configuración de criptografía.  
  
## <a name="in-this-section"></a>En esta sección  
 [Asignar nombres de algoritmo a clases de criptografía](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 Describe cómo asignar un nombre de algoritmo a una clase de criptografía.  
  
 [Asignar identificadores de objeto a algoritmos de criptografía](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 Describe cómo asignar un identificador de objeto a un algoritmo de criptografía.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)  
 Proporciona información general de servicios criptográficos proporcionados por el [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].  
  
 [Esquema de la configuración de criptografía](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 Describe los elementos que asignan nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.
