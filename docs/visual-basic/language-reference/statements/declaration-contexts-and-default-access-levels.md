---
title: "Contextos de declaraci&#243;n y niveles de acceso predeterminados (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "niveles de acceso, niveles predeterminados"
  - "niveles de acceso, Visual Basic"
  - "contextos de declaración, Visual Basic"
  - "nivel de módulo, definición"
  - "nivel del espacio de nombres, definición"
  - "nivel del procedimiento, definición"
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Contextos de declaraci&#243;n y niveles de acceso predeterminados (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En este tema se describen qué tipos de Visual Basic se pueden declarar dentro de otros tipos y qué niveles de acceso se establecen de manera predeterminada si no se especifican.  
  
## Niveles del contexto de declaración  
 El *contexto de declaración* de un elemento de programación es la región de código en la que se declara.  A menudo suele ser otro elemento de programación, que se denomina *elemento contenedor*.  
  
 Los niveles de contexto de declaración son los siguientes:  
  
-   *Nivel de espacio de nombres* — dentro de un archivo de código fuente o espacio de nombres, pero no dentro de una clase, estructura, módulo o interfaz  
  
-   *Nivel de módulo* — dentro de una clase, estructura, módulo o interfaz, pero no dentro de un procedimiento o bloque  
  
-   *Nivel de procedimiento* — dentro de un procedimiento o bloque \(como `If` o `For`\)  
  
 En la tabla siguiente se muestran los niveles de acceso predeterminados para los distintos elementos de programación declarados, en función de sus contextos de declaración.  
  
|Elemento declarado|Nivel de espacio de nombres|Nivel de módulo|Nivel de procedimiento|  
|------------------------|---------------------------------|---------------------|----------------------------|  
|Variable \([Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md)\)|No se permite|`Private` \(`Public` en `Structure`, no se permite en `Interface`\)|`Public`|  
|Constante \([Const \(Instrucción\)](../../../visual-basic/language-reference/statements/const-statement.md)\)|No se permite|`Private` \(`Public` en `Structure`, no se permite en `Interface`\)|`Public`|  
|Enumeración \([Enum \(Instrucción\)](../../../visual-basic/language-reference/statements/enum-statement.md)\)|`Friend`|`Public`|No se permite|  
|Clase \([Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md)\)|`Friend`|`Public`|No se permite|  
|Estructura \([Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md)\)|`Friend`|`Public`|No se permite|  
|Módulo \([Module \(Instrucción\)](../../../visual-basic/language-reference/statements/module-statement.md)\)|`Friend`|No se permite|No se permite|  
|Interfaz \([Interface \(Instrucción\)](../../../visual-basic/language-reference/statements/interface-statement.md)\)|`Friend`|`Public`|No se permite|  
|Procedimiento \([Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md), [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)\)|No se permite|`Public`|No se permite|  
|Referencia externa \([Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)\)|No se permite|`Public` \(no se permite en `Interface`\)|No se permite|  
|Operador \([Operator \(Instrucción\)](../../../visual-basic/language-reference/statements/operator-statement.md)\)|No se permite|`Public` \(no se permite en `Interface` o `Module`\)|No se permite|  
|Propiedad \([Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)\)|No se permite|`Public`|No se permite|  
|Propiedad predeterminada \([Default](../../../visual-basic/language-reference/modifiers/default.md)\)|No se permite|`Public` \(no se permite en `Module`\)|No se permite|  
|Evento \([Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md)\)|No se permite|`Public`|No se permite|  
|Delegado \([Delegate \(Instrucción\)](../../../visual-basic/language-reference/statements/delegate-statement.md)\)|`Friend`|`Public`|No se permite|  
  
 Para obtener más información, vea [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Vea también  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)