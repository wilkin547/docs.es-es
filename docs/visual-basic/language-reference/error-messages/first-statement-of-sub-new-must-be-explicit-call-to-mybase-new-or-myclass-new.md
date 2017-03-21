---
title: "La primera instrucción de este &quot;Sub New&quot; debe ser una llamada explícita a &quot;MyBase.New&quot; o &quot;MyClass.New&quot; porque el &quot;&lt;constructorname&gt;&quot;en la clase base&quot;&lt;baseclassname&gt;&quot;de&quot;&lt;derivedclassname&gt;&quot; está marcado como obsoleto: &quot;&lt;errormessage&gt;&quot; | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30920
- bc30920
dev_langs:
- VB
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: feb04d426b7e050b7ad05cdfd4d481172dda3a49
ms.lasthandoff: 03/13/2017

---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a>La primera instrucción de este 'Sub New' debe ser una llamada explícita a 'MyBase.New' o 'MyClass.New' porque el '&lt;constructorname&gt;'en la clase base'&lt;baseclassname&gt;'de'&lt;derivedclassname&gt;' está marcado como obsoleto: '&lt;errormessage&gt;'
Un constructor de clase no llama explícitamente a un constructor de clase base y el constructor de clase base implícito está marcado con el <xref:System.ObsoleteAttribute>atributo y la directiva para tratarlo como un error.</xref:System.ObsoleteAttribute>  
  
 Cuando un constructor de clase derivada no llama a un constructor de clase base, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] intenta generar una llamada implícita a un constructor de clase base sin parámetros. Si no hay ningún constructor accesible en la clase base que se puede llamar sin argumentos, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] no se puede generar una llamada implícita. En este caso, el constructor necesario se marca con el <xref:System.ObsoleteAttribute>lo atributo [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] no puede llamar a lo</xref:System.ObsoleteAttribute>  
  
 Puede marcar cualquier elemento de programación ya no está en uso aplicando <xref:System.ObsoleteAttribute>a lo</xref:System.ObsoleteAttribute> Si lo hace, puede establecer el atributo <xref:System.ObsoleteAttribute.IsError%2A>propiedad como `True` o `False`.</xref:System.ObsoleteAttribute.IsError%2A> Si se establece en `True`, el compilador trata un intento de usar el elemento como un error. Si se establece en `False`o se deja el valor predeterminado `False`, el compilador emite una advertencia si se produce un intento de usar el elemento.  
  
 **Id. de error:** BC30920  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Examine el mensaje de error indicado y tome las medidas adecuadas.  
  
2.  Incluya una llamada a `MyBase.New()` o `MyClass.New()` como la primera instrucción de `Sub New` en la clase derivada.  
  
## <a name="see-also"></a>Vea también  
 [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 
