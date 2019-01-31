---
title: No se puede aplicar '<attribute>' porque el formato del GUID '<number>' no es correcto
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: 1e92c77e6138bbd546d9b837e095e41d5dfaf30c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279869"
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

