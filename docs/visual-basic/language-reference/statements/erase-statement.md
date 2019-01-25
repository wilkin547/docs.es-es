---
title: Erase (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: cab3da4465b4671d203036c2d9bcd40662dc234a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522445"
---
# <a name="erase-statement-visual-basic"></a>Erase (Instrucción, Visual Basic)
Se utiliza para liberar variables de matriz y desasignar la memoria utilizada para sus elementos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a>Elementos  
 `arraylist`  
 Obligatorio. Lista de variables de matriz debe borrarse. Las variables se separan con comas.  
  
## <a name="remarks"></a>Comentarios  
 El `Erase` instrucción sólo puede aparecer en el nivel de procedimiento. Esto significa que puede publicar matrices dentro de un procedimiento, pero no en el nivel de clase o módulo.  
  
 El `Erase` instrucción es equivalente a asignar `Nothing` a cada variable de matriz.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Erase` instrucción borrar dos matrices y liberar su memoria (1000 y 100 elementos de almacenamiento, respectivamente). El `ReDim` instrucción, a continuación, asigna una nueva instancia de matriz a la matriz tridimensional.  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también
- [Nothing](../../../visual-basic/language-reference/nothing.md)
- [ReDim (instrucción)](../../../visual-basic/language-reference/statements/redim-statement.md)
