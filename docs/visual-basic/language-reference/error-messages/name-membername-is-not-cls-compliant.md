---
title: Nombre &lt;membername&gt; no es compatible con CLS | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40031
- vbc40031
dev_langs:
- VB
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
caps.latest.revision: 9
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
ms.openlocfilehash: 6a678c66580a7917a3869aac81418152130debff
ms.lasthandoff: 03/13/2017

---
# <a name="name-ltmembernamegt-is-not-cls-compliant"></a>Nombre &lt;membername&gt; no es compatible con CLS
Un ensamblado está marcado como `<CLSCompliant(True)>` pero expone un miembro con un nombre que comienza con un carácter de subrayado (`_`).  
  
 Un elemento de programación puede contener uno o más caracteres de subrayado, pero to sea compatible con la [independencia del lenguaje y componentes independientes del lenguaje](https://msdn.microsoft.com/library/12a7a7h3) (CLS), no debe comenzar con un carácter de subrayado. Consulte [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Al aplicar el <xref:System.CLSCompliantAttribute>a un elemento de programación, establezca el atributo `isCompliant` parámetro como `True` o `False` para indicar compatibilidad o incompatibilidad.</xref:System.CLSCompliantAttribute> No hay ningún valor predeterminado para este parámetro y debe proporcionar un valor.  
  
 Si no se aplica el <xref:System.CLSCompliantAttribute>a un elemento, se considera como no conforme.</xref:System.CLSCompliantAttribute>  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC40031  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si tiene control sobre el código fuente, cambie el nombre de miembro para que no comience con un carácter de subrayado.  
  
-   Si necesita que el nombre de miembro permanezca sin modificar, quite el <xref:System.CLSCompliantAttribute>de su definición o márquelo como `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute> Todavía puede marcar el ensamblado como `<CLSCompliant(True)>`.  
  
## <a name="see-also"></a>Vea también  
 [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [\<PAVE sobre > escribir código conforme a CLS](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
