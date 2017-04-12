---
title: No compatible con CLS &lt;membername&gt; no se permite en una interfaz conforme a CLS | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
dev_langs:
- VB
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
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
ms.openlocfilehash: 2861ef22c9307e5bd7d2eabf4f6e37bbd9086345
ms.lasthandoff: 03/13/2017

---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a>No compatible con CLS &lt;membername&gt; no se permite en una interfaz conforme a CLS
Una propiedad, procedimiento o evento en una interfaz se marca como `<CLSCompliant(True)>` cuando la propia interfaz está marcada como `<CLSCompliant(False)>` o no está marcada.  
  
 Para una interfaz que sea compatible con la [independencia del lenguaje y componentes independientes del lenguaje](https://msdn.microsoft.com/library/12a7a7h3) (CLS), deben ser compatible con todos sus miembros.  
  
 Al aplicar el <xref:System.CLSCompliantAttribute>a un elemento de programación, establezca el atributo `isCompliant` parámetro como `True` o `False` para indicar compatibilidad o incompatibilidad.</xref:System.CLSCompliantAttribute> No hay ningún valor predeterminado para este parámetro y debe proporcionar un valor.  
  
 Si no se aplica el <xref:System.CLSCompliantAttribute>a un elemento, se considera como no conforme.</xref:System.CLSCompliantAttribute>  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC40033  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si requiere compatibilidad con CLS y tiene control sobre el código fuente de interfaz, marque la interfaz como `<CLSCompliant(True)>` si todos sus miembros son compatibles.  
  
-   Si requiere compatibilidad con CLS y no tiene control sobre el código fuente de interfaz, o si no califica ser compatible, defina a este miembro dentro de una interfaz diferente.  
  
-   Si requiere que este miembro permanezca dentro de su interfaz actual, quite el <xref:System.CLSCompliantAttribute>de su definición o márquelo como `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute>  
  
## <a name="see-also"></a>Vea también  
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [\<PAVE sobre > escribir código conforme a CLS](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
