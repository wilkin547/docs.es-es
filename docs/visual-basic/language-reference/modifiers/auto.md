---
title: "Auto (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Auto"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Auto (palabra clave)"
  - "Auto (palabra clave), referencias externas"
  - "Auto (palabra clave), calcular las referencias de cadenas"
  - "Declare (instrucción), calcular las referencias de cadenas"
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Auto (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que Visual Basic debe calcular las referencias a las cadenas según reglas de .NET Framework basadas en el nombre externo del procedimiento externo que se declara.  
  
 Cuando se llama a un procedimiento definido fuera del proyecto, el compilador de Visual Basic no tiene acceso a la información que debe tener para llamarlo correctamente.  Esta información incluye la ubicación del procedimiento, la forma de identificación, su secuencia de llamada y tipo de valor devuelto y el juego de caracteres de cadena que utiliza.  [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.  
  
 La parte de `charsetmodifier` en la instrucción `Declare` proporciona la información del juego de caracteres para calcular las referencias de las cadenas durante una llamada al procedimiento externo.  También afecta a la forma en que Visual Basic busca el nombre de procedimiento externo en el archivo externo.  El modificador `Auto` especifica que Visual Basic debe calcular las referencias a las cadenas según las reglas de .NET Framework y que debe determinar el juego de caracteres base de la plataforma en tiempo de ejecución y, posiblemente, modificar el nombre del procedimiento externo si no tiene éxito la búsqueda inicial.  Para obtener más información, vea "Juegos de caracteres" en [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md).  
  
 Si no se especifica un modificador de juego de caracteres, `Ansi` es el valor predeterminado.  
  
## Comentarios  
 El modificador `Auto` se puede utilizar en este contexto:  
  
 [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## Notas para desarrolladores de dispositivos Smart Device  
 No se admite esta palabra clave.  
  
## Vea también  
 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)   
 [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)   
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)