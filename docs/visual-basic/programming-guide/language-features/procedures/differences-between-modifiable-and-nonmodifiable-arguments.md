---
title: Diferencias entre argumentos modificables y no modificables (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ab108d064f5c6740f80328a9b6db4785334550ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a>Diferencias entre argumentos modificables y no modificables (Visual Basic)
Cuando se llama a un procedimiento, normalmente se pasa uno o más argumentos a él. Cada argumento corresponde a un elemento de programación subyacente. Los elementos subyacentes y los argumentos pueden ser modificables o no modificables.  
  
## <a name="modifiable-and-nonmodifiable-elements"></a>Elementos modificables y no modificables  
 Un elemento de programación puede ser un *elemento modificable*, que puede tener su valor cambiado, o un *elemento no modificable*, que tiene un valor fijo, una vez que se ha creado.  
  
 En la tabla siguiente se enumera los elementos de programación modificables y no modificables.  
  
|Elementos modificables|Elementos no modificables|  
|-------------------------|----------------------------|  
|Las variables locales (declaradas dentro de procedimientos), incluidas las variables de objeto, excepto las de sólo lectura|Propiedades, campos y variables de solo lectura|  
|Campos (variables miembro de módulos, clases y estructuras), excepto las de sólo lectura|Constantes y literales|  
|Propiedades, excepto las de sólo lectura|Miembros de enumeración|  
|Elementos de matriz|Expresiones (incluso si sus elementos son modificables)|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a>Argumentos modificables y no modificables  
 A *argumento modificable* es aquel que tiene un elemento subyacente modificable. El código de llamada puede almacenar un nuevo valor en cualquier momento, y si se pasa el argumento [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), el código del procedimiento también puede modificar el elemento subyacente en el código de llamada.  
  
 A *argumento no modificable* tiene un elemento subyacente no modificable o se pasa [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). El procedimiento no puede modificar el elemento subyacente en el código que realiza la llamada, incluso si es un elemento modificable. Si es un elemento no modificable, el propio código de llamada no puede modificarlo.  
  
 El procedimiento llamado puede modificar su copia local de un argumento no modificable, pero que la modificación no afectaría al elemento subyacente en el código de llamada.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)  
 [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)  
 [Diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [Cambiar el valor de un argumento de procedimiento](./how-to-change-the-value-of-a-procedure-argument.md)  
 [Proteger un argumento de procedimiento para que no se realicen cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [Forzar un argumento para que pase como un valor](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)  
 [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
