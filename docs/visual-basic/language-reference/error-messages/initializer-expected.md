---
title: Se esperaba un inicializador
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 0795fdc1c4b177e13979d7555cd7588217b8cb4c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013808"
---
# <a name="initializer-expected"></a>Se esperaba un inicializador
Ha intentado declarar una instancia de una clase con un inicializador de objeto en el que la lista de inicialización está vacía, tal como se muestra en el ejemplo siguiente.  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 Al menos un campo o propiedad se debe inicializar en la lista de inicializadores, como se muestra en el ejemplo siguiente.  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **Identificador de error:** BC30996  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Inicializar al menos un campo o propiedad en el inicializador o no use un inicializador de objeto.  
  
## <a name="see-also"></a>Vea también

- [Inicializadores de objeto: Tipos con nombre y anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Cómo: Declarar un objeto usando un inicializador de objeto](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
