---
title: No se puede aplicar '<attribute>' porque el formato del GUID '<number>' no es correcto
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: f7b6e42480075666ce9f7e8fc6966bd4bb6b888a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977312"
---
# <a name="attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>no se puede aplicar '\<atributo > ' porque el formato del GUID '\<número > ' no es correcto

Un bloque de atributos `COMClassAttribute` especifica un identificador único global (GUID) que no se ajusta al formato adecuado para un GUID. `COMClassAttribute` utiliza GUID para identificar de forma única la clase, la interfaz y el evento de creación.  
  
 Un GUID consta de 16 bytes, de los cuales los ocho primeros son numéricos y el resto son binarios. Se genera mediante utilidades de Microsoft como Uuidgen. exe y se garantiza que es único en el espacio y en el tiempo.  
  
 **Identificador de error:** BC32500  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Determine el GUID o los GUID correctos necesarios para identificar el objeto COM.  
  
2. Asegúrese de que las cadenas del GUID presentadas en el bloque de atributos `COMClassAttribute` se copian correctamente.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Guid>
- [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)
