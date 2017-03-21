---
title: "&quot;&lt;atributo&gt;&quot; no puede aplicarse porque el formato del GUID &quot;&lt;número&gt;&quot; no es correcto | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32500
- bc32500
dev_langs:
- VB
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f22f9ecd63582e2a346702919cf9154819b8eb0e
ms.lasthandoff: 03/13/2017

---
# <a name="39ltattributegt39-cannot-be-applied-because-the-format-of-the-guid-39ltnumbergt39-is-not-correct"></a>'&lt;atributo&gt;' no puede aplicarse porque el formato del GUID '&lt;número&gt;' no es correcto
Un `COMClassAttribute` bloque de atributos especifica un identificador único global (GUID) que no cumple el formato apropiado para un GUID. `COMClassAttribute`utiliza los GUID para identificar de forma única la clase, la interfaz y el evento de creación.  
  
 Un GUID consta de 16 bytes, de los cuales los ocho primeros son numéricos y el resto son binarios. Se genera mediante utilidades de Microsoft como uuidgen.exe y se garantiza que sea único en el espacio y tiempo.  
  
 **Id. de error:** BC32500  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Determinar el GUID o el GUID es necesarios para identificar el objeto COM correcto.  
  
2.  Asegúrese de que las cadenas del GUID presentadas en el bloque de atributos `COMClassAttribute` se copian correctamente.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Guid></xref:System.Guid>   
[Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)


