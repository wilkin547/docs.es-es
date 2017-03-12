---
title: "La propiedad &#39;&lt;nombre de propiedad&gt;&#39; no devuelve un valor en todas las rutas de acceso a c&#243;digo | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc42107"
  - "vbc42107"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42107"
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# La propiedad &#39;&lt;nombre de propiedad&gt;&#39; no devuelve un valor en todas las rutas de acceso a c&#243;digo
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

La propiedad '\<propertyname\>' no devuelve un valor en todas las rutas de acceso a código.Podría producirse en tiempo de ejecución una excepción de referencia nula cuando se utiliza el resultado.  
  
 Un procedimiento `Get` para obtener una propiedad tiene al menos una ruta posible en el código que no devuelve un valor.  
  
 Puede devolver un valor de un procedimiento `Get` de propiedad de cualquiera de las maneras siguientes:  
  
-   Asigne el valor al nombre de propiedad y, a continuación, realice una instrucción `Exit Property`.  
  
-   Asigne el valor al nombre de propiedad y, a continuación, realice la instrucción `End Get`.  
  
-   Incluya el valor en [Return \(Instrucción\)](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Si el control pasa a `Exit Property` o a `End Get` y no ha asignado ningún valor al nombre de propiedad, el procedimiento `Get` devuelve el valor predeterminado del tipo de datos de la propiedad.  Para obtener más información, vea "Comportamiento" en [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 De forma predeterminada, este mensaje es una advertencia.  Para obtener más información sobre cómo ocultar las advertencias o tratar las advertencias como errores, consulte [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC42107  
  
### Para corregir este error  
  
-   Compruebe su lógica de flujo de control y asegúrese de que asigna un valor antes de cada instrucción que genera un valor devuelto.  
  
     Es más fácil garantizar que cada valor devuelto del procedimiento devuelve un valor si siempre utiliza la instrucción `Return`.  Si lo hace, la última instrucción antes de `End Get` debería ser una instrucción `Return`.  
  
## Vea también  
 [Procedimientos de propiedad](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Get \(Instrucción\)](../../../visual-basic/language-reference/statements/get-statement.md)