---
title: "La propiedad predeterminada &#39;&lt;propiedad1&gt;&#39; est&#225; en conflicto con la propiedad predeterminada &#39;&lt;propiedad2&gt;&#39; en la base &#39;&lt;clase&gt;&#39; y, por tanto, se debe declarar como &#39;Shadows&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc40007"
  - "bc40007"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40007"
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# La propiedad predeterminada &#39;&lt;propiedad1&gt;&#39; est&#225; en conflicto con la propiedad predeterminada &#39;&lt;propiedad2&gt;&#39; en la base &#39;&lt;clase&gt;&#39; y, por tanto, se debe declarar como &#39;Shadows&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una propiedad está declarada con el mismo nombre que una propiedad definida en la clase base.  En esta situación, la propiedad de esta clase debe sombrear a la propiedad de la clase base.  
  
 Este mensaje es una advertencia.  De manera predeterminada, se da por supuesto que es `Shadows`.  Para obtener más información sobre cómo ocultar las advertencias o tratarlas como errores, vea [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40007  
  
### Para corregir este error  
  
-   Agregue la palabra clave `Shadows` a la declaración o cambie el nombre de la propiedad que se declara.  
  
## Vea también  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)