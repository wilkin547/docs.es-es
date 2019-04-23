---
title: No se puede aplicar '<attribute>' porque el formato del GUID '<number>' no es correcto
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: d27c326b6a88271ba4abf0144e71027f6671b17e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330680"
---
# <a name="attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>'\<atributo >' no se puede aplicar porque el formato del GUID '\<número >' no es correcto
Un `COMClassAttribute` bloque de atributos especifica un identificador único global (GUID) que no se ajusta al formato apropiado para un GUID. `COMClassAttribute` usa los GUID para identificar de forma exclusiva la clase, la interfaz y el evento de creación.  
  
 Un GUID consta de 16 bytes, de los cuales los ocho primeros son numéricos y el resto son binarios. Se genera mediante utilidades de Microsoft como uuidgen.exe y se garantiza que sea único en el espacio y tiempo.  
  
 **Identificador de error:** BC32500  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Determinar el GUID o el GUID es necesarios para identificar el objeto COM correcto.  
  
2. Asegúrese de que las cadenas del GUID presentadas en el bloque de atributos `COMClassAttribute` se copian correctamente.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Guid>
- [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)
