---
description: "Más información sobre: BC32500: ' <attribute> ' no se puede aplicar porque el formato del GUID ' <number> ' no es correcto"
title: No se puede aplicar '<attribute>' porque el formato del GUID '<number>' no es correcto
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: a527608aebf338a5877bb3439f45fc79a40f5ac1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797138"
---
# <a name="bc32500-attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>No se puede aplicar BC32500: ' \<attribute> ' porque el formato del GUID ' \<number> ' no es correcto

Un `COMClassAttribute` bloque de atributos especifica un identificador único global (GUID) que no se ajusta al formato adecuado para un GUID. `COMClassAttribute` utiliza GUID para identificar de forma única la clase, la interfaz y el evento de creación.

 Un GUID consta de 16 bytes, de los cuales los ocho primeros son numéricos y el resto son binarios. Se genera mediante utilidades de Microsoft como uuidgen.exe y se garantiza que es único en el espacio y en el tiempo.

 **Identificador de error:** BC32500

## <a name="to-correct-this-error"></a>Para corregir este error

1. Determine el GUID o los GUID correctos necesarios para identificar el objeto COM.

2. Asegúrese de que las cadenas del GUID presentadas en el bloque de atributos `COMClassAttribute` se copian correctamente.

## <a name="see-also"></a>Vea también

- <xref:System.Guid>
- [Información general de atributos](../../programming-guide/concepts/attributes/index.md)
