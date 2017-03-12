---
title: "La funci&#243;n &#39;&lt;nombre de propiedad&gt;&#39; no devuelve un valor en todas las rutas de acceso a c&#243;digo | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc42105"
  - "vbc42105"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42105"
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# La funci&#243;n &#39;&lt;nombre de propiedad&gt;&#39; no devuelve un valor en todas las rutas de acceso a c&#243;digo
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

La función '\<nombre de procedimiento\>' no devuelve un valor en todas las rutas de acceso de código.¿Le falta una instrucción 'Return'?  
  
 Un procedimiento `Function` tiene al menos una posible ruta de acceso en el código que no devuelve un valor.  
  
 Puede devolver un valor de un procedimiento `Function` de cualquiera de las maneras siguientes:  
  
-   Incluya el valor en [Return \(Instrucción\)](../../../visual-basic/language-reference/statements/return-statement.md).  
  
-   Asigne el valor al nombre de procedimiento `Function` y, a continuación, ejecute una instrucción `Exit Function`.  
  
-   Asigne el valor al nombre de procedimiento `Function` y, a continuación, ejecute la instrucción `End Function`.  
  
 Si el control pasa a `Exit Function` o `End Function` y no ha asignado ningún valor al nombre de procedimiento, éste devuelve el valor predeterminado del tipo de datos devuelto.  Para obtener más información, vea "Comportamiento" en [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 De forma predeterminada, este mensaje es una advertencia.  Para obtener más información sobre cómo ocultar las advertencias o tratar las advertencias como errores, consulte [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC42105  
  
### Para corregir este error  
  
-   Compruebe su lógica de flujo de control y asegúrese de que asigna un valor antes de cada instrucción que genera un valor devuelto.  
  
     Es más fácil garantizar que cada valor devuelto del procedimiento devuelve un valor si siempre utiliza la instrucción `Return`.  Si hace esto, la última instrucción antes de `End Function` debería ser una instrucción `Return`.  
  
## Vea también  
 [Procedimientos Function](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Página Compilación, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic)