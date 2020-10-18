---
title: "'<methodname>' tiene varias definiciones con firmas idénticas"
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 663b22421d1a0e401cfb3c135c99bd097163a78b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160371"
---
# <a name="bc30269-methodname-has-multiple-definitions-with-identical-signatures"></a>BC30269: ' \<methodname> ' tiene varias definiciones con firmas idénticas

Una `Function` `Sub` declaración de procedimiento o usa el nombre de procedimiento idéntico y la lista de argumentos como una declaración anterior. Una posible causa es un intento de sobrecargar el procedimiento original. Los procedimientos sobrecargados deben tener listas de argumentos diferentes.

 **Identificador de error:** BC30269

## <a name="to-correct-this-error"></a>Para corregir este error

- Cambie el nombre del procedimiento o la lista de argumentos, o bien Quite la declaración duplicada.

## <a name="see-also"></a>Vea también

- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Consideraciones sobre la sobrecarga de procedimientos](../../programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
