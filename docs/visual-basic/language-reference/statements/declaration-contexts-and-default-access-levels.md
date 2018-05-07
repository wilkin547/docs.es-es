---
title: Contextos de declaración y niveles de acceso predeterminados (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
ms.openlocfilehash: b30b1068fe662d5f0318a1712dc4690b79bd739d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>Contextos de declaración y niveles de acceso predeterminados (Visual Basic)
Este tema describe qué tipos de Visual Basic se pueden declarar dentro de otros tipos, y lo que los niveles de acceso de forma predeterminada si no se especifica.  
  
## <a name="declaration-context-levels"></a>Niveles de contexto de declaración  
 El *contexto de la declaración* de un elemento de programación es la región de código en el que se declara. Esto suele ser otro elemento de programación, que, a continuación, se llama la *que contiene el elemento*.  
  
 Los niveles de contextos de declaración son los siguientes:  
  
-   *Nivel de Namespace* : dentro de un archivo de código fuente o espacio de nombres pero no dentro de una clase, estructura, módulo o interfaz  
  
-   *Nivel de módulo* : dentro de una clase, estructura, módulo o interfaz, pero no dentro de un procedimiento o bloque  
  
-   *Nivel de procedimiento* : dentro de un procedimiento o bloque (como `If` o `For`)  
  
 La siguiente tabla muestra los niveles de acceso predeterminados para varios elementos de programación declarados, dependiendo de sus contextos de declaración.  
  
|Elemento declarado|Nivel de Namespace|Nivel de módulo|Nivel de procedimiento|  
|----------------------|---------------------|------------------|---------------------|  
|Variable ([Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md))|No permitido|`Private` (`Public` en `Structure`, no está permitida en `Interface`)|`Public`|  
|Constante ([Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md))|No permitido|`Private` (`Public` en `Structure`, no está permitida en `Interface`)|`Public`|  
|Enumeración ([Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md))|`Friend`|`Public`|No permitido|  
|Clase ([Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md))|`Friend`|`Public`|No permitido|  
|Estructura ([estructura instrucción](../../../visual-basic/language-reference/statements/structure-statement.md))|`Friend`|`Public`|No permitido|  
|Módulo ([Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md))|`Friend`|No permitido|No permitido|  
|Interfaz ([Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md))|`Friend`|`Public`|No permitido|  
|Procedimiento ([función instrucción](../../../visual-basic/language-reference/statements/function-statement.md), [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md))|No permitido|`Public`|No permitido|  
|Referencia externa ([instrucción Declare](../../../visual-basic/language-reference/statements/declare-statement.md))|No permitido|`Public` (no se permite en `Interface`)|No permitido|  
|Operador ([Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md))|No permitido|`Public` (no se permite en `Interface` o `Module`)|No permitido|  
|Propiedad ([Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md))|No permitido|`Public`|No permitido|  
|Propiedad predeterminada ([predeterminado](../../../visual-basic/language-reference/modifiers/default.md))|No permitido|`Public` (no se permite en `Module`)|No permitido|  
|Evento ([Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md))|No permitido|`Public`|No permitido|  
|Delegado ([Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md))|`Friend`|`Public`|No permitido|  
  
 Para obtener más información, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Vea también  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)
