---
title: Instrucción Erase
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 31aeaf822bc9c1de59a5c5f68406c6521216ae0e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404724"
---
# <a name="erase-statement-visual-basic"></a>Erase (Instrucción, Visual Basic)
Se usa para liberar las variables de matriz y desasignar la memoria usada para sus elementos.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a>Partes  
 `arraylist`  
 Necesario. Lista de variables de matriz que se van a borrar. Las variables se separan con comas.  
  
## <a name="remarks"></a>Observaciones  
 La `Erase` instrucción solo puede aparecer en el nivel de procedimiento. Esto significa que puede liberar matrices dentro de un procedimiento, pero no en el nivel de clase o módulo.  
  
 La `Erase` instrucción es equivalente a asignar `Nothing` a cada variable de matriz.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa la `Erase` instrucción para borrar dos matrices y liberar su memoria (elementos de almacenamiento 1000 y 100, respectivamente). `ReDim`A continuación, la instrucción asigna una nueva instancia de matriz a la matriz de tres dimensiones.  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>Consulte también

- [Relación](../nothing.md)
- [Instrucción ReDim](redim-statement.md)
