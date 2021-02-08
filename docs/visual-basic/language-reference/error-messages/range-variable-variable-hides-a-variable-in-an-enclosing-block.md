---
description: 'Más información sobre: BC36633: la variable <variable> de rango oculta una variable en un bloque de inclusión, una variable de rango definida previamente o una variable declarada implícitamente en una expresión de consulta'
title: La variable de rango <variable> oculta una variable en un bloque de inclusión, una variable de rango definida anteriormente o una variable declarada de forma implícita en una expresión de consulta
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: f8e5c109274af9c00963e8a9f18384a299d17a4a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792081"
---
# <a name="bc36633-range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a>BC36633: la variable \<variable> de rango oculta una variable en un bloque de inclusión, una variable de rango definida previamente o una variable declarada implícitamente en una expresión de consulta.

Un nombre de variable de rango especificado en una `Select` `From` cláusula,, `Aggregate` o `Let` duplica el nombre de una variable de rango ya especificada previamente en la consulta, o el nombre de una variable declarada implícitamente por la consulta, como un nombre de campo o el nombre de una función de agregado.

 **Identificador de error:** BC36633

## <a name="to-correct-this-error"></a>Para corregir este error

- Asegúrese de que todas las variables de rango de un ámbito de consulta determinado tienen nombres únicos. Puede incluir una consulta entre paréntesis para asegurarse de que las consultas anidadas tienen un ámbito único.

## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Cláusula From](../queries/from-clause.md)
- [Cláusula Let](../queries/let-clause.md)
- [Aggregate Clause](../queries/aggregate-clause.md)
- [Select (cláusula)](../queries/select-clause.md)
