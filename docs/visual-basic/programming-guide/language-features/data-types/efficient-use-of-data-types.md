---
title: "Uso eficiente de tipos de datos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "AscW (función), preferida a Asc"
  - "ChrW (función), preferida a Chr"
  - "tipos de datos [Visual Basic], optimizar"
  - "tipos de datos [Visual Basic], tipado fuerte"
  - "tipos de datos [Visual Basic], utilizar eficazmente"
  - "tipos de datos [Visual Basic], establecimiento flexible de tipos"
  - "optimización, tipos de datos"
  - "rendimiento, eficacia de los tipos de datos"
  - "tipado fuerte"
  - "establecimiento de tipos, inflexible"
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Uso eficiente de tipos de datos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

A las variables no declaradas y a las variables declaradas sin un tipo de datos se les asigna el tipo de datos `Object`.  Esto facilita la creación más rápida de programas, pero puede provocar que se ejecuten de una forma más lenta.  
  
## Tipado fuerte  
 La especificación de tipos de datos para todas las variables recibe el nombre de *tipado fuerte*.  La utilización del tipado fuerte tiene diversas ventajas:  
  
-   Habilita la compatibilidad con intellisense® para las variables.  Esto le permite ver las propiedades de las variables y otros miembros a medida que escribe el código.  
  
-   Saca partido de la comprobación de tipos del compilador.  Permite detectar las instrucciones que pueden fallar en tiempo de ejecución debido a errores tales como el desbordamiento.  También detecta llamadas a métodos en objetos que no las admiten.  
  
-   Tiene como consecuencia una ejecución más rápida del código.  
  
## Tipos de datos más eficaces  
 Para las variables que no contienen nunca valores decimales, los tipos de datos integrales son más eficientes que los tipos no integrales.  En [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], `Integer` y `UInteger` son los tipos numéricos más eficaces.  
  
 Para los números fraccionarios, `Double` es el más eficaz de los tipos de datos, porque los procesadores de las plataformas actuales realizan las operaciones de punto flotante en precisión doble.  Sin embargo, las operaciones con `Double` no son tan rápidas como con los tipos enteros como `Integer`.  
  
## Especificar tipo de datos  
 Utilice [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md) para declarar una variable de un tipo específico.  Puede especificar su nivel de acceso simultáneamente utilizando la palabra clave [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) o [Private](../../../../visual-basic/language-reference/modifiers/private.md), como en el ejemplo siguiente.  
  
```  
Private x As Double  
Protected s As String  
```  
  
## Conversión de caracteres  
 Las funciones `AscW` y `ChrW` funcionan en Unicode.  Es más recomendable utilizar estas funciones que `Asc` y `Chr`, que deben traducir a Unicode y desde éste.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>   
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>   
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Tipos de datos numéricos](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)   
 [Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Utilizar IntelliSense](/visual-studio/ide/using-intellisense)