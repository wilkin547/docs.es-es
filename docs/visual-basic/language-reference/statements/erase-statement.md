---
title: Erase (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 5828e28b84ec62c7ed674757090806d73c61caea
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966741"
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
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>Vea también
- [Nothing](../../../visual-basic/language-reference/nothing.md)
- [ReDim (instrucción)](../../../visual-basic/language-reference/statements/redim-statement.md)
