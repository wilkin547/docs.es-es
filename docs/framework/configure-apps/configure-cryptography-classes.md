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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b12d5d95a17439308d79d094e8c22206778f3128
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743256"
---
# <a name="configuring-cryptography-classes"></a>Configurar clases de criptografía
El [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] permite a los administradores de equipo configurar los algoritmos criptográficos predeterminados y las implementaciones de algoritmos que utilizan .NET Framework y las aplicaciones escritas correctamente.  Por ejemplo, una empresa que tenga su propia implementación de un algoritmo criptográfico puede hacer que la implementación el valor predeterminado en lugar de la implementación que se incluye en el [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]. Aunque las aplicaciones administradas que utilizan criptografía siempre pueden elegir enlazarse de forma explícita a una implementación concreta, se recomienda que creen objetos criptográficos mediante el sistema de configuración de criptografía.  
  
## <a name="in-this-section"></a>En esta sección  
 [Asignar nombres de algoritmo a clases de criptografía](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 Describe cómo asignar un nombre de algoritmo a una clase de criptografía.  
  
 [Asignar identificadores de objeto a algoritmos de criptografía](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 Describe cómo asignar un identificador de objeto a un algoritmo criptográfico.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)  
 Proporciona información general de servicios criptográficos proporcionados por el [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].  
  
 [Esquema de la configuración de criptografía](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 Describe los elementos que asignan nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.
