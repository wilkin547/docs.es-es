---
title: "La primera instrucci&#243;n de este &#39;Sub New&#39; debe ser una llamada expl&#237;cita a &#39;MyBase.New&#39; o a &#39;MyClass.New&#39; porque el constructor &#39;&lt;nombre de constructor&gt;&#39; de la clase base &#39;&lt;nombre de clase base&gt;&#39; de &#39;&lt;nombre de clase derivada&gt;&#39; est&#225; marcado como obsoleto: &#39;&lt;mensaje de error&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30920"
  - "bc30920"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30920"
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# La primera instrucci&#243;n de este &#39;Sub New&#39; debe ser una llamada expl&#237;cita a &#39;MyBase.New&#39; o a &#39;MyClass.New&#39; porque el constructor &#39;&lt;nombre de constructor&gt;&#39; de la clase base &#39;&lt;nombre de clase base&gt;&#39; de &#39;&lt;nombre de clase derivada&gt;&#39; est&#225; marcado como obsoleto: &#39;&lt;mensaje de error&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un constructor de clase no llama explícitamente a un constructor de clase base y el constructor de la clase base implícita está marcado con el atributo <xref:System.ObsoleteAttribute> y la directiva de tratarlo como un error.  
  
 Cuando un constructor de clase derivada no llama a un constructor de clase base, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] intenta generar una llamada implícita a un constructor de clase base sin parámetros.  Si no hay en la clase base un constructor accesible al que se puede llamar sin argumentos, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] no puede generar una llamada implícita.  En este caso, el constructor necesario está marcado con el atributo <xref:System.ObsoleteAttribute>, por lo tanto, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] no puede llamarlo.  
  
 Para indicar que un elemento de programación ya no está en uso, puede marcarlo aplicándole <xref:System.ObsoleteAttribute>.  Si hace esto, podrá establecer la propiedad <xref:System.ObsoleteAttribute.IsError%2A> del atributo en `True` o `False`.  Si la establece en `True`, el compilador tratará como un error los intentos de utilizar el elemento.  Si la establece en `False`, o deja el valor predeterminado `False`, el compilador emitirá una advertencia cuando se intente utilizar el elemento.  
  
 **Identificador de error:** BC30920  
  
### Para corregir este error  
  
1.  Examine el mensaje de error y adopte las medidas oportunas.  
  
2.  Incluya una llamada a `MyBase.New()` o `MyClass.New()` como la primera instrucción de `Sub New` en la clase derivada.  
  
## Vea también  
 [Atributos](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)