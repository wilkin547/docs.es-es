---
description: "Más información sobre: BC31393: la expresión tiene el tipo ' <typename> ', que es un tipo restringido y no se puede usar para tener acceso a los miembros heredados de ' Object ' o ' ValueType '"
title: La expresión tiene el tipo '<typename>' que es un tipo restringido y no se puede utilizar para obtener acceso a miembros heredados de 'Object' o 'ValueType'
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 3b5f9bbb85d1645936286ea0e907e3e25764f69a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796384"
---
# <a name="bc31393-expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a>BC31393: la expresión tiene el tipo ' \<typename> ', que es un tipo restringido y no se puede usar para tener acceso a los miembros heredados de ' Object ' o ' ValueType '

Una expresión se evalúa como un tipo al que el Common Language Runtime (CLR) no puede aplicar la conversión boxing, pero tiene acceso a un miembro que requiere la conversión boxing.

 La *conversión boxing* hace referencia al procesamiento necesario para convertir un tipo a `Object` o, en ocasiones, a <xref:System.ValueType>. En el Common Language Runtime no se pueden Box determinados tipos de estructura, por ejemplo <xref:System.ArgIterator> , <xref:System.RuntimeArgumentHandle> y <xref:System.TypedReference> .

 Esta expresión intenta utilizar el tipo restringido para llamar a un método heredado de <xref:System.Object> o <xref:System.ValueType> , como <xref:System.Object.GetHashCode%2A> o <xref:System.Object.ToString%2A> . Para obtener acceso a este método, Visual Basic ha intentado realizar una conversión boxing implícita que produce este error.

 **Identificador de error:** BC31393

## <a name="to-correct-this-error"></a>Para corregir este error

1. Localice la expresión que se evalúa en el tipo mencionado.

2. Busque la parte de la instrucción que intenta llamar al método heredado de <xref:System.Object> o <xref:System.ValueType> .

3. Vuelva a escribir la instrucción para evitar la llamada al método.

## <a name="see-also"></a>Vea también

- [Conversiones implícitas y explícitas](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
