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
ms.openlocfilehash: e53f4c5c9e24fb25b43b7f27b80ab984214eeac2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "69927766"
---
# <a name="configuring-cryptography-classes"></a>Configurar clases de criptografía
El Windows SDK permite a los administradores del equipo configurar los algoritmos criptográficos y las implementaciones de algoritmo predeterminados que usan las aplicaciones .NET Framework y escritas correctamente.  Por ejemplo, una empresa que tenga su propia implementación de un algoritmo criptográfico puede hacer que esa implementación sea la predeterminada en lugar de la implementación incluida en el Windows SDK. Aunque las aplicaciones administradas que usan criptografía siempre pueden optar por enlazar explícitamente a una implementación concreta, se recomienda que creen objetos criptográficos mediante el sistema de configuración de criptografía.  
  
## <a name="in-this-section"></a>En esta sección  
 [Asignar nombres de algoritmo a clases de criptografía](map-algorithm-names-to-cryptography-classes.md)  
 Describe cómo asignar un nombre de algoritmo a una clase de criptografía.  
  
 [Asignar identificadores de objeto a algoritmos de criptografía](map-object-identifiers-to-cryptography-algorithms.md)  
 Describe cómo asignar un identificador de objeto a un algoritmo criptográfico.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Servicios criptográficos](../../standard/security/cryptographic-services.md)  
 Proporciona información general sobre los servicios criptográficos proporcionados por el Windows SDK.  
  
 [Esquema de la configuración de criptografía](./file-schema/cryptography/index.md)  
 Describe los elementos que asignan nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.
