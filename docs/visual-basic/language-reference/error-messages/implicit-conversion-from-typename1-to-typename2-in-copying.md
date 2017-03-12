---
title: "Conversi&#243;n impl&#237;cita de &#39;&lt;nombre de tipo 1&gt;&#39; a &#39;&lt;nombre de tipo 2&gt;&#39; al copiar de nuevo el valor del par&#225;metro &#39;ByRef&#39; &#39;&lt;nombre de par&#225;metro&gt;&#39; en el argumento correspondiente | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc41999"
  - "bc41999"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC41999"
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Conversi&#243;n impl&#237;cita de &#39;&lt;nombre de tipo 1&gt;&#39; a &#39;&lt;nombre de tipo 2&gt;&#39; al copiar de nuevo el valor del par&#225;metro &#39;ByRef&#39; &#39;&lt;nombre de par&#225;metro&gt;&#39; en el argumento correspondiente
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Se llama a un procedimiento con un argumento [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) de un tipo diferente que el de su parámetro correspondiente.  
  
 Si pasa un argumento `ByRef`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] en ocasiones copia el valor de argumento en una variable local en el procedimiento en lugar de pasar una referencia.  En este caso, cuando el procedimiento vuelve, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] debe copiar de nuevo el valor de la variable local en el argumento del código de llamada.  
  
 Si un valor de argumento `ByRef` se copia en el procedimiento y el argumento y el parámetro son del mismo tipo, no es necesaria ninguna conversión.  Si los tipos son diferentes, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] debe convertir en ambas direcciones.  Dado que no puede utilizar `CType` ni ninguna de las demás palabras clave de conversión en un argumento o un parámetro de procedimiento, este tipo de conversión siempre es implícito.  
  
 De forma predeterminada, este mensaje es una advertencia.  Para obtener más información sobre cómo ocultar las advertencias o tratarlas como errores, vea [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC41999  
  
### Para corregir este error  
  
-   Si es posible, utilice un argumento de llamada del mismo tipo que el parámetro de procedimiento, de forma que [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] no necesite realizar ninguna conversión.  
  
-   Si necesita llamar al procedimiento con un tipo de argumento diferente del tipo de parámetro pero no necesita devolver un valor al argumento que realiza la llamada, defina el parámetro como [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) en lugar de definirlo como `ByRef`.  
  
## Vea también  
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Pasar argumentos por valor y por referencia](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)