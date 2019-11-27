---
title: Erase (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 6d2052ceccbecd772c4e4bb18052aed74223a36e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343697"
---
# <a name="erase-statement-visual-basic"></a>Erase (Instrucción, Visual Basic)
Se usa para liberar las variables de matriz y desasignar la memoria usada para sus elementos.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a>Elementos  
 `arraylist`  
 Obligatorio. Lista de variables de matriz que se van a borrar. Las variables se separan con comas.  
  
## <a name="remarks"></a>Comentarios  
 La instrucción `Erase` solo puede aparecer en el nivel de procedimiento. Esto significa que puede liberar matrices dentro de un procedimiento, pero no en el nivel de clase o módulo.  
  
 La instrucción `Erase` es equivalente a asignar `Nothing` a cada variable de matriz.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa la instrucción `Erase` para borrar dos matrices y liberar su memoria (elementos de almacenamiento 1000 y 100, respectivamente). A continuación, la instrucción `ReDim` asigna una nueva instancia de la matriz a la matriz tridimensional.  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>Vea también

- [Nothing](../../../visual-basic/language-reference/nothing.md)
- [ReDim (instrucción)](../../../visual-basic/language-reference/statements/redim-statement.md)
