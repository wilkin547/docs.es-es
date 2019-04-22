---
title: "'<elementname>' está obsoleto (Advertencia de Visual Basic)"
ms.date: 07/20/2015
f1_keywords:
- vbc40008
- bc40008
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
ms.openlocfilehash: 545f0f4a56e72e32d2225217225d441a10f0e52e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836368"
---
# <a name="elementname-is-obsolete-visual-basic-warning"></a>'\<elementname >' está obsoleto (advertencia de Visual Basic)
Una instrucción intenta obtener acceso a un elemento de programación que se ha marcado con el atributo <xref:System.ObsoleteAttribute> y la directiva para tratarlo como una advertencia.  
  
 Puede marcar que un elemento de programación ya no está en uso aplicándole <xref:System.ObsoleteAttribute> . Si lo hace, puede establecer la propiedad <xref:System.ObsoleteAttribute.IsError%2A> del atributo en `True` o `False`. Si se establece en `True`, el compilador trata como un error los intentos de usar el elemento. Si se establece en `False`o se deja el valor predeterminado `False`, el compilador emite una advertencia si se produce un intento de usar el elemento.  
  
 De forma predeterminada, este mensaje es una advertencia, ya que la propiedad <xref:System.ObsoleteAttribute.IsError%2A> de <xref:System.ObsoleteAttribute> es `False`. Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40008  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Asegúrese de que la referencia del código fuente escriba correctamente el nombre del elemento.  
  
## <a name="see-also"></a>Vea también

- [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)
