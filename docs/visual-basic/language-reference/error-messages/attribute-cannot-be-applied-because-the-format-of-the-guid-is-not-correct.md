---
title: No se puede aplicar '<attribute>' porque el formato del GUID '<number>' no es correcto
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: 554c38c8f44999feba4cfa04d58ce2f07e955eb1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409925"
---
# <a name="attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>No se puede aplicar '\<attribute>' porque el formato del GUID '\<number>' no es correcto

Un `COMClassAttribute` bloque de atributos especifica un identificador único global (GUID) que no se ajusta al formato adecuado para un GUID. `COMClassAttribute`utiliza GUID para identificar de forma única la clase, la interfaz y el evento de creación.  
  
 Un GUID consta de 16 bytes, de los cuales los ocho primeros son numéricos y el resto son binarios. Se genera mediante utilidades de Microsoft como Uuidgen. exe y se garantiza que es único en el espacio y en el tiempo.  
  
 **Identificador de error:** BC32500  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Determine el GUID o los GUID correctos necesarios para identificar el objeto COM.  
  
2. Asegúrese de que las cadenas del GUID presentadas en el bloque de atributos `COMClassAttribute` se copian correctamente.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Guid>
- [Información general de atributos](../../programming-guide/concepts/attributes/index.md)
