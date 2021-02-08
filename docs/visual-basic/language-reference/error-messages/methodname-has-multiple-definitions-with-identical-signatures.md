---
description: "Más información sobre: BC30269: ' <methodname> ' tiene varias definiciones con firmas idénticas"
title: "'<methodname>' tiene varias definiciones con firmas idénticas"
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 7364ee7a308fab96afce268ff0c92cd45717f1bd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795812"
---
# <a name="bc30269-methodname-has-multiple-definitions-with-identical-signatures"></a>BC30269: ' \<methodname> ' tiene varias definiciones con firmas idénticas

Una `Function` `Sub` declaración de procedimiento o usa el nombre de procedimiento idéntico y la lista de argumentos como una declaración anterior. Una posible causa es un intento de sobrecargar el procedimiento original. Los procedimientos sobrecargados deben tener listas de argumentos diferentes.

 **Identificador de error:** BC30269

## <a name="to-correct-this-error"></a>Para corregir este error

- Cambie el nombre del procedimiento o la lista de argumentos, o bien Quite la declaración duplicada.

## <a name="see-also"></a>Vea también

- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Consideraciones sobre la sobrecarga de procedimientos](../../programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
