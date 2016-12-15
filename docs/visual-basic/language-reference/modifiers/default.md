---
title: "Default (Visual Basic) | Microsoft Docs"
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
  - "vb.Default"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Default (palabra clave) [Visual Basic]"
  - "propiedades predeterminadas"
  - "propiedades predeterminadas, en Visual Basic"
  - "predeterminados, propiedades"
  - "propiedades [Visual Basic], predeterminado"
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Default (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Identifica una propiedad como la propiedad predeterminada de su clase, estructura o interfaz.  
  
## Comentarios  
 Una clase, estructura o interfaz puede designar sólo una de sus propiedades como *propiedad predeterminada*, siempre que esa propiedad acepte al menos un parámetro.  Si el código hace referencia a una clase o estructura sin especificar un miembro, Visual Basic resuelve esta referencia como propiedad predeterminada.  
  
 Las propiedades predeterminadas pueden producir una pequeña reducción en los caracteres del código fuente pero pueden dificultar la lectura del código.  Si el código de llamada no está familiarizado con su clase o estructura, cuando hace referencia al nombre de éstas, no puede estar seguro de si esta referencia tiene acceso a la clase o estructura en sí, o a una propiedad predeterminada.  Esto puede conducir a errores del compilador o a ligeros errores lógicos en tiempo de ejecución.  
  
 Puede reducir levemente las posibilidades de errores de propiedades predeterminadas utilizando siempre [Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md) para establecer la comprobación de tipos del compilador en `On`.  
  
 Si está pensando en utilizar una clase o estructura en el código, debe determinar si tiene una propiedad predeterminada, y si es así, cómo se llama.  
  
 Debido a estas desventajas, debería considerar no definir propiedades predeterminadas.  Para una mejor lectura del código, debería considerar asimismo hacer siempre una referencia explícita a todas las propiedades, incluso a las propiedades predeterminadas.  
  
 El modificador `Default` se puede utilizar en este contexto:  
  
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## Vea también  
 [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)