---
title: El nombre <membername> no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 33b60b2212d25737330dc93d7ba2715e4d5865b7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873701"
---
# <a name="name-membername-is-not-cls-compliant"></a>El nombre \<membername> no es compatible con CLS

Un ensamblado se marca como `<CLSCompliant(True)>` pero expone un miembro con un nombre que comienza con un carácter de subrayado ( `_` ).  
  
 Un elemento de programación puede contener uno o más guiones bajos, pero para que sea compatible con la [independencia del lenguaje y los componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), no debe comenzar con un carácter de subrayado. Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad. No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.  
  
 Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40031  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Si tiene control sobre el código fuente, cambie el nombre del miembro para que no comience por un carácter de subrayado.  
  
- Si necesita que el nombre de miembro permanezca inalterado, quite el <xref:System.CLSCompliantAttribute> de su definición o márquelo como `<CLSCompliant(False)>` . Todavía puede marcar el ensamblado como `<CLSCompliant(True)>` .  
  
## <a name="see-also"></a>Consulte también

- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [Convenciones de nomenclatura de Visual Basic](../../programming-guide/program-structure/naming-conventions.md)
