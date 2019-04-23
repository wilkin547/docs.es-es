---
title: Reanudar sin error
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 61332486b20af66af24eac06b222a38353578c16
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300910"
---
# <a name="resume-without-error"></a>Reanudar sin error
Un `Resume` aparecido instrucción fuera del código de control de errores o el código pasó de un controlador de errores, aunque se ha producido ningún error.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Mover el `Resume` instrucción en un controlador de errores, o eliminarlo.  
  
2. No se pueden producir los saltos a etiquetas en los procedimientos, de modo que busque el procedimiento para la etiqueta que identifica el controlador de errores. Si encuentra una etiqueta duplicada especificada como destino de un `GoTo` instrucción que no sea un `On Error GoTo` instrucción, cambiar la etiqueta de línea para que coincida con su destino pretendido.  
  
## <a name="see-also"></a>Vea también

- [Resume (instrucción)](../../../visual-basic/language-reference/statements/resume-statement.md)
- [On Error (instrucción)](../../../visual-basic/language-reference/statements/on-error-statement.md)
