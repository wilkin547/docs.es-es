---
title: "&quot;&lt;elementname&gt;&quot; está obsoleto (advertencia de Visual Basic) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40008
- bc40008
dev_langs:
- VB
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: ccec3b2659502c84dd4db9c9c4d796362958030b
ms.lasthandoff: 03/13/2017

---
# <a name="39ltelementnamegt39-is-obsolete-visual-basic-warning"></a>'&lt;elementname&gt;' está obsoleto (advertencia de Visual Basic)
Una instrucción intenta obtener acceso a un elemento de programación que se ha marcado con el <xref:System.ObsoleteAttribute>atributo y la directiva para tratarlo como una advertencia.</xref:System.ObsoleteAttribute>  
  
 Puede marcar cualquier elemento de programación ya no está en uso aplicando <xref:System.ObsoleteAttribute>a lo</xref:System.ObsoleteAttribute> Si lo hace, puede establecer el atributo <xref:System.ObsoleteAttribute.IsError%2A>propiedad como `True` o `False`.</xref:System.ObsoleteAttribute.IsError%2A> Si se establece en `True`, el compilador trata un intento de usar el elemento como un error. Si se establece en `False`o se deja el valor predeterminado `False`, el compilador emite una advertencia si se produce un intento de usar el elemento.  
  
 De forma predeterminada, este mensaje es una advertencia, ya que el <xref:System.ObsoleteAttribute.IsError%2A>propiedad de <xref:System.ObsoleteAttribute>es `False`.</xref:System.ObsoleteAttribute> </xref:System.ObsoleteAttribute.IsError%2A> Para obtener más información acerca de cómo ocultar las advertencias o tratar las advertencias como errores, vea [configurar advertencias en Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC40008  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Asegúrese de que la referencia del código fuente escriba correctamente el nombre del elemento.  
  
## <a name="see-also"></a>Vea también  
 [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)

