---
description: "Más información acerca de: BC40008: ' <elementname> ' está obsoleto (Visual Basic ADVERTENCIA)"
title: "'<elementname>' está obsoleto (Advertencia de Visual Basic)"
ms.date: 07/20/2015
f1_keywords:
- vbc40008
- bc40008
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
ms.openlocfilehash: 6fea3526f19b139af103f21ddd89f2272eb6eac5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796579"
---
# <a name="bc40008-elementname-is-obsolete-visual-basic-warning"></a>BC40008: ' \<elementname> ' está obsoleto (advertencia Visual Basic)

Una instrucción intenta obtener acceso a un elemento de programación que se ha marcado con el atributo <xref:System.ObsoleteAttribute> y la directiva para tratarlo como una advertencia.

 Para marcar que cualquier elemento de programación ya no está en uso, aplíquele <xref:System.ObsoleteAttribute> . Si lo hace, puede establecer la propiedad <xref:System.ObsoleteAttribute.IsError%2A> del atributo en `True` o `False`. Si se establece en `True`, el compilador trata como un error los intentos de usar el elemento. Si se establece en `False`o se deja el valor predeterminado `False`, el compilador emite una advertencia si hay un intento de usar el elemento.

 De forma predeterminada, este mensaje es una advertencia, ya que la propiedad <xref:System.ObsoleteAttribute.IsError%2A> de <xref:System.ObsoleteAttribute> es `False`. Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identificador de error:** BC40008

## <a name="to-correct-this-error"></a>Para corregir este error

- Asegúrese de que la referencia del código fuente escriba correctamente el nombre del elemento.

## <a name="see-also"></a>Vea también

- [Información general de atributos](../../programming-guide/concepts/attributes/index.md)
