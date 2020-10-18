---
title: Se esperaba una declaración
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: 2755f5afcb96ca7a6c4d140908649390dd66d571
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162705"
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
