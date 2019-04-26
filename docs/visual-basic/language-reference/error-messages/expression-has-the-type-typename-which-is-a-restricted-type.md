---
title: La expresión tiene el tipo '<typename>' que es un tipo restringido y no se puede utilizar para obtener acceso a miembros heredados de 'Object' o 'ValueType'
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 017a2458562068727674bd3fd9cda8c33d989e8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803173"
---
# <a name="expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a>Expresión tiene el tipo '\<typename >' que es un tipo restringido y no se puede usar para tener acceso a miembros heredados de 'Object' o 'ValueType'
Una expresión se evalúa como un tipo que no se puede realizar la conversión boxing por common language runtime (CLR), pero tiene acceso a un miembro que requiere la conversión boxing.  
  
 La*conversión boxing* hace referencia al procesamiento necesario para convertir un tipo a `Object` o, en ocasiones, a <xref:System.ValueType>. Common language runtime no puede encerrar ciertos tipos de estructura, por ejemplo <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, y <xref:System.TypedReference>.  
  
 Esta expresión intenta utilizar el tipo restringido para llamar a un método heredado de <xref:System.Object> o <xref:System.ValueType>, tales como <xref:System.Object.GetHashCode%2A> o <xref:System.Object.ToString%2A>. Para obtener acceso a este método, Visual Basic ha intentado una conversión boxing implícita que produce este error.  
  
 **Identificador de error:** BC31393  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Localice la expresión que se evalúa en el tipo mencionado.  
  
2. Busque la parte de la instrucción que intenta llamar al método se hereda de <xref:System.Object> o <xref:System.ValueType>.  
  
3. Reescriba la instrucción para evitar la llamada al método.  
  
## <a name="see-also"></a>Vea también

- [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
