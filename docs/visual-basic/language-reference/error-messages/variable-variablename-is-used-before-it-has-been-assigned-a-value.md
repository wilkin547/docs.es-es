---
title: "La variable &#39;&lt;nombre de variable&gt;&#39; se utiliza antes de ser asignada a un valor | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc42104"
  - "BC42104"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42104"
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# La variable &#39;&lt;nombre de variable&gt;&#39; se utiliza antes de ser asignada a un valor
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

La variable '\<nombre de variable\>' se utiliza antes de haber sido asignada a un valor.Podría producirse en tiempo de ejecución una excepción de referencia nula.  
  
 Una aplicación tiene por lo menos una posible ruta de acceso mediante su código que lee una variable antes de que se le asigne cualquier valor.  
  
 Si no se ha asignado nunca ningún valor a una variable, contiene el valor predeterminado para su tipo de datos.  Para un tipo de datos de referencia, ese valor predeterminado es [Nothing](../../../visual-basic/language-reference/nothing.md).  Leer una variable de referencia que tiene un valor de `Nothing` puede producir una <xref:System.NullReferenceException> en algunas circunstancias.  
  
 De forma predeterminada, este mensaje es una advertencia.  Para obtener más información sobre cómo ocultar las advertencias o tratar las advertencias como errores, consulte [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC42104  
  
### Para corregir este error  
  
-   Compruebe la lógica de control del flujo y asegúrese de que la variable tiene un valor válido antes de que el control pase a cualquier instrucción que lo lea.  
  
-   Una manera de garantizar que la variable siempre tiene un valor válido es inicializarla como parte de su declaración.  Vea "Inicialización" en [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## Vea también  
 [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Declaración de variable](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Solucionar problemas de variables](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)