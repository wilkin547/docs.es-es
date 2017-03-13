---
title: "Promoci&#243;n de tipos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "elementos declarados, ámbito"
  - "elementos declarados, visibilidad"
  - "Partial (palabra clave), resultados inesperados con promoción de tipos"
  - "ámbito, elementos declarados"
  - "ámbito, Visual Basic"
  - "promoción de tipos"
  - "visibilidad, elementos declarados"
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Promoci&#243;n de tipos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Cuando se declara un elemento de programación en un módulo, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] promueve su ámbito al espacio de nombres que contiene el módulo.  Esto se conoce como *promoción de tipos*.  
  
 El ejemplo siguiente muestra una definición esquemática de un módulo y dos miembros de ese módulo.  
  
 [!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 Dentro de `projModule`, los elementos de programación declarados en el nivel de módulo se promueven a `projNamespace`.  En el ejemplo anterior, `basicEnum` e `innerClass` se promueven, pero `numberSub` no, porque no está declarado en el nivel de módulo.  
  
## Efecto de promoción de tipos  
 El efecto de promoción de tipos es que una cadena de calificación no necesita incluir el nombre del módulo.  El ejemplo siguiente realiza dos llamadas al procedimiento del ejemplo anterior.  
  
 [!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 En el ejemplo anterior, la primera llamada utiliza las cadenas de calificación completas.  Sin embargo, esto no es necesario debido a la promoción de tipos.  La segunda llamada también tiene acceso a los miembros del módulo sin incluir `projModule` en las cadenas de calificación.  
  
## Rechazo de promoción de tipos  
 Si el espacio de nombres ya tiene un miembro con el mismo nombre que un miembro del módulo, se rechaza la promoción de tipos para ese miembro del módulo.  El ejemplo siguiente muestra una definición esquemática de una enumeración y un módulo dentro del mismo espacio de nombres.  
  
 [!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 En el ejemplo anterior, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] no puede promover la clase `abc` a `thisNameSpace` porque ya hay una enumeración con el mismo nombre en el nivel del espacio de nombres.  Para tener acceso a `abcSub`, debe utilizar la cadena de calificación completa `thisNamespace.thisModule.abc.abcSub`.  Sin embargo, todavía se promueve la clase `xyz` y puede tener acceso a `xyzSub` con la cadena de calificación más corta `thisNamespace.xyz.xyzSub`.  
  
### Rechazo de promoción de tipos para tipos parciales  
 Si una clase o estructura dentro de un módulo utiliza la palabra clave [Partial](../../../../visual-basic/language-reference/modifiers/partial.md), se rechaza automáticamente la promoción de tipos para esa clase o estructura, ya tenga o no el espacio de nombres un miembro con el mismo nombre.  Otros elementos en el módulo reúnen todavía los requisitos necesarios para la promoción de tipos.  
  
 **Consecuencias.** El rechazo de la promoción de tipos de una definición parcial puede provocar unos resultados inesperados e incluso errores del compilador.  El ejemplo siguiente muestra definiciones esquemáticas parciales de una clase, una de las cuales está dentro de un módulo.  
  
 [!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 En el ejemplo anterior, el desarrollador podría esperar que el compilador combinara las dos definiciones parciales de `sampleClass`.  Sin embargo, el compilador no considera la promoción para la definición parcial dentro de `sampleModule`.  En consecuencia, intenta compilar dos clases separadas y distintas, ambas denominadas `sampleClass` pero con rutas de acceso de calificación diferentes.  
  
 El compilador sólo combina las definiciones parciales cuando sus rutas de acceso completas son idénticas.  
  
## Recomendaciones  
 Las recomendaciones siguientes representan un buen hábito de programación.  
  
-   **Nombres únicos.** Si tiene el control completo sobre la denominación de los elementos de programación, suele ser una buena idea utilizar nombres únicos en todas partes.  Unos nombres idénticos requieren calificación adicional y pueden dificultar la lectura del código.  También pueden llevar a errores poco claros y a unos resultados inesperados.  
  
-   **Calificación completa.** Si trabaja con módulos y otros elementos en el mismo espacio de nombres, el enfoque más seguro es utilizar siempre una calificación completa para todos los elementos de programación.  Si la promoción de tipos se rechaza para un miembro del módulo y no califica ese miembro por completo, puede tener acceso por error a un elemento de programación diferente.  
  
## Vea también  
 [Module \(Instrucción\)](../../../../visual-basic/language-reference/statements/module-statement.md)   
 [Namespace \(Instrucción\)](../../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)   
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Cómo: Controlar el ámbito de una variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)   
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)