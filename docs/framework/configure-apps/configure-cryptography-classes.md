---
title: Configurar clases de criptografía
description: Comprenda cómo los administradores de equipos pueden configurar los algoritmos criptográficos y las implementaciones de algoritmo predeterminados que usan .NET y las aplicaciones.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: 5262dfca914fd5306297ea9535bcef3d2088d107
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165213"
---
# <a name="configuring-cryptography-classes"></a>Configurar clases de criptografía

El Windows SDK permite a los administradores del equipo configurar los algoritmos criptográficos y las implementaciones de algoritmo predeterminados que usan las aplicaciones .NET Framework y escritas correctamente.  Por ejemplo, una empresa que tenga su propia implementación de un algoritmo criptográfico puede hacer que esa implementación sea la predeterminada en lugar de la implementación incluida en el Windows SDK. Aunque las aplicaciones administradas que usan criptografía siempre pueden optar por enlazar explícitamente a una implementación concreta, se recomienda que creen objetos criptográficos mediante el sistema de configuración de criptografía.  
  
## <a name="in-this-section"></a>En esta sección  

 [Asignar nombres de algoritmo a clases de criptografía](map-algorithm-names-to-cryptography-classes.md)  
 Describe cómo asignar un nombre de algoritmo a una clase de criptografía.  
  
 [Asignar identificadores de objeto a algoritmos de criptografía](map-object-identifiers-to-cryptography-algorithms.md)  
 Describe cómo asignar un identificador de objeto a un algoritmo criptográfico.  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [servicios criptográficos](../../standard/security/cryptographic-services.md)  
 Proporciona información general sobre los servicios criptográficos proporcionados por el Windows SDK.  
  
 [Esquema de configuración de criptografía](./file-schema/cryptography/index.md)  
 Describe los elementos que asignan nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.
