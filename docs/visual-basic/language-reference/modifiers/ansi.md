---
title: "Ansi (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Ansi"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ANSI"
  - "ANSI, Visual Basic"
  - "Declare (instrucción), calcular las referencias de cadenas"
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Ansi (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifica que Visual Basic debe calcular las referencias de todas las cadenas a valores ANSI \(American National Standards Institute\), independientemente del nombre del procedimiento externo que se declara.  
  
 Cuando se llama a un procedimiento definido fuera del proyecto, el compilador de Visual Basic no tiene acceso a la información que necesita para llamarlo correctamente.  Esta información incluye la ubicación del procedimiento, la forma de identificación, su secuencia de llamada y tipo de valor devuelto y el juego de caracteres de cadena que utiliza.  [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.  
  
 La parte de `charsetmodifier` en la instrucción `Declare` proporciona la información del juego de caracteres para calcular las referencias de las cadenas durante una llamada al procedimiento externo.  También afecta a la forma en que Visual Basic busca el nombre de procedimiento externo en el archivo externo.  El modificador `Ansi` especifica que Visual Basic debe calcular las referencias de todas las cadenas a valores ANSI y debe localizar el procedimiento sin modificar su nombre durante la búsqueda.  
  
 Si no se especifica un modificador de juego de caracteres, `Ansi` es el valor predeterminado.  
  
## Comentarios  
 El modificador `Ansi` se puede utilizar en este contexto:  
  
 [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## Notas para desarrolladores de dispositivos Smart Device  
 No se admite esta palabra clave.  
  
## Vea también  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)   
 [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)   
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)