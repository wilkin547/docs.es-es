---
title: Se esperaba 'Optional'
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 9c717cef2052722563e04595ef7a808ea103a75d
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159825"
---
# <a name="bc30202-optional-expected"></a>BC30202: se esperaba ' Optional '

Un argumento opcional en una declaración de procedimiento va seguido de un argumento necesario. Cada argumento que siga a un argumento opcional también debe ser opcional.

 **Identificador de error:** BC30202

## <a name="to-correct-this-error"></a>Para corregir este error

- Si el argumento está pensado para ser necesario, muévalo para que preceda al primer argumento opcional de la lista de argumentos.

- Si el argumento está pensado para ser opcional, use la `Optional` palabra clave.

## <a name="see-also"></a>Vea también

- [Parámetros opcionales](../../programming-guide/language-features/procedures/optional-parameters.md)
