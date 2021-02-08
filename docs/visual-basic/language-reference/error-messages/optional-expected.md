---
description: "Más información acerca de: se esperaba BC30202: ' Optional '"
title: Se esperaba 'Optional'
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 543dbf6226d4d298d46764ee506b55e770c91604
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795552"
---
# <a name="bc30202-optional-expected"></a>BC30202: se esperaba ' Optional '

Un argumento opcional en una declaración de procedimiento va seguido de un argumento necesario. Cada argumento que siga a un argumento opcional también debe ser opcional.

 **Identificador de error:** BC30202

## <a name="to-correct-this-error"></a>Para corregir este error

- Si el argumento está pensado para ser necesario, muévalo para que preceda al primer argumento opcional de la lista de argumentos.

- Si el argumento está pensado para ser opcional, use la `Optional` palabra clave.

## <a name="see-also"></a>Vea también

- [Parámetros opcionales](../../programming-guide/language-features/procedures/optional-parameters.md)
