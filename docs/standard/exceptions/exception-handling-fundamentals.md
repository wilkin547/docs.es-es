---
title: "Fundamentos del control de excepciones | Microsoft Docs"
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
  - "Common Language Runtime, excepciones"
  - "excepciones, ejemplos"
  - "tiempo de ejecución, excepciones"
ms.assetid: e865d48c-b862-4448-833e-09fcd48adf6b
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Fundamentos del control de excepciones
Common Language Runtime admite un modelo de control de excepciones basado en los conceptos de objetos de excepción y bloques de código protegidos.  Cuando se produce una excepción, el tiempo de ejecución crea un objeto que la representa.  También se pueden crear clases de excepción personalizadas derivando clases de la excepción base adecuada.  
  
 Todos los lenguajes que utilizan el motor en tiempo de ejecución controlan las excepciones de forma parecida.  Cada lenguaje usa una forma de control de excepciones estructurado Try\/Catch\/Finally.  En esta sección se proporcionan varios ejemplos de control de excepciones básico.  
  
## En esta sección  
 [Cómo: Utilizar el bloque Try\/Catch para detectar excepciones](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)  
 Describe cómo usar el bloque try\/catch para controlar excepciones.  
  
 [Cómo: Utilizar excepciones específicas en un bloque Catch](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)  
 Describe cómo detectar excepciones específicas.  
  
 [Cómo: Iniciar excepciones explícitamente](../../../docs/standard/exceptions/how-to-explicitly-throw-exceptions.md)  
 Describe cómo producir excepciones y cómo detectarlas y, a continuación, volver a producirlas otra vez.  
  
 [Cómo: Crear excepciones definidas por el usuario](../../../docs/standard/exceptions/how-to-create-user-defined-exceptions.md)  
 Describe cómo crear clases de excepciones personalizadas.  
  
 [Utilizar controladores filtrados por el usuario](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md)  
 Describe cómo configurar excepciones filtradas.  
  
 [Cómo: Utilizar un bloque Finally](../../../docs/standard/exceptions/how-to-use-finally-blocks.md)  
 Explica cómo utilizar la instrucción Finally en un bloque de excepciones.  
  
## Secciones relacionadas  
 [Excepciones](../../../docs/standard/exceptions/index.md)  
 Proporciona una descripción general de las excepciones de Common Language Runtime.  
  
 [Clase Exception y propiedades](../../../docs/standard/exceptions/exception-class-and-properties.md)  
 Describe los elementos de un objeto de excepción.