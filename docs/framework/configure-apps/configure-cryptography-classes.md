---
title: "Configurar clases de criptograf&#237;a | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "configuración de las aplicaciones de .NET Framework, criptografía"
  - "archivos de configuración [.NET Framework], criptografía"
  - "algoritmos criptográficos"
  - "criptografía, clases"
  - "criptografía predeterminada"
  - "seguridad [.NET Framework], cifrado"
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Configurar clases de criptograf&#237;a
[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] permite a los administradores de equipos configurar los algoritmos de cifrado predeterminados y las implementaciones de algoritmos usados por .NET Framework y las aplicaciones correctamente escritas.  Por ejemplo, una empresa que use su propia implementación de un algoritmo de cifrado puede hacer que esa implementación sea la predeterminada en lugar de la que se incluye en [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].  Aunque las aplicaciones administradas que utilizan criptografía siempre pueden elegir enlazarse de forma explícita a una implementación concreta, es recomendable que creen objetos criptográficos mediante el sistema de configuración de criptografía.  
  
## En esta sección  
 [Asignar nombres de algoritmo a clases de criptografía](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 Describe cómo se asigna un nombre de algoritmo a una clase criptográfica.  
  
 [Asignar identificadores de objeto a algoritmos de criptografía](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 Describe cómo se asigna un identificador de objeto a un algoritmo criptográfico.  
  
## Secciones relacionadas  
 [Servicios criptográficos](../../../docs/standard/security/cryptographic-services.md)  
 Facilita información general sobre los servicios de cifrado proporcionados por [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].  
  
 [Esquema de la configuración de criptografía](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 Describe los elementos que asignan nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.