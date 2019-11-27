---
title: Contextos de declaración y niveles de acceso predeterminados
ms.date: 07/20/2015
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
ms.openlocfilehash: 1ba25d830b1e7529bdf09c1195cc1fe7f9b2243b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354101"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>Contextos de declaración y niveles de acceso predeterminados (Visual Basic)
En este tema se describe qué tipos de Visual Basic se pueden declarar dentro de los demás tipos y cuál es el valor predeterminado de los niveles de acceso si no se especifica.  
  
## <a name="declaration-context-levels"></a>Niveles de contexto de declaración  
 El *contexto* de la declaración de un elemento de programación es la región de código en la que se declara. A menudo, se trata de otro elemento de programación, que se llama *elemento contenedor*.  
  
 Los niveles de los contextos de declaración son los siguientes:  
  
- *Nivel de espacio de nombres* : dentro de un archivo de código fuente o espacio de nombres pero no dentro de una clase, estructura, módulo o interfaz  
  
- *Nivel de módulo* : dentro de una clase, una estructura, un módulo o una interfaz, pero no dentro de un procedimiento o bloque  
  
- *Nivel de procedimiento* : dentro de un procedimiento o bloque (como `If` o `For`)  
  
 En la tabla siguiente se muestran los niveles de acceso predeterminados para varios elementos de programación declarados, en función de sus contextos de declaración.  
  
|Elemento declarado|Nivel de espacio de nombres|Nivel de módulo|Nivel de procedimiento|  
|----------------------|---------------------|------------------|---------------------|  
|Variable ([instrucción Dim](../../../visual-basic/language-reference/statements/dim-statement.md))|No admitido|`Private` (`Public` en `Structure`, no permitido en `Interface`)|`Public`|  
|Constant ([instrucción const](../../../visual-basic/language-reference/statements/const-statement.md))|No admitido|`Private` (`Public` en `Structure`, no permitido en `Interface`)|`Public`|  
|Enumeración ([instrucción enum](../../../visual-basic/language-reference/statements/enum-statement.md))|`Friend`|`Public`|No admitido|  
|Class ([instrucción de clase](../../../visual-basic/language-reference/statements/class-statement.md))|`Friend`|`Public`|No admitido|  
|Structure ([instrucción Structure](../../../visual-basic/language-reference/statements/structure-statement.md))|`Friend`|`Public`|No admitido|  
|Module ([instrucción de módulo](../../../visual-basic/language-reference/statements/module-statement.md))|`Friend`|No admitido|No admitido|  
|Interface ([instrucción interface](../../../visual-basic/language-reference/statements/interface-statement.md))|`Friend`|`Public`|No admitido|  
|Procedure ([instrucción function](../../../visual-basic/language-reference/statements/function-statement.md), [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md))|No admitido|`Public`|No admitido|  
|Referencia externa ([instrucción Declare](../../../visual-basic/language-reference/statements/declare-statement.md))|No admitido|`Public` (no se permite en `Interface`)|No admitido|  
|Operator ([instrucción de operador](../../../visual-basic/language-reference/statements/operator-statement.md))|No admitido|`Public` (no se permite en `Interface` o `Module`)|No admitido|  
|Property ([instrucción de propiedad](../../../visual-basic/language-reference/statements/property-statement.md))|No admitido|`Public`|No admitido|  
|Propiedad default ([valor predeterminado](../../../visual-basic/language-reference/modifiers/default.md))|No admitido|`Public` (no se permite en `Module`)|No admitido|  
|Event ([instrucción de evento](../../../visual-basic/language-reference/statements/event-statement.md))|No admitido|`Public`|No admitido|  
|Delegate ([instrucción Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md))|`Friend`|`Public`|No admitido|  
  
 Para obtener más información, consulte [niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Vea también

- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
