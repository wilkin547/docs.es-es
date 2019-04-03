---
title: "La primera instrucción de este 'Sub New' debe ser una llamada explícita a 'MyBase.New' o a 'MyClass.New' porque el constructor '<constructorname>' de la clase base '<baseclassname>' de '<derivedclassname>' está marcado como obsoleto: '<errormessage>'"
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: 737f9119814e784ebabcbb4629ab6948ce164168
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814099"
---
# <a name="first-statement-of-this-sub-new-must-be-an-explicit-call-to-mybasenew-or-myclassnew-because-the-constructorname-in-the-base-class-baseclassname-of-derivedclassname-is-marked-obsolete-errormessage"></a>La primera instrucción de este 'Sub New' debe ser una llamada explícita a 'MyBase.New' o 'MyClass.New' porque el '\<nombreconstructor >' en la clase base\<nombredeclasebase >' de '\<derivedclassname >' está marcado como obsoleto: '\< ErrorMessage >'
Un constructor de clase no realiza una llamada de manera explícita a un constructor de clase base y el constructor de clase base se marca con el atributo <xref:System.ObsoleteAttribute> y la directiva para tratarlo como un error.  
  
 Cuando un constructor de clase derivada no llama a un constructor de clase base, Visual Basic intenta generar una llamada implícita a un constructor de clase base sin parámetros. Si no hay ningún constructor accesible en la clase base que se pueda llamar sin argumentos, Visual Basic no se puede generar una llamada implícita. En este caso, el constructor necesario se marca con el <xref:System.ObsoleteAttribute> atributo, por lo que Visual Basic no puede llamarlo.  
  
 Para marcar que cualquier elemento de programación ya no está en uso, aplíquele <xref:System.ObsoleteAttribute> . Si lo hace, puede establecer la propiedad <xref:System.ObsoleteAttribute.IsError%2A> del atributo en `True` o `False`. Si se establece en `True`, el compilador trata como un error los intentos de usar el elemento. Si se establece en `False`o se deja el valor predeterminado `False`, el compilador emite una advertencia si se produce un intento de usar el elemento.  
  
 **Identificador de error:** BC30920  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Examine el mensaje de error indicado y tome las medidas adecuadas.  
  
2.  Incluya una llamada a `MyBase.New()` o `MyClass.New()` como la primera instrucción de `Sub New` en la clase derivada.  
  
## <a name="see-also"></a>Vea también

- [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)
