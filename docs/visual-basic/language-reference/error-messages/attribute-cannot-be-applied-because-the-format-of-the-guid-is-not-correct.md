---
title: No se puede aplicar '<attribute>' porque el formato del GUID '<number>' no es correcto
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: ab821db45ae834e82aa134b6f20ded14d43709ef
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832273"
---
# <a name="attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>'\<atributo >' no se puede aplicar porque el formato del GUID '\<número >' no es correcto
Un `COMClassAttribute` bloque de atributos especifica un identificador único global (GUID) que no se ajusta al formato apropiado para un GUID. `COMClassAttribute` usa los GUID para identificar de forma exclusiva la clase, la interfaz y el evento de creación.  
  
 Un GUID consta de 16 bytes, de los cuales los ocho primeros son numéricos y el resto son binarios. Se genera mediante utilidades de Microsoft como uuidgen.exe y se garantiza que sea único en el espacio y tiempo.  
  
 **Identificador de error:** BC32500  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Determinar el GUID o el GUID es necesarios para identificar el objeto COM correcto.  
  
2.  Asegúrese de que las cadenas del GUID presentadas en el bloque de atributos `COMClassAttribute` se copian correctamente.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Guid>
- [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)
