---
description: 'Más información sobre: una llamada a una propiedad o un método no puede incluir una referencia a un objeto privado, ya sea como argumento o como valor devuelto'
title: Una llamada a una propiedad o un método no puede incluir una referencia a un objeto privado como un argumento o un valor de retorno
ms.date: 07/20/2015
f1_keywords:
- vbrID98
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
ms.openlocfilehash: 8fe570c9ed789a5bac36aafa9b1ec2f507a55d51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797203"
---
# <a name="a-property-or-method-call-cannot-include-a-reference-to-a-private-object-either-as-an-argument-or-as-a-return-value"></a>Una llamada a una propiedad o un método no puede incluir una referencia a un objeto privado como un argumento o un valor de retorno

Entre las causas posibles de este error se incluyen:

- Un cliente invocó una propiedad o un método de un componente fuera de proceso e intentó pasar una referencia a un objeto privado como uno de los argumentos.

- Un componente fuera de proceso invocó un método de devolución de llamada en su cliente e intentó pasar una referencia a un objeto privado.

- Un componente fuera de proceso intentó pasar una referencia a un objeto privado como un argumento de un evento que estaba generando.

- Un cliente intentó asignar una referencia de objeto privado a un argumento `ByRef` de un evento que estaba controlando.

## <a name="to-correct-this-error"></a>Para corregir este error

- Quite la referencia.

## <a name="see-also"></a>Vea también

- [Privado](../modifiers/private.md)
