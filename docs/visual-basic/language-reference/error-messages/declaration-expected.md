---
description: 'Más información acerca de: BC30188: se esperaba una declaración'
title: Se esperaba una declaración
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: b86c182fb9dc8ab7d624833136f0e87b072aed92
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796670"
---
# <a name="bc30188-declaration-expected"></a>BC30188: se esperaba una declaración

Una instrucción no declarativa, como una instrucción de asignación o bucle, se produce fuera de cualquier procedimiento. Solo se permiten declaraciones fuera de los procedimientos.

 Como alternativa, un elemento de programación se declara sin una palabra clave de declaración, como `Dim` o `Const` .

 **Identificador de error:** BC30188

## <a name="to-correct-this-error"></a>Para corregir este error

- Mueva la instrucción no declarativa al cuerpo de un procedimiento.

- Comience la declaración con una palabra clave de declaración adecuada.

- Asegúrese de que una palabra clave de declaración no esté mal escrita.

## <a name="see-also"></a>Vea también

- [Procedimientos](../../programming-guide/language-features/procedures/index.md)
- [Instrucción Dim](../statements/dim-statement.md)
