---
description: 'Más información sobre: contextos de declaración y niveles de acceso predeterminados (Visual Basic)'
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
ms.openlocfilehash: c550db39862fbe9f69e5651b6e9fc7fdfcc88513
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700343"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>Contextos de declaración y niveles de acceso predeterminados (Visual Basic)

En este tema se describe qué tipos de Visual Basic se pueden declarar dentro de los demás tipos y cuál es el valor predeterminado de los niveles de acceso si no se especifica.  
  
## <a name="declaration-context-levels"></a>Niveles de contexto de declaración  

 El *contexto* de la declaración de un elemento de programación es la región de código en la que se declara. A menudo, se trata de otro elemento de programación, que se llama *elemento contenedor*.  
  
 Los niveles de los contextos de declaración son los siguientes:  
  
- *Nivel de espacio de nombres* : dentro de un archivo de código fuente o espacio de nombres pero no dentro de una clase, estructura, módulo o interfaz  
  
- *Nivel de módulo* : dentro de una clase, una estructura, un módulo o una interfaz, pero no dentro de un procedimiento o bloque  
  
- *Nivel de procedimiento* : dentro de un procedimiento o bloque (como `If` o `For` )  
  
 En la tabla siguiente se muestran los niveles de acceso predeterminados para varios elementos de programación declarados, en función de sus contextos de declaración.  
  
|Elemento declarado|Nivel de espacio de nombres|Nivel de módulo|Nivel de procedimiento|  
|----------------------|---------------------|------------------|---------------------|  
|Variable ([instrucción Dim](dim-statement.md))|No permitida|`Private` ( `Public` in `Structure` , no se permite en `Interface` )|`Public`|  
|Constant ([instrucción const](const-statement.md))|No permitida|`Private` ( `Public` in `Structure` , no se permite en `Interface` )|`Public`|  
|Enumeración ([instrucción enum](enum-statement.md))|`Friend`|`Public`|No permitida|  
|Class ([instrucción de clase](class-statement.md))|`Friend`|`Public`|No permitida|  
|Structure ([instrucción Structure](structure-statement.md))|`Friend`|`Public`|No permitida|  
|Module ([instrucción de módulo](module-statement.md))|`Friend`|No permitido|No permitido|  
|Interface ([instrucción interface](interface-statement.md))|`Friend`|`Public`|No permitida|  
|Procedure ([instrucción function](function-statement.md), [Sub Statement](sub-statement.md))|No permitido|`Public`|No permitido|  
|Referencia externa ([instrucción Declare](declare-statement.md))|No permitida|`Public` (no se permite en `Interface` )|No permitida|  
|Operator ([instrucción de operador](operator-statement.md))|No permitida|`Public` (no se permite en `Interface` o `Module` )|No permitida|  
|Property ([instrucción de propiedad](property-statement.md))|No permitido|`Public`|No permitido|  
|Propiedad default ([valor predeterminado](../modifiers/default.md))|No permitida|`Public` (no se permite en `Module` )|No permitida|  
|Event ([instrucción de evento](event-statement.md))|No permitido|`Public`|No permitido|  
|Delegate ([instrucción Delegate](delegate-statement.md))|`Friend`|`Public`|No permitida|  
  
 Para obtener más información, consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Vea también

- [Friend](../modifiers/friend.md)
- [Privado](../modifiers/private.md)
- [Público](../modifiers/public.md)
