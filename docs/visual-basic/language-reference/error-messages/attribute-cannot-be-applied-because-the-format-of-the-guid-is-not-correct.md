---
title: '&#39;&lt;atributo&gt; &#39; no se puede aplicar porque el formato del GUID &#39; &lt;número&gt; &#39; no es correcto'
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: 85b8c9dcccbb307d8a744e33a5f1d4b1775fda04
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623670"
---
# <a name="39ltattributegt39-cannot-be-applied-because-the-format-of-the-guid-39ltnumbergt39-is-not-correct"></a>&#39;&lt;atributo&gt; &#39; no se puede aplicar porque el formato del GUID &#39; &lt;número&gt; &#39; no es correcto
Un `COMClassAttribute` bloque de atributos especifica un identificador único global (GUID) que no se ajusta al formato apropiado para un GUID. `COMClassAttribute` usa los GUID para identificar de forma exclusiva la clase, la interfaz y el evento de creación.  
  
 Un GUID consta de 16 bytes, de los cuales los ocho primeros son numéricos y el resto son binarios. Se genera mediante utilidades de Microsoft como uuidgen.exe y se garantiza que sea único en el espacio y tiempo.  
  
 **Identificador de error:** BC32500  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Determinar el GUID o el GUID es necesarios para identificar el objeto COM correcto.  
  
2.  Asegúrese de que las cadenas del GUID presentadas en el bloque de atributos `COMClassAttribute` se copian correctamente.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Guid>
- [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)

