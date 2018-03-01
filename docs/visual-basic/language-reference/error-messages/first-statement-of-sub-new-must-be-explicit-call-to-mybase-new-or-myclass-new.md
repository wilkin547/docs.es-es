---
title: "La primera instrucción de este &#39; Sub New &#39; debe ser una llamada explícita a &#39; MyBase.New &#39; o &#39; MyClass.New &#39; Dado que el &#39; &lt;nombreconstructor&gt;&#39; en la clase base &#39;&lt; nombredeclasebase&gt;&#39; de &#39;&lt; nombreclasederivada&gt;&#39; está marcado como obsoleto: &#39;&lt; ErrorMessage&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8882acd947251d85804fbefd54267ce078e31b95
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a>La primera instrucción de este &#39; Sub New &#39; debe ser una llamada explícita a &#39; MyBase.New &#39; o &#39; MyClass.New &#39; Dado que el &#39; &lt;nombreconstructor&gt;&#39; en la clase base &#39;&lt; nombredeclasebase&gt;&#39; de &#39;&lt; nombreclasederivada&gt;&#39; está marcado como obsoleto: &#39;&lt; ErrorMessage&gt;&#39;
Un constructor de clase no realiza una llamada de manera explícita a un constructor de clase base y el constructor de clase base se marca con el atributo <xref:System.ObsoleteAttribute> y la directiva para tratarlo como un error.  
  
 Cuando un constructor de clase derivada no llama a un constructor de clase base, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] intenta generar una llamada implícita a un constructor de clase base sin parámetros. Si no hay ningún constructor accesible en la clase base que se pueda llamar sin argumentos, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] no puede generar una llamada implícita. En este caso, el constructor necesario se marca con el atributo <xref:System.ObsoleteAttribute> , por lo que [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] no puede llamarlo.  
  
 Para marcar que cualquier elemento de programación ya no está en uso, aplíquele <xref:System.ObsoleteAttribute> . Si lo hace, puede establecer la propiedad <xref:System.ObsoleteAttribute.IsError%2A> del atributo en `True` o `False`. Si se establece en `True`, el compilador trata como un error los intentos de usar el elemento. Si se establece en `False`o se deja el valor predeterminado `False`, el compilador emite una advertencia si hay un intento de usar el elemento.  
  
 **Id. de error:** BC30920  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Examine el mensaje de error indicado y tome las medidas adecuadas.  
  
2.  Incluya una llamada a `MyBase.New()` o `MyClass.New()` como la primera instrucción de `Sub New` en la clase derivada.  
  
## <a name="see-also"></a>Vea también  
 [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 
